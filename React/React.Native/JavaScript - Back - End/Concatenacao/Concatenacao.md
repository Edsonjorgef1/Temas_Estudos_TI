Arquivo, App.js

```js
import React from "react";
import { View, Text } from "react-native";

const canal = "Engenheiro Youtuber";
const curso = "Curso de React";

export default function App_function_Component() {
  return (
    <View className="App">
      <Text> {"Canal: " + canal} </Text>
      <Text> {curso} </Text>
    </View>
  );
}
```
