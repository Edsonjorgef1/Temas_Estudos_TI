Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
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

React.Native, temos o "Text", ele é diferente do React.js, aqui você tem que determinar o tamanho do seu texto e também, você tem que importar o "Text"

"React.Native"
Arquivo, "App.js"

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
