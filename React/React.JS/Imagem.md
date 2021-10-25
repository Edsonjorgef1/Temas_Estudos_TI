Arquivo, App.js

Pegando a imagem dentro do nosso projeto

```js
//Importando o react
import React from "react";
import Logo from "./componentes/imgs/logo.png";

export default function App_function_Component() {
  return (
    <div className="App_function_Component">
      <img src={Logo} />
    </div>
  );
}
```

Pegando a imagem fora do nosso projeto na pasta puclic

```js
//Importando o react
import React from "react";

export default function App_function_Component() {
  return (
    <div className="App_function_Component">
      <img src="/img/logo.png" />
    </div>
  );
}
```
