Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

### Input

Quando o usuário digitar alguma coisa, depois salvar as informações em uma state

## Criando com uma função externa

```js
import React, { useState } from "react"; /*Iportando state*/
import { Text, View } from "react-native";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  justify-content: center;
  align-items: center;
`;
const Input = styled.TextInput`
  width: 200px;
  height: 40px;
  border: 1px solid #000;
  border-radius: 10px;
`;

const Hello = ({ frase }) => {
  const [name, setName] = useState("Beto");

  function mudarTexto(texto) {
    setName(texto);
  }

  return (
    <View>
      <Input value={name} onChangeText={mudarTexto} />
      <Text>Olá {name}</Text>
    </View>
  );
};

function App() {
  return (
    <Page>
      <Hello />
    </Page>
  );
}

export default App;
```

## Criando uam função internamente

```js
import React, { useState } from "react"; /*Iportando state*/
import { Text, View } from "react-native";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  justify-content: center;
  align-items: center;
`;
const Input = styled.TextInput`
  width: 200px;
  height: 40px;
  border: 1px solid #000;
`;

const Hello = ({ frase }) => {
  const [name, setName] = useState("Beto");

  return (
    <View>
      <Input value={name} onChangeText={t => setName(t)} />
      <Text>Olá {name}</Text>
    </View>
  );
};

function App() {
  return (
    <Page>
      <Hello />
    </Page>
  );
}

export default App;
```
