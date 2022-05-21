Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Condicional de Exibição

App.js

```js
import React, { useState } from "react"; /*Iportando state*/
import { Text, View, Button } from "react-native";
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
  border-radius: 5px;
`;

const Quadrado = styled.View`
  width: 200px;
  height: 200px;
  justify-content: center;
  align-items: center;
  border: 3px dashed #000; //Esse dashed deixa pontilhado a linha
`;

const Hello = ({ frase }) => {
  const [name, setName] = useState("Qual o nome?");
  const [mostrar, setMostrar] = useState(false);

  const handleClick = () => {
    /*  if (mostrar == true) {
      setMostrar(false);
    } else {
      setMostrar(true);
    }
  };*/
    /*ou*/
    /*  if (mostrar) {
      setMostrar(false);
    } else {
      setMostrar(true);
    }
  };*/
    /*ou mais resumido ainda*/
    setMostrar(!mostrar);
  };

  return (
    <View>
      <Input value={name} onChangeText={t => setName(t)} />
      <Button
        title={mostrar ? "Ocultar Nome" : "Mostrar Nome"}
        onPress={handleClick}
      />

      {mostrar == true && (
        <Quadrado>
          <Text>Seu nome é:</Text>
          <Text>{name}</Text>
        </Quadrado>
      )}
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
