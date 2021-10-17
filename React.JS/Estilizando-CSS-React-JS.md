## Estilizando o CSS, dentro de um arquivo .CSS (Projeto básico do React, após criado o projeto, 1 Opção)

Arquivo App.js

```js
import React from "react";
import "./App.css";

const App = () => {
  return (
    <div className="Nome1">
      <h1>Descrição 1</h1>
      <h2>Descrição 2</h2>
    </div>
  );
};

export default App;
```

O nome deste aquivo é App.css

```js
//Estilizando o CSS, Geral
.Nome1 {
background-color: #f8f9fa;
}

// Estilizando o css, somente no H1
.Nome1 h1 {
font-size: 32px;
color: #525252;

// Estilizando o css, somente no H2
.Nome1 h2 {
font-size: 32px;
color: #525252;
```

## Estilizando o CSS, dentro de um arquivo .CSS (Projeto básico do React, após criado o projeto, 2 Opção)

Adiconei este comando abaixo, em h1 e h2, olha que facil.

```js
style={{ fontWeight: "100", color: "#919191", fontSize: "14px" }}
```

Adicionei este comando na div.

```js
style={{height:"50px",display:'flex',width:'100%',justifyContent:'space-between', alignItems:'center'}}
```

Vou estilizar o css, direto neste aquivo aqui, App.js.

```js
import React from "react";
import "./App.css";

const App = () => {
  return (
    <div
      style={{
        height: "50px",
        display: "flex",
        width: "100%",
        justifyContent: "space-between",
        alignItems: "center",
      }}
    >
      <h1 style={{ fontWeight: "100", color: "#919191", fontSize: "14px" }}>
        Descrição 1
      </h1>
      <h2 style={{ fontWeight: "100", color: "#919191", fontSize: "14px" }}>
        Descrição 2
      </h2>
    </div>
  );
};

export default App;
```

## Estilizando o CSS, dentro de um arquivo .CSS (Projeto básico do React, após criado o projeto, 3 Opção)

Olha que facil adicionei no div, este comando

```js
style = { div };
```

Adicionei no h1, este comando

```js
style = { h1 };
```

Adicionei no h2, este comando

```js
style = { h2 };
```

```js
import React from "react";

const div = {
  minHeight: "500px",
};
const h1 = {
  backgroundColor: "black",
  color: "blue",
};
const h2 = {
  backgroundColor: "black",
  color: "white",
};

function App() {
  return (
    <div style={div}>
      <h1 style={h1}>olá 1</h1>
      <h2 style={h2}>Ola 2</h2>
    </div>
  );
}

export default App;
```

## Estilizando o Css, dentro de um arquivo, JavaScript (1 Opção)

Observação:
Para quem instalar está extenção, com ela você consegue estilizar o css do seu projeto, dentro de um aquivo javascript, muito utilizado nas empresas hoje em dia.

Comando para instalar o Styled-Component

```js
yarn add styled-components
```

Arquivo App.js

```js
import React from "react";

import { Title } from "./style";
import { Paragrafo } from "./style";
import { Botao } from "./style";
import { Container } from "./style";

function App() {
  return (
    <div>
      <Container>
        <Title>
          Hello Word
          <span>Texto menor</span>
        </Title>
        <Paragrafo>Oi Beto</Paragrafo>
        <Botao>Teste</Botao>
      </Container>
    </div>
  );
}

export default App;
```

Arquivo style.js

```js
import styled, { css } from "styled-components";

export const Container = styled.div`
  text-align: center;
  background-color: yellow;
`;

export const Title = styled.h1`
  color: black;

  span {
    font-size: 12px;
  }
`;

export const Paragrafo = styled.p`
  color: green;
`;

export const Botao = styled.button`
  background: transparent;
  border-radius: 3px;
  border: 2px solid palevioletred;
  color: red;
  margin: 0 1em;
  padding: 0.25em 1em;
`;
```

## Estilizando o Css, dentro de um arquivo, JavaScript (2 Opção)

Arquivo App.js

```js
import React from "react";

import * as St from "./style";

function App() {
  return (
    <div>
      <St.Title>Hello Word</St.Title>
      <St.Paragrafo>Oi Beto</St.Paragrafo>
      <St.Botao>Teste</St.Botao>
    </div>
  );
}

export default App;
```

Arquivo style.js

```js
import styled, { css } from "styled-components";

export const Title = styled.h1`
  color: black;

  span {
    font-size: 12px;
  }
`;

export const Paragrafo = styled.p`
  color: green;
`;

export const Botao = styled.button`
  background: transparent;
  border-radius: 3px;
  border: 2px solid palevioletred;
  color: red;
  margin: 0 1em;
  padding: 0.25em 1em;
`;
```

## Estilizando o Css, dentro de um arquivo, JavaScript (3 Opção)

Arquivo App.js

```js
import React from "react";
import styled from "styled-components";

const Geral = styled.div`
  background-color: black;

  h1 {
    color: white;
  }
  h2 {
    color: blue;
  }
`;

function App() {
  return (
    <Geral>
      <h1>olá 1</h1>
      <h2>Ola 2</h2>
    </Geral>
  );
}

export default App;
```

## Estilizando o css, css-modules

...

## Estilizando o css, Sass

...

## Estilizando o css, Less

...

## Estilizando o Css, tailwindcss

Site:

```js
https://tailwindcss.com/docs/font-size
```

## Estilizando o Css, rebass

Site:

```js
https://rebassjs.org/
```

## Estilizando o Css, boostrap

Site:

```js
https://getbootstrap.com/
```

## Estilizando o Css, reacstrap

Site:

```js
https://reactstrap.github.io/
```

## Estilizando o Css, react-bootstrap

Site:

```js
https://react-bootstrap.github.io/
```
