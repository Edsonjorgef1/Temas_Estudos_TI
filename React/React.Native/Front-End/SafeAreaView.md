Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

SafeAreaView, é bom, tem algumas coisas que ele vai ajustar no IOS

```js
import React from "react";
import { SafeAreaView, Image, StyleSheet } from "react-native";

const styles = StyleSheet.create({
  container: {
    backgroundColor: "black",
    height: "100vh",
    display: "flex",
    alignItems: "center",
    justifyContent: "center",
    flexDirection: "row",
  },
  Logo: {
    width: 50,
    height: 50,
  },
});

const DisplayAnImage = () => {
  return (
    <SafeAreaView style={styles.container}>
      <Image
        style={styles.Logo}
        source={{
          uri: "https://reactnative.dev/img/tiny_logo.png",
        }}
      />
    </SafeAreaView>
  );
};

export default DisplayAnImage;
```
