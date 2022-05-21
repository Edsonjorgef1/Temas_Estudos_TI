Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Lidando com Teclado e Platform

```js
import React, { useEffect } from "react";
import { Platform } from "react-native";
//import { useEffect } from "react/cjs/react.production.min";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  justify-content: center;
  align-items: center;
`;
const Logo = styled.View`
  width: 100px;
  height: 100px;
  background-color: #000;
  margin-bottom: 20px;
`;
const Input = styled.TextInput`
  width: 90%;
  height: 50px;
  border: 1px solid #000;
`;
const KeyboardArea = styled.KeyboardAvoidingView`
  width: 100%;
  flex: 1;
  background-color: ${Platform.OS == "ios" ? "#00FF00" : "#0000FF"};
  justify-content: center;
  align-items: center;
`;

function App() {
  //Mostrando qual sistema está em uso naquele momento
  /* useEffect(() => {
    alert(`Sistema: ${Platform.OS} - ${Platform.Version}`);
  }, []);*/
  return (
    <Page>
      <KeyboardArea behavior={Platform.OS == "ios" ? "padding" : null}>
        {/*padding ele da uma margem na parte inferior, height vai alterar a altura como um todo, para este opção tem que tirar o flex:1 do KeyboardArea */}
        <Logo></Logo>
        <Input />
      </KeyboardArea>
    </Page>
  );
}

export default App;

//KeyboardAvoidingView = Ela igual uma view si que se comporta diferente no ios e android
//Na documentação fala que para android não coloque o behavior="padding" agora no ios que você ponha o  behavior="padding"
//behavior ele evita o teclado passar por cima do nosso layout
```
