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

Modifier height
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

Modifierheight with width
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

Modifier size
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

Modifier padding
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

Modifier padding
```kotlin
@Composable
fun ModifierEx() {
  Button(
    colors = ButtonDefaults.buttonColors(
      Color.Magenta,
      contentColor = Color.Cyan
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

Click 범위 설정
```kotlin
@Composable
fun ModifierEx() {
  Button(
    colors = ButtonDefaults.buttonColors(
      Color.Magenta,
      contentColor = Color.Cyan
    ),
    onClick = {},
    modifier = Modifier.padding(100.dp),
    enabled = false // click 불가
  ) {
    Icon(
      imageVector = Icons.Filled.Search,
      contentDescription = "something search"
    )
    Spacer(modifier = Modifier.size(ButtonDefaults.IconSpacing))
    Text(
      text = "Search",
      modifier = Modifier.clickable {}
    )
  }
}
```

Offset
```kotlin
@Composable
fun ModifierEx() {
  Button(
    colors = ButtonDefaults.buttonColors(
      Color.Magenta,
      contentColor = Color.Cyan
    ),
    onClick = {},
    modifier = Modifier.padding(100.dp),  
  ) {
    Icon(
      imageVector = Icons.Filled.Search,
      contentDescription = "something search"
    )
    Spacer(modifier = Modifier.size(ButtonDefaults.IconSpacing))
    Text(
      text = "Search",
      modifier = Modifier.offset(x = 10.dp) // offset 설정
    )
  }
}
```
> spacer와 text 사이에 offset이 설정된 모습
<img width="203" alt="스크린샷 2024-01-24 오후 10 15 44" src="https://github.com/Chaebin-Park/Chaebin-Park.github.io/assets/64880435/385a9025-5fb2-4bc8-a41d-e140d3e4e8c9">
