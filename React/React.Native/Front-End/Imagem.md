Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

Importando uma imagem (Interna)

App.js

```js
import React from "react";
import styled from "styled-components/native";
import { Image } from "react-native";

const Page = styled.SafeAreaView`
  flex: 1;
  justify-content: center;
  align-items: center;
`;

function App() {
  return (
    <Page>
      <Image
        source={require("./src/images/logo.jpg")}
        style={{ width: 100, height: 100, backgroundColor: "#FF0000" }}
        //resizeMode="stretch" // Esta opção stretch, vai distorce o logo, para caber dentro do quadrado e não cortar
        //resizeMode="center" // centralizar minha imagem no meio, do <Image><Image/>
        resizeMode="cover" // Elá irá ocupar toda a área do <Image><Image/>
      />

      <Header />
    </Page>
  );
}

export default App;
```

Importando uma imagem, URL (Externa)

```js
import React, { useState } from "react";
import styled from "styled-components/native";
import { Image, Text } from "react-native";

const Page = styled.SafeAreaView`
  flex: 1;
  justify-content: center;
  align-items: center;
`;

function App() {
  const [status, setStatus] = useState("");
  return (
    <Page>
      <Image
        source={{ uri: "https://www.google.com.br/google.jpg" }}
        style={{ width: 200, height: 200, backgroundColor: "#FF0000" }}
        //resizeMode="stretch" // Esta opção stretch, vai distorce o logo, para caber dentro do quadrado e não cortar
        //resizeMode="center" // centralizar minha imagem no meio, do <Image><Image/>
        resizeMode="center" // Elá irá ocupar toda a área do <Image><Image/>
        defaultSource={require("./src/images/placeholder.jpg")} // Ira aparecer está imagem enquanto carrega a imagem interna para não ficar feio funciona no ios
        onLoadStart={() => setStatus("Carregando...")} // Quando inicia o carregamento de minha imagem
        /*onLoadEnd={() => setStatus("Carregou")} // Caregou imagem*/
        onLoad={() => setStatus("Carregou")} // desta forma só vai ser executado depois, de ter carregado e ter dado certo o carregamento, vai fazer primeiro onLoadStart depois o onError, ira fazer onload
        onError={e => setStatus(e.nativeEvent.error)} // Caso não acessar a url ou qualquer erro irá mostrar na tela
        /*onProgress={e => e.nativeEvent.total} */ // onProgress funciona só no ios, total quantidade total de bytes desta imagem
      />
      <Text>{status}</Text>
    </Page>
  );
}
// Ler a documentação do image para ver mais detalhes

export default App;
```
