Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Flex-Box

```js
import React from "react";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  /*flex-direction: column; // Direção coluna, não vai fazer nada */
  /*flex-direction: row; // Direção vertical*/
  flex-direction: column-reverse; // ele inverte, fica na parte de baixo, começando de baixo para cima
`;
const Quadrado = styled.View`
  width: 50px;
  height: 50px;
  background-color: ${props => props.cor};
`;

function App() {
  return (
    <Page>
      <Quadrado cor="red"></Quadrado>
      <Quadrado cor="green"></Quadrado>
      <Quadrado cor="blue"></Quadrado>
    </Page>
  );
}

export default App;
```
