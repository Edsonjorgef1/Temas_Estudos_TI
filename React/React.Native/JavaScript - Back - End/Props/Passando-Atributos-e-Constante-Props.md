Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

Arquivo, App.js

Passando atributos para a props

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
