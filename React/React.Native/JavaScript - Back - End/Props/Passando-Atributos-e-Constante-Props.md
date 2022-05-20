Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

### Props

Props são propriedades, que você poem ao seu componente externamente, então
normalmente props são propriedades fixas, são coisas que não vão mudar com o

## Passando um nome com props

```js
import React from "react";
import { Text } from "react-native";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  justify-content: center;
  align-items: center;
`;
const Hello = props => {
  return <Text>{props.frase}</Text>;
};

function App() {
  return (
    <Page>
      <Hello frase="Seja bem vindo(a)" />
      <Hello frase="Outra frase" />
    </Page>
  );
}

export default App;

/*ou*/

/******************************/

import React from "react";
import { Text } from "react-native";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  justify-content: center;
  align-items: center;
`;
const Hello = ({ frase }) => {
  return <Text>{frase}</Text>;
};

function App() {
  return (
    <Page>
      <Hello frase="Seja bem vindo(a)" />
      <Hello frase="Outra frase" />
    </Page>
  );
}

export default App;
```

## Passando atributos para a props

Arquivo, App.js

```js
import React from "react";
import Dados from "./componentes/Dados";
import { View } from "react-native";

export default function App() {
  const cnl = "Engenheiro Youtuber";
  const yt = "youtube.com/engenheiroyoutuber";
  const crs = "React.js";

  return (
    <View className="App">
      <Dados canal={cnl} youtube={yt} curso={crs} />
    </View>
  );
}
```

Arquivo, Dados.js

Passando conteúdo de uma constante

```js
import React from "react";
import { View, Text } from "react-native";

export default function Dados(props) {
  // Este (props), aqui desta linha tem que ir para, poder passar atributos para o componente
  return (
    <View className="App">
      <Text> Canal:{props.canal} </Text>
      <Text> Youtube: {props.youtube} </Text>
      <Text> Curso: {props.curso} </Text>
    </View>
  );
}
```
