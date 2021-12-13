Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```
## lembrete
Sempre quando for declarar o className, colocar nomes diferentes, para que não tenha problemas no futuro, exemplo, na sua pasta botao, no arquivo index.js, colocar nomes, tipo, botao-btn, para evitar conflitos no futuro, com outros componentes criados, não e para dar problema caso esteja os nomes iguais, mas, o ideal fazer deste jeito, pricipalmente quando utilizar com stylesheet.

## Estilizando o CSS, dentro de um arquivo .CSS, Stylesheet (Projeto básico do React, após criado o projeto, 1 Opção)
Repare estou importando, o nome do arquivo

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

## Estilizando o CSS, dentro de um arquivo .CSS, Stylesheet (Projeto básico do React, após criado o projeto, 1.1 Opção)

Repare estou importando, o nome da pasta agora, muito melhor mais organizado

Para você importar, somente a pasta, você deve, deixar o aquivo dentro de botão, index.js e styles.js, assim quando importar o Botao, o react vai reconhecer.

App.js

```js
import React from "react";
import Botao from "./components/Botao"

const App = () => {
  return (
    <div className="Nome1">
      < Botao />
    </div>
  );
};

export default App;
```
components/Botao/index.js

```js
import React from "react";
import './styles.css'

const App = () => {
  return (
    <div className="Nome1">
    <h1>Ola Mundo</h1>
    </div>
  );
};

export default App;
```

components/Botao/styles.js

```js

.Nome1 {
background-color: #f8f9fa;
}

.Nome1 h1 {
font-size: 32px;
color: #e03030;


}
```

## Estilizando o CSS, dentro de um arquivo .JS Estilo inline (Projeto básico do React, após criado o projeto, 2 Opção)

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
Site descrição:
styled-components.com

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

Porque utilizar o css-modules ao inves do stylesheet, porque no css-modules, ele cria um numero, por tras dos panos, quando você faz o className, assim nunca vai dar conflito o nome caso você esquecer e deixar igual, imagina um projeto, grande, é dificil de você ficar monitorando se contém algum nome igual, em varios componentes criados, uma otima opção esta aqui.

App.js

```js
import React from "react";
import Botao from "./components/Botao"

const App = () => {
  return (
    <div className="Nome1">
      < Botao />
    </div>
  );
};

export default App;
```
components/Botao/index.js

```js
import React from "react";
import './styles.module.css'

const App = () => {
  return (
    <div className={styles.geral}>
    <h1 className={syles.h1}>Ola Mundo</h1>
    </div>
  );
};

export default App;
```

components/Botao/styles.module.css

```js

.Geral{
background-Color: white
}

.Nome1 {
background-color: #f8f9fa;
}

.Nome1 h1 {
font-size: 32px;
color: #e03030;
}
```


## Estilizando o css, Sass

Como Usar SCSS Com React
Você utiliza Sass ou Scss para construir seu CSS e está criando um aplicação em React mas não sabe como utilizar ele?
Usar o Sass dentro do React é muito simples e fácil de ser configurado!

Para isso, em seu terminal instale o sass:

```js
npm install node-sass

// Ou utlizando yarn

yarn add node-sass
```

Pronto, agora você já está apto a utilizar arquivos Sass dentro do seu projeto!
Mas como podemos importar os estilos? Da mesma maneira que fazemos com o CSS tradicional.
Este exemplo é muito legal, imagina que você tem 50 titulos, todos iguais e depois você gostaria de trocar a cor de todos os textos, se não fosse o Sass, você ia ter que trocar um por um, agora com o Sass, basta trocar a cor uma vez só no .scss, lembrando que isso é apenas uma funcionalidade do Sass mas tem outras vantagens também.

Criamos um arquivo .scss, nesse caso, chamaremos de estilo.scss:

```js
$color: #000;

h1 {
  color: $color;
}
h2 {
  color: $color;
}
```

E dentro do nosso arquivo js, importamos nosso estilo:

```js
//Importando o react
import React from "react";

function App() {
  return (
    <div className="App">
      <h1>Titulo 1</h1>
      <h1>Titulo 2</h1>
    </div>
  );
}

//Exportando Componente
export default App;
```

Aqui neste site, tem mais exemplos como utilizar o Sass

```js
https://www.w3schools.com/sass/default.php
```

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

Repositorio, Rebass:

```js
https://github.com/orgs/rebassjs/repositories
```

Siglas, tradução:

```js
m: margin
mt: margin-top
mr: margin-right
mb: margin-bottom
ml: margin-left
mx: margin-left and margin-right
my: margin-top and margin-bottom
p : padding
pt: padding-top
pr: padding-right
pb: padding-bottom
pl: padding-left
px: padding-left and padding-right
py: padding-top and padding-bottom
```

## Estilizando o Css, react-spring (Animation)

Muito top está biblioteca

site:

```js
https://react-spring.io/hooks/use-spring
```

Comando:

```js
yarn add react-spring
```

## Estilizando o Css, boostrap

### Estilizando o Css, boostrap (1 Opção)

Para este modelo aqui, depois que você fizer o comando abaixo, vai ser instalada uma dependência dentro da pasta node_modules, para você importar o que foi instalado, com o comando abaixo, você vai importar a dependência, direto da pasta node_modules, exemplo:
Depois, você já pode usar o boostrap, muito facil.

```js
import React from "react";
import "bootstrap/dist/css/bootstrap.min.css";

function App() {
  return <div className="App"></div>;
}

export default App;
```

Comando para instalar o boostrap, digite no terminal:

```js
npm install bootstrap --save
```

ou

```js
yarn add bootstrap
```

### Estilizando o Css, boostrap (2 Opção)

Você também pode copiar o link, CSS

Site, Link

```js
https://getbootstrap.com/docs/5.1/getting-started/introduction/
```

React.js, copiar o link, dentro da pasta "public" depois entrar no arquivo "index.html'

Copie e cole a folha de estilo <link> dentro do <head> para carregar o CSS, com o bootstrap.

```js
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
```

Site:

```js
https://getbootstrap.com/
```

Arquivo index.html

```js
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <meta
      name="description"
      content="Web site created using create-react-app"
    />
    <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
    <!--
      Repare que eu copiei o link do boostrap, aqui dentro do head, esta aqui abaixo.
    -->

    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">

    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />

    <title>React App</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>

  </body>
</html>
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

## Estilizando o Css, devtools

Site:

```js
https://react-hook-form.com/pt/dev-tools/
```

## Metodo para estilizar o css, estilos Inline

```js
import React from "react";

let estilo = {
  color: "red",
  fontSize: "2em",
  border: "1px solid red",
};

function App_function_Component() {
  return (
    <div className="App_function_Component">
      <p style={estilo}>Estilos Inline</p>
    </div>
  );
}
export default App_function_Component;
```
## Quando clicar, gostaria de fazer alguma coisa no CSS

App.js

```js
import { useState } from "react";


const App = () => {
  const [padding, setPadding] = useState(0)

  const handleClick = () => {
  setPadding(20)
  }
    
  return (
    <div>
    <button 
    onClick={handleClick}
    style={{ padding}}
    
    >clique</button>
    </div>
  );
};

export default App;
```

## Adicionando um operador ternario, com estilo inline

```js
import { useState } from "react";


const App = () => {
  const [cor, setCor] = useState(0)

  const handleClick = () => {
  setCor(true)
  }
    
  return (
    <div>
    <button 
    onClick={handleClick}
    style={{backgroundColor: cor ? '#0000FF' : '#FF0000'}}
    
    >clique</button>
    </div>
  );
};

export default App;
```