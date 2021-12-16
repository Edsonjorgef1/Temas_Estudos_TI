Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

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

## Passando imagem ou atribudos para uma div

```js
function App() {
let imagem = 'https://www.google.com.br/google.jpg'

return <>
<img src={imagem} />
</>
}

export default App
```

## Imagem e props, 1

App.js

```js
import React from 'react'

function Avatar(props) {
return (
<div>
<img src={props.url} alt={props.name} />
<br/>
<span>{props.name}</span>
</div>
)
}

function App() {
let user = {
  url: "https://www.google.com.br/google.jpg",
  name:"Beto"
}
return <>
<Avatar url={user.url} name={user.name}/>
</>
}
export default App
```

## Imagem e props, resumido 2

App.js

```js

import React, { useRef } from 'react'

function Avatar(props) {
return (
<div>
<img src={props.user.url} alt={props.user.name} />
<br/>
<span>{props.user.name}</span>
</div>
)
}

function App() {
let user = {
  url: "https://www.google.com.br/google.jpg",
  name:"Beto"
}
return <>
<Avatar user={user}/>
</>
}
export default App
```