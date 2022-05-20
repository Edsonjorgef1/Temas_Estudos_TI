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
  flex-direction: row; // Direção vertical, da esquerda para direita
  /* flex-direction: row-reverse; // direção vertica, da direita para esquerda */
  /* flex-direction: column-reverse; // Começa de baixo para cima, reverso, na coluna */
`;
const Quadrado = styled.View`
  flex: 1; // flex 1, ele ta dizendo que todos tem o mesmo tamanho, ou você pode derminar a largura de cada um com o width
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

## Duplicando somente o green, que ele fique o dobro e dos lados manter o mesmo tamanho, organizando verticalmente ou horizontalmente, flex combinando com o flex-direction

```js
import React from "react";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  /* flex-direction: row; */
  /*ou*/
  flex-direction: column;
`;
const Quadrado = styled.View`
  flex: ${props => props.flex};
  height: 50px;
  background-color: ${props => props.cor};
`;

function App() {
  return (
    <Page>
      <Quadrado flex={1} cor="red"></Quadrado>
      <Quadrado flex={2} cor="green"></Quadrado>
      <Quadrado flex={1} cor="blue"></Quadrado>
    </Page>
  );
}

export default App;
```

## Alinhamento horizontal ou vertical

```js
import React from "react";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  flex-direction: row; /*Aqui pode alternar para row horizontal ou column forma vertical*/
  /* justify-content: start; // Definido como padrão não vai fazer nada */
  justify-content: flex-end; /*Definido como alinhamento no fim, na parte de baixo*/
  justify-content: center; /*Centralizar no meio da tela, se o flex direction estiver em row, centraliza horizontalmente, se flex direction tiver em column centraliza verticalmente */
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

## Alinhamento e espaço entre eles iguais, space-between não tem efeito ao redor do item resumindo encosta nos cantos da tela, e o space-around que fica alinhado em todas as direções, não fica colado na tela

```js
import React from "react";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  flex-direction: row;
  justify-content: space-between;
  /*ou*/
  justify-content: space-around;
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

## Alinhamento no meio da tela, verticalmente e horizontalmente

```js
import React from "react";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  flex-direction: row; /*Aqui você coloca, centralizar horizontalmente row, verticalmente column */
  justify-content: center;
  align-items: center; /*Alinhamento no meio*/
  /* align-items: flex-end; Alinhamento no fim */
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
      <Quadrado cor="pink"></Quadrado>
    </Page>
  );
}

export default App;
```

## Destacando apenas um item do flex box

```js
import React from "react";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
`;
const Header = styled.View`
  flex-direction: row;
  justify-content: center;
  background-color: #eee;
  height: 200px;
`;
const Quadrado = styled.View`
  width: 50px;
  height: 50px;
  background-color: ${props => props.cor};
`;

function App() {
  return (
    <Page>
      <Header>
        <Quadrado cor="red"></Quadrado>
        <Quadrado style={{ alignSelf: "flex-end" }} cor="green"></Quadrado>
        {/*alignSelf vai substituir align itens do styled components  */}
        <Quadrado cor="blue"></Quadrado>
        <Quadrado cor="pink"></Quadrado>
      </Header>
    </Page>
  );
}

export default App;
```

## Caso não caber meus itens na mesma linha, pule para a linha de baixo, flex-rap

```js
import React from "react";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
`;
const Header = styled.View`
  flex-direction: row;
  /* flex-wrap: nowrap; Padrão nada acontece */
  flex-wrap: wrap; /*Possibilita os itens para quebrarem*/
  background-color: #eee;
  height: 200px;
`;
const Quadrado = styled.View`
  width: 50px;
  height: 50px;
  background-color: ${props => props.cor};
`;

function App() {
  return (
    <Page>
      <Header>
        <Quadrado cor="red"></Quadrado>
        <Quadrado cor="green"></Quadrado>
        <Quadrado cor="blue"></Quadrado>
        <Quadrado cor="pink"></Quadrado>
        <Quadrado cor="blue"></Quadrado>
        <Quadrado cor="pink"></Quadrado>
        <Quadrado cor="blue"></Quadrado>
        <Quadrado cor="pink"></Quadrado>
        <Quadrado cor="blue"></Quadrado>
        <Quadrado cor="pink"></Quadrado>
        <Quadrado cor="blue"></Quadrado>
        <Quadrado cor="pink"></Quadrado>
        <Quadrado cor="blue"></Quadrado>
        <Quadrado cor="pink"></Quadrado>
      </Header>
    </Page>
  );
}

export default App;
```
