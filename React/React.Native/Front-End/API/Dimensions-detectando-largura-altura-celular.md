Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## APIs dimensions

Api dimensions

```js
https://reactnative.dev/docs/dimensions
```

App.js

```js
import React, { useEffect } from "react";
import { Dimensions } from "react-native";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  justify-content: center;
  align-items: center;
`;

function App() {
  useEffect(() => {
    let { width: largura, height: altura } = Dimensions.get("window"); // Desta forma eu pego a largura e altura do dispositivo*/
    /*ou*/
    /*let largura = Dimensions.get("window").width; // Aqui eu pego somente a largura*/
    /*let altura = Dimensions.get("window").height; // Aqui eu pego somente a altura*/
    // alert("Altura:" + altura);
    alert(largura + "x" + altura);
  }, []);
  return <Page></Page>;
}

export default App;
```
