# TopLevel

```kotlin
@Composable
fun TopLevel() {
  val (text, setText) = remember { mutableStateOf("") }
  val toDoList = remember { mutableStateListOf<ToDoData>() }

  val onSubmit: (String) -> Unit = { inputText ->
    val key = (toDoList.lastOrNull()?.key ?: 0) + 1
    val data = ToDoData(key, inputText)
    toDoList.add(data)
    setText("")
  }

  val onToggle: (Int, Boolean) -> Unit = { key, checked ->
    val index = toDoList.indexOfFirst { it.key == key }
    val copy = toDoList[index].copy(done = checked)
    toDoList[index] = copy
  }

  val onDelete: (Int) -> Unit = { key ->
    val index = toDoList.indexOfFirst { it.key == key }
    toDoList.removeAt(index)
  }

  val onEdit: (Int, String) -> Unit = { key, editText ->
    val index = toDoList.indexOfFirst { it.key == key }
    val copy = toDoList[index].copy(text = editText)
    toDoList[index] = copy
  }

  Scaffold { innerPadding ->
    Column(
      modifier = Modifier
        .fillMaxSize()
        .padding(innerPadding)
    ) {
      ToDoInput(
        text = text,
        onTextChange = setText,
        onSubmit = onSubmit
      )

      LazyColumn {
        items(toDoList) { data ->
          ToDo(
            toDoData = data,
            onToggle = onToggle,
            onDelete = onDelete,
            onEdit = onEdit
          )
        }
      }
    }
  }
}
```

# ToDoInput

> 텍스트 입력받는 용도

```kotlin
@Composable
fun ToDoInput(
  text: String,
  onTextChange: (String) -> Unit,
  onSubmit: (String) -> Unit
) {
  Row(modifier = Modifier.padding(8.dp)) {
    OutlinedTextField(value = text, onValueChange = onTextChange, modifier = Modifier.weight(1f))
    Spacer(modifier = Modifier.size(8.dp))
    Button(onClick = { onSubmit(text) }) {
      Text("입력")
    }
  }
}
```

# ToDo

> 입력받은 Todo 목록 아이템

```kotlin
@Composable
fun ToDo(
  toDoData: ToDoData,
  onEdit: (key: Int, text: String) -> Unit = { _, _ -> },
  onToggle: (key: Int, checked: Boolean) -> Unit = { _, _ -> },
  onDelete: (key: Int) -> Unit = {}
) {
  var isEditing by remember { mutableStateOf(false) }
  Card(
    modifier = Modifier.padding(4.dp),
    elevation = CardDefaults.cardElevation(8.dp)
  ) {
    // isEditing이 true일 경우, edit UI
    // isEditing이 false일 경우, 일반적인 목록 UI
    Crossfade(targetState = isEditing, label = "") {
      when (it) {
        true -> {
          Row(
            modifier = Modifier.padding(8.dp),
            verticalAlignment = Alignment.CenterVertically
          ) {
            val (newText, setNewText) = remember { mutableStateOf(toDoData.text) }
            
            OutlinedTextField(value = newText, onValueChange = setNewText, modifier = Modifier.weight(1f))
            Spacer(modifier = Modifier.size(4.dp))
            Button(onClick = {
              onEdit(toDoData.key, newText)
              isEditing = false
            }) {
              Text("완료")
            }
          }
        }
        false -> {
          Row(
            modifier = Modifier.padding(8.dp),
            verticalAlignment = Alignment.CenterVertically
          ) {
            Text(text = toDoData.text, modifier = Modifier.weight(1f))
            Text(text = "완료")
            Checkbox(
              checked = toDoData.done,
              onCheckedChange = { checked -> onToggle(toDoData.key, checked) })
            Button(onClick = { isEditing = true }) {
              Text(text = "수정")
            }
            Spacer(modifier = Modifier.size(4.dp))
            Button(onClick = { onDelete(toDoData.key) }) {
              Text(text = "삭제")
            }
          }
        }
      }
    }
  }
}
```

