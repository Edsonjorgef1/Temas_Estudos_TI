Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

Arquivo, App.js

```js
import React from "react";
import { View, Text } from "react-native";

const canal = () => {
  return "Engenheiro Youtuber";
};

export default function App_function_Component() {
  return (
    <View className="App_function_Component">
      <Text> {"Canal: " + canal()} </Text>
    </View>
  );
}
```
