Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Como fazer espaços entre linhas <br />

```js
import React from 'react';

export default function App() {

  return (

    <div className="App">
    Link para o site: 
    <br/>
    <a href="https://engenheiroyoutuber.com.br">Lik do site</a>
    </div>
    
  );
}
```
ou

```js
import React from 'react';

export default function App() {

let link = "https://engenheiroyoutuber.com.br"

  return (

    <div className="App">
    Link para o site: 
    <br/>
    <a href={link}>Link do site </a>
    </div>
    
  );
}
```
Eu posso adicionar uma expressão aqui dentro também se quiser, do lado do link

```js
import React from 'react';

export default function App() {

let link = "https://engenheiroyoutuber.com.br"

  return (

    <div className="App">
    Link para o site: 
    <br/>
    <a href={link}>Clique para acessar {3 + 1} vezes</a>
    </div>
    
  );
}
```