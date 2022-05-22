Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## APIs Alert

```js
import React, { useEffect } from "react";
import { Alert } from "react-native";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  justify-content: center;
  align-items: center;
`;

function App() {
  useEffect(() => {
    /*Vamos entender como funciona*/
    Alert.alert("Titulo do alerta", "Mensagem qualquer", [
      /*Aqui eu posso montar os botões que eu quero, array com objetos*/
      { text: "Concordo", onPress: () => console.log("Concordo") },
      {
        text: "Não concordo",
        onPress: () =>
          console.log(
            "Não concordou!"
          ) /*Botão padrão se quiser colocar cancel */,
        /*style: "cancel",*/
      },

      /*Apartir do terceiro botão ja fica um embaixo do outro*/
    ]);

    /*Exemplo da documentação */
    /*Alert.alert(
      "Alert Title",
      "My Alert Msg",
      [
        {
          text: "Ask me later",
          onPress: () => console.log("Ask me later pressed"),
        },
        {
          text: "Cancel",
          onPress: () => console.log("Cancel Pressed"),
          style: "cancel",
        },
        { text: "OK", onPress: () => console.log("OK Pressed") },
      ],
      { cancelable: false }
    );*/
  }, []);
  return <Page></Page>;
}

export default App;
```
