Default
```kotlin
@Composable
fun ModifierEx() {
  Button(onClick = {}) {
    Icon(
      imageVector = Icons.Filled.Search,
      contentDescription = "something search"
    )
    Spacer(modifier = Modifier.size(ButtonDefaults.IconSpacing))
    Text(text = "Search")
  }
}
```

Modifier fillMaxSize
```kotlin
@Composable
fun ModifierEx() {
  Button(
    onClick = {},
    modifier = Modifier.fillMaxSize()
  ) {
    Icon(
      imageVector = Icons.Filled.Search,
      contentDescription = "something search"
    )
    Spacer(modifier = Modifier.size(ButtonDefaults.IconSpacing))
    Text(text = "Search")
  }
}
```

Modifier height
```kotlin
@Composable
fun ModifierEx() {
  Button(
    onClick = {},
    modifier = Modifier.height(100.dp)
  ) {
    Icon(
      imageVector = Icons.Filled.Search,
      contentDescription = "something search"
    )
    Spacer(modifier = Modifier.size(ButtonDefaults.IconSpacing))
    Text(text = "Search")
  }
}
```

Modifier height with width
```kotlin
@Composable
fun ModifierEx() {
  Button(
    onClick = {},
    modifier = Modifier
      .height(100.dp)
      .width(200.dp)
  ) {
    Icon(
      imageVector = Icons.Filled.Search,
      contentDescription = "something search"
    )
    Spacer(modifier = Modifier.size(ButtonDefaults.IconSpacing))
    Text(text = "Search")
  }
}
```

Modifier size
```kotlin
@Composable
fun ModifierEx() {
  Button(
    onClick = {},
    modifier = Modifier.size(200.dp, 100.dp) // size(width, height)
  ) {
    Icon(
      imageVector = Icons.Filled.Search,
      contentDescription = "something search"
    )
    Spacer(modifier = Modifier.size(ButtonDefaults.IconSpacing))
    Text(text = "Search")
  }
}
```

Background
```kotlin
@Composable
fun ModifierEx() {
  Button(
    onClick = {},
    modifier = Modifier
                .size(200.dp, 100.dp)
                .background(Color.Red) // Failed case: Button에서는 background 동작안함
  ) {
    Icon(
      imageVector = Icons.Filled.Search,
      contentDescription = "something search"
    )
    Spacer(modifier = Modifier.size(ButtonDefaults.IconSpacing))
    Text(text = "Search")
  }
}
```

Modifier padding
```kotlin
@Composable
fun ModifierEx() {
  Button(
    colors = ButtonDefaults.buttonColors(
      Color.Magenta,  // Button 자체 색상
      contentColor = Color.Cyan  // Button 내부 content 색상
    ),
    onClick = {},
    modifier = Modifier.padding(100.dp)
  ) {
    Icon(
      imageVector = Icons.Filled.Search,
      contentDescription = "something search"
    )
    Spacer(modifier = Modifier.size(ButtonDefaults.IconSpacing))
    Text(text = "Search")
  }
}
```

Modifier padding
```kotlin
@Composable
fun ModifierEx() {
  Button(
    colors = ButtonDefaults.buttonColors(
      Color.Magenta,  // Button 자체 색상
      contentColor = Color.Cyan  // Button 내부 content 색상
    ),
    onClick = {},
    modifier = Modifier.padding(100.dp)
  ) {
    Icon(
      imageVector = Icons.Filled.Search,
      contentDescription = "something search"
    )
    Spacer(modifier = Modifier.size(ButtonDefaults.IconSpacing))
    Text(text = "Search")
  }
}
```
