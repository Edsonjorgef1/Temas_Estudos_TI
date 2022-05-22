Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Organização Componentes

Lembre-se que sempre é bom separar os componentes, da melhor forma possivel e
menores, para ficar melhor para a manutenção dos códigos no futuro e tambem fica
melhor a visualização, para saber o que está acontecendo.

Exemplo:

Aqui vou criar uma pasta src, aonde ficará todos os nossos códigos do aplicativo
e dentro vou criar uma pasta chamada components e dentro um arquivo chamado
Header.js aonde irá ficar a parte superior do meu aplicativo.

src/components/header.js

```js
import React from "react";
import styled from "styled-components/native";

const Header = styled.View`
  width: 100%;
  height: 80px;
  background-color: #ccc;
  justify-content: center;
  align-items: center;
`;
const HeaderText = styled.Text`
  color: blue;
`;

export default () => {
  return (
    <Header>
      <HeaderText>Texto Qualquer</HeaderText>
    </Header>
  );
};
```

//Repare que este componente header.js eu posso reutilizar ele depois se eu
quiser

App.js

```js
import React, { useEffect } from "react";
import styled from "styled-components/native";
import Header from "./src/components/Header";

const Page = styled.SafeAreaView`
  flex: 1;
`;

function App() {
  return (
    <Page>
      <Header />
      {/*Aqui você pode organizar o restante do 
      seu aplicativo, importando outros componentes, 
      aqui será uma visão geral, de todos criados*/}
    </Page>
  );
}

export default App;
```
