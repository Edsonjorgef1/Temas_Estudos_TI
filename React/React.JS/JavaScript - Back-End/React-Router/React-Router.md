Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## React-Router

Para instalar a biblioteca

```js
yarn add react-router-dom
```

ou

```js
npm install react-router-dom
```

## Primeiro passo, importar o react-router-dom

index.js

```js
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import { BrowserRouter } from 'react-router-dom'


ReactDOM.render(
  <React.StrictMode>
  <BrowserRouter>
  <App />
  </BrowserRouter>
  </React.StrictMode>,
  document.getElementById('root')
);
```

Como eu coloquei o App, dentro de BrowserRouter, agora toda minha 
aplicação vai ter suporte a rotas

## Clicando e indo para outra tela, sem renderizar toda a tela

index.js

```js
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import { BrowserRouter } from 'react-router-dom'


ReactDOM.render(
  <React.StrictMode>
  <BrowserRouter>
  <App />
  </BrowserRouter>
  </React.StrictMode>,
  document.getElementById('root')
);

```

App.js

```js
import React from "react";
import { Routes, Route } from "react-router-dom";
import { Home } from "./pages/Home";
import { About } from "./pages/About";
import { AboutBeto } from "./pages/AboutBeto";
import { AboutMarlene } from "./pages/AboutMarlene";
import { NotFound } from "./pages/NotFound";

import styled from "styled-components";

const Pagina = styled.h1`
  padding: 10px;
  color: blue;
`;

function App() {
  return (
    <div>
      <header>
        <h1>Titulo do site</h1>
      </header>
      <hr />

      <Pagina className="Pagina">

      {/*Configurando rotas*/}
      <Routes>
       <Route path="/" element={<Home />} />
       <Route path="/sobre" element={<About />} />
       <Route path="/sobre/beto" element={<AboutBeto />} />
       <Route path="/sobre/marlene" element={<AboutMarlene />} />
       {/*Caso a rota não existir, aparecer esta página*/}
       <Route path="*" element={<NotFound />} />
      </Routes>

      </Pagina>
      <hr />

      <footer>Todos os direitos reservados</footer>
    </div>
  );
}
export default App;
```
pages/About.js

```js
import React from 'react';
//Este Link, ele deicha renderiza somente, a tela que foi clicada
import { Link } from 'react-router-dom'

export const About = () => {
    return (
    <div>
    Página Sobre:
    <ul>
    <li><Link to="/sobre/beto">Beto</Link></li>
    <li><Link to="/sobre/marlene">Marlene</Link></li>
    </ul>
    </div>
    )
}
```

pages/AboutBeto.js

```js
import React from 'react';

export const AboutBeto = () => {
    return (
    <div>
    Página sobre Beto
    </div>
    )
}
```

pages/AboutMarlene.js

```js
import React from 'react';

export const AboutMarlene = () => {
    return (
    <div>
    Página sobre Marlene
    </div>
    )
}
```

pages/Home.js

```js
import React from 'react';

export const Home = () => {
    return (
    <div>
    Página Home
    </div>
    )
}
```

pages/NotFound.js

```js
import React from 'react';

export const NotFound = () => {
    return (
    <div>
    Página não encontrada!!!
    </div>
    )
}
```



