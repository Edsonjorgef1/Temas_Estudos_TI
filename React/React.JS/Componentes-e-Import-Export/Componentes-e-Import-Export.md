Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Comando para criar um projeto, React.Js

```js
npx create-react-app Meu_Primeiro_Projeto
```

## Comando para criar um projeto, React.Js (Typescript)

```js
npx create-react-app (Nome do Projeto) ls
```

## Yarn ou NPM (Instalar dependências)

Você pode instalar as dependência com npm ou yarn, lembre-se se for instalar com o yarn deve instalar ele no seu computador, no site, abaixo.

```js
https://yarnpkg.com/
```

## Node_Modules

Depois que você criar seu projeto, repare que foi criado automático uma pasta
node_modules, nesta pasta vai conter suas dependências, já foi criado um projeto basico de react, de exemplo.
Exemplo, se você, instalar, o bootstrap, para o estilo do projeto ficar mais bunito, você irá,
fazer, o comando yarn add bootstrap, no terminal, ai suas dependências vai ficar instalada
dentro desta pasta, para auxiliar você no desenvolvimento, lembrando que na sua pasta package.json,
da para ver todos os nomes de suas dependências que foram instaladas, mais facil.

## Componente, Function Component, 1

Arquivo, App.js

```js
//Importando o react
import React from "react";

function App_function_Component() {
  return (
    <div className="App_function_Component">
      <h1>Componente principal</h1>
    </div>
  );
}

//Exportando Componente
export default App_function_Component;
```

## Componente, Function Component, 2

```js
import React from "react"


function App() {
   return <h1>Testando 1</h1>
}
export default App;
```

## Componente, Function Component, 3

Arquivo, App.js

```js
//Importando o react
import React from "react";

export default function App_function_Component() {
  return (
    <div className="App_function_Component">
      <h1>Componente principal</h1>
    </div>
  );
}
```
## Componente, Function Component, 4

App.js

```js
import React from "react"


let App = () => {
   return <h1>Testando 1</h1>
}
export default App;
```

## Componente, Function Component, 5

App.js

```js
import React from "react"


let App = () => <h1>Testando 1</h1>

export default App;
```

## Componente, Arrow Function

Arquivo, App.js

```js
//Importando o react
import React from "react";

const App_Arrow_Funcion = () => {
  return (
    <div className="App_Arrow_Funcion">
      <h1>Componente principal</h1>
    </div>
  );
};

//Exportando Componente
export default App_Arrow_Funcion;
```

# Componente, Class Component

Arquivo, App.js

```js
//Importando o react
import React from "react";

class App_Class_Component extends React.Component {
  render() {
    return (
      <div className="App_Class_Component">
        <h1>Componente principal</h1>
      </div>
    );
  }
}

//Exportando Componente
export default App_Class_Component;
```

## Componente, Function Component, (Typescript)

Arquivo App.tsx (Repare que aqui o arquivo diferente ele é .tsx)

```js
//Importando o react
import React from "react";

// Este React.FC, ele tipa o componente, este FC, é a abreviação do function component
const App: React.FC = () => {
  return (
    <div className="App_function_Component">
      <h1>Componente principal</h1>
    </div>
  );
};

//Exportando Componente
export default App;
```

# Exemplo de um elemento em JSX

Arquivo, App.js

```js
//Importando o react
import React from "react";

//Elemento JSX
const elemento = (
  <div>
    <h1>Elemento</h1>
  </div>
);

//Componente Function Component
function ElementoJsx() {
  return (
    <div className="ElementoJsx">
      {elemento} {/*Repare que estou pegando os dados, fora do componente*/}
    </div>
  );
}

//Exportar componente
export default ElementoJsx;
```

# Exemplo, como importar um componente, repare vou importar os componentes acima

```js
//Importando o react
import React from "react";

//Importando o componente, App_function_Component
import App_function_Component from "./App_function_Component";
//Importando o componente App_Arrow_Funcion
import App_Arrow_Funcion from "./App_Arrow_Funcion";
//Importando o componente
import App_Class_Component from "./App_Class_Component";

//Componente Function Component
function Identificacao() {
  return (
    <div className="AppIdentificacao">
      <App_function_Component />
      <App_Arrow_Funcion />
      <App_Class_Component />
    </div>
  );
}

//Exportar componente
export default Identificacao;
```
