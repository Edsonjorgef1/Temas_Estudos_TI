Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
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

## Componente, Arrow Function, 1

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
## Componente, Arrow Function, resumido 2

App.js

```js
import React from "react"

const App = () => <h1>Testando 1</h1>

export default App;
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

## Maneiras para navegar entre pastas

src/App.js

Aqui estou importando, a pasta home

```js
import React from "react";
import Home from "./view/home"

function App() {
  
  return (
    <div>
    <Home/>
    </div>
  );
}

export default App
```

src/view/home/index.js
Repare que aqui, coloquei o index.js, assim, que importar a pasta home ele ja entende o index.js

```js
import React from "react";
import './styles.css'

const Home = () => {
  return (
    <div className="Geral">
    <div className="Header">
    <h1>Home</h1>
    </div>
    </div>
  );
};

export default Home;
```

src/view/home/styles.css

/*styles Css*/

```js

```

## Metodo prodissional, para não quebrar a aplicação, caso tenha que remover alguma pasta

link, para visualizar o video, recomendado

```js
https://www.youtube.com/watch?v=lAV1-19hHqw
```
Para evitar navegando entre pastas, com ./, ../

yarn add react-app-rewired

Na pasta src, criar um arquivo, config-overrides.js
ele vai substituir algumas configuração do babel

Agora vamos instalar um plugin, yarn add babel-plugin-root-import --dev
(--dev), está instalando como uma dependencia de desenvolvimento