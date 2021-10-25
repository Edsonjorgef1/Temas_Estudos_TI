Inscrevam-se: Canal, Engenheiro Youtuber

https://www.youtube.com/engenheiroyoutuber

## React.Js "div" "H1" X React.Native "View" "Text"

Este exemplo, vai ser bem legal, vamos abordar,
como fazer o projeto em React.js e React.Native a mesma coisa,
para ver qual a diferença de um projeto React.Js (Web) e React.Native
(Aplicativo).
Para fazer esta pasta aqui, você deve ver, primeiro a pasta,"Estilizando-CSS-React-Native.md" e também "Estilizando-CSS-React-JS.md" e também deve aprender a pasta, "Componentes.md", para você aprender está pasta.

## Instalar, Node

```js
https://nodejs.org/en/download/
```

## Instalar o VsCode

```js
https://code.visualstudio.com/download
```

## Criando o projeto em React.js

Aqui para rodar o projeto depois de pronto, comando: "yarn start", você digita no terminar do vscode ou gitbast ou o terminal que você achar mais atraente para você.
Vai criar uma estrutura de um projeto pronto para você, depois só aterar como desejar.

```js
npx create-react-app "Nomedoseuprojeto"
```

## Criando o projeto em React.Native

Vai criar uma estrutura de um projeto pronto para você, depois só aterar como desejar.

```js
npx create-react-app "Nomedoseuprojeto"
```

## Introdução

Vamos utilizar o Método Hooks, para os dois projetos, porque ele é
um componente Function Component ou poderia ser Arrow Function também, agora se fosse um componente Class Component, ai seria um componente de class, não seria mais um componente de Hooks, só para se abtuar no mundo da programação.
Lembrando, para estilizar o projeto em React.Js ou React.Native,
já contém uma pasta explicando os métodos disponível.
Repare que no projeto React.Js, Temos uma Div, que está dentro de um componente Function component, dentro desta div, será aonde vai ficar o JSX.
Jsx ele fica dentro de uma div, para ele funcionar, você deve importar o React, igual este comando abaixo:

```js
import React from "react";
```

Depois que você importar o react, igual o exemplo acima, servindo para React.js e React.Native, no seu código, o babel que é o processador do javascript vai começar a entender o JSX, dentro de uma div, que será aonde vamos fazer a estrutura do nosso código aonde podemos, escrever um código em html, dentro de um arquivo Javascript e também estilizar um CSS dentro de um arquivo javascript, lembrando que você não vai ver este código, que o babel está imterpretando por trás, do nosso código.

## React.Js "div" "H1" X React.Native "View" "Text"

### React.Js "div" "H1"

React.js, temos que importar o React, para que possa funcionar o Jsx dentro do componente.
Exemplo abaixo:

```js
import React from "react";
```

React.js, tempos o "Div" dentro da div fica o Jsx.

```js
<div>
  Aqui vai conter o JSX, vamos ver mas para frente como vai ficar este lugar
  aqui.
</div>
```

React.Js, temos o "H1", ele é o tamanho da seu texto, ele é o maior texto, exemplo abaixo:

```js
<h1>Cabeçalho nível 1</h1>
<h2>Cabeçalho nível 2</h2>
<h3>Cabeçalho nível 3</h3>
<h4>Cabeçalho nível 4</h4>
<h5>Cabeçalho nível 5</h5>
<h6>Cabeçalho nível 6</h6>
```

React.js - Arquivo, "App.js"
Neste exemplo abaixo, utilizamos o styled-components, para
isso você deve instalar a biblioteca, utilizando o comando abaixo:
Lembrando, não vou entrar em, detalhes aqui, pois na outra pasta,
que citei acima, é o requesito para fazer este exemplo aqui, instalar o yarn, agora se for instalar com o npm, não precisa instalar o yarn.

```js
yarn add styled-components
ou
npm install --save styled-components
```

```js
import React from "react"; // importando o React
import styled from "styled-components"; // Importando o styled components

{
  /*Estilizando CSS*/
}
const Geral = styled.div`
  background-color: black;
  h1 {
    color: white;
  }
  h2 {
    color: blue;
  }
`;

//Componente Function Componente
function App() {
  return (
    <Geral>
      {/*Aqui dentro JSX, ja está funcionando agora, porque importamos o react*/}
      <h1>olá 1</h1>
      <h2>Ola 2</h2>
    </Geral>
  );
}

export default App; // Exportando o componente, para que você possa reutilizar ele depois em outros lugares, o nome deste componente é App
```

### React.Native "View" "Text"

Aqui para rodar o projeto depois de pronto, comando: "expo start", você digita no terminar do vscode ou gitbast ou o terminal que você achar mais atraente para você.
Vai criar uma estrutura de um projeto pronto para você, depois só aterar como desejar.
Vamos utilizar o expo, pois e mais leve para simular os projetinhos, mas você pode instalar o android studio também, mas ele é um pouco pesado e você tem que ter um computador um pouco melhor, fica a seu gosto e também qual a condição você está hoje para pode emular o seu aplicativo, se o seu computador é bom ou não

Aqui você também, tem que importar o React, igual o React.Js, igual foi explicado acima, anteriormente.

```js
import React from "react";
```

React.Native, tempo o View, ele é igual a div, do React.Js, só que aqui, você tem que importar o "View" para que ele possa funcionar.

```js
import { View } from "react-native";
```

React.Native, temos o "Text", ele é diferente do React.js, aqui você tem que determinar o tamanho do seu texto e também, você tem que importar o "Text"

```js
import { Text } from "react-native";
```

React.Native - Arquivo, "App.js"
Neste exemplo abaixo, utilizamos o StyleSheet, para estilizar
o css, desta forma temos que importar ele.

```js
import { StyleSheet } from "react-native";
```

Agora vamos importar os três

```js
import { StyleSheet, View, Text } from "react-native";
```

Você deve estar perguntando, eu tenho que fazer desta forma, logico que não na pasta (Estilizando-CSS-React-Native.md) você vai encontrar outros metodos para estilizar, estou mostrando assim, mas poderia ser de outras formas também, leia esta pasta que citei acima, dentro da pasta React.Native.

"React.Native"
Arquivo, "App.js"

```js
import React from "react";
import { StyleSheet, Text, View } from "react-native";

function App() {
  return (
    <View style={styles.container}>
      <Text style={styles.logo}>Engenheiro Youtuber</Text>
    </View>
  );
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

//Exportando Componente
export default App;
```
