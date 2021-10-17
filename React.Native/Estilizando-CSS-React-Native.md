## Estilizando o CSS, dentro de um arquivo .CSS (Projeto básico do React.native, após criado o projeto, 1 Opção)

Comando para criar um projeto em React.native

```js
npx create-react-native-app (Nome do projeto)
```

Para estilizar o css em React.native, modelo padão que vem, depois que cria o projeto, você deve importar o "StyleSheet", para que possa funcionar.

```js
import { StyleSheet } from "react-native";
```

Exemplo: Text, ele é o texto que será exibido na tela, mas para isso você deve importar ele, igual está abaixo.

```js
import { Text } from "react-native";
```

Exemplo: View, ele é igual a div, do react.js, só que no react.native está com este nome, para ele funcionar você deve importar ele também.

```js
import { View } from "react-native";
```

View, foi adicionado, este comando para estlizar o css.
Container e o nome que eu criei para esta nova view, ok, você poderia dar qualquer nome para ela, lembrando que a View e como se fosse a div do react.js ou do Html padrão.

```js
<View style={styles.container}></View>
```

Text, foi adicionado este comando para estilizar o css.
logo é o nome que eu criei para este novo text.
Text significa, texto.

```js
<Text style={styles.logo}>Engenheiro Youtuber</Text>
```

Arquivo App.js

```js
import React from "react";

import { StyleSheet, Text, View } from "react-native";

export default class App extends React.Component {
  render() {
    return (
      <View style={styles.container}>
        <Text style={styles.logo}>Engenheiro Youtuber</Text>
      </View>
    );
  }
}
//Chamando o Css, estrutura padrão.
const styles = StyleSheet.create({
  container: {
    flex: 1, // Pegar o espaço disponível
    backgroundColor: "#003f5c", // Cor de fundo
    alignItems: "center", //  Centraliza verticalmente
    textAlign: "center", // Centraliza no meio da tela
    justifyContent: "center", //Para alinhar itens flexíveis ao longo do eixo principal
  },
  logo: {
    fontWeight: "bold", // Tipo da fonte
    fontSize: 50, // Tamanho da fonte
    color: "#fb5b5a", // Cor da fonte
    textAlign: "center", // Centraliza no meio da tela
    marginBottom: 10, // Margem inferior
  },
});
```

## Estilizando o CSS, dentro de um arquivo .CSS (Projeto básico do React, após criado o projeto, 2 Opção)

Neste outro modelo, é quase igual o exemplo anterior, deve importar, "Text", "View".
O"StyleSheet", que foi importado anteriormente neste exemplo não precisa.

View foi adicionado este comando para estilizar o css

```js
 <View> style={{Aqui dentro, Css}} </View>
```

Text, foi adicionado este comando para estilizar o css

```js
 <Text> style={{Aqui dentro, Css}} </Text>
```

```js
import React from "react";

import { Text, View } from "react-native";

export default class App extends React.Component {
  render() {
    return (
      <View
        style={{
          flex: 1,
          backgroundColor: "#003f5c",
          alignItems: "center",
          textAlign: "center",
          justifyContent: "center",
        }}
      >
        <Text
          style={{
            fontWeight: "bold",
            fontSize: 50,
            color: "#fb5b5a",
            textAlign: "center",
            marginBottom: 10,
          }}
        >
          Engenheiro Youtuber
        </Text>
      </View>
    );
  }
}
```

## Estilizando o CSS, dentro de um arquivo .js (styled-components, 1 Opção)

Comando para instalar o styled-components

```js
yarn add styled-components
```

Arquivo App.js

```js
import React from "react";

import { Container, Title } from "./style";

function App() {
  return (
    <Container>
      <Title>Hello Word</Title>
    </Container>
  );
}

export default App;
```

Arquivo, style.js

```js
import styled, { CSS } from "styled-components/native";

export const Container = styled.View`
  flex: 1;
  background-color: yellow;
  justify-content: center;
`;

export const Title = styled.Text`
  color: black;
  text-align: center;
`;
```

## Estilizando o CSS, dentro de um arquivo .js (styled-components, 2 Opção)

Repare que neste exemplo, é mais resumido, olha esta linha abaixo, o St,
subistitui todos os nomes que estavam sendo importados anteriormente.

```js
import * as St from "./style";
```

Arquivo App.js

```js
import React from "react";

import * as St from "./style";

function App() {
  return (
    <St.Container>
      <St.Title>Hello Word</St.Title>
    </St.Container>
  );
}

export default App;
```

Arquivo, style.js

```js
import styled, { CSS } from "styled-components/native";

export const Container = styled.View`
  flex: 1;
  background-color: yellow;
  justify-content: center;
`;

export const Title = styled.Text`
  color: black;
  text-align: center;
`;
```

## Estilizando o CSS, dentro de um arquivo .js (styled-components, 3 Opção)

Repare que neste exemplo, está tudo no mesmo arquivo, não estamos utizando
outro arquivo para separar o css, agora depende qual a empresa vai querer para
estilizar o projeto.

Arquivo App.js

```js
import React from "react";
import styled, { Css } from "styled-components/native";

const Geral = styled.View`
  flex: 1;
  background-color: yellow;
  justify-content: center;
`;
const Texto = styled.Text`
  color: black;
  text-align: center;
`;

function App() {
  return (
    <Geral>
      <Texto>Olá mundo</Texto>
    </Geral>
  );
}

export default App;
```
