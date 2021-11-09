Inscrevam-se: Canal, Engenheiro Youtuber

https://www.youtube.com/engenheiroyoutuber

## Componente, Function Component

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
