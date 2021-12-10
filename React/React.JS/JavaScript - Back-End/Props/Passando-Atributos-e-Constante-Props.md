Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## 1 Exemplo: (CRA)

Arquivo, Dados.js

Passando conteúdo de uma constante

```js
//Importando o react
import React from "react";
import Dados from "./componentes/Dados";

export default function App() {
  const cnl = "Engenheiro Youtuber";
  const yt = "youtube.com/engenheiroyoutuber";
  const crs = "React.js";

  return (
    <div className="App">
      <section>
        <Dados canal={cnl} youtube={yt} curso={crs} />
      </section>
    </div>
  );
}
```

Arquivo, App.js

Passando atributos para a props

```js
//Importando o react
import React from "react";

export default function Dados(props) {
  // Este (props), aqui desta linha tem que ir para, poder passar atributos para o componente
  return (
    <div className="App">
      <section>
        <p> Canal:{props.canal} </p>
        <p> Youtube: {props.youtube} </p>
        <p> Curso: {props.curso} </p>
      </section>
    </div>
  );
}
```

## 2 Exemplo: (CRA)

Função que depende das propriedades, retornando um elemento qualquer
valor enviado via props

```js
//Importando o react
import React from "react";

//Função que depende das propriedades, retornando um elemento qualquer
//valor enviado via props
const Display = (props) => {
  return <h1>{props.title}</h1>;
};

function App_function_Component() {
  return (
    <div className="App_function_Component">
      <h1>Componente principal</h1>
      <Display title="teste" />
    </div>
  );
}
//Exportando Componente
export default App_function_Component;
```

## 3 Props, typeScript (vite)

Neste exemplo foi utilizado o Vite
Repare que neste exemplo, eu posso somente passar, o title.

App.tsx

```js
import { Header } from './Components/Header2'

export default function App() {

  return (

    <div className="App">
    <Header title="Este é um exemplo"/>
     {/*Para adicionar, <Header /> sem o title, deve adicionar um ?, no arquivo, Components/Header.tsx, para o metodo CRA, não precisa colocar a interrogação*/}

     Olá Mundo
  
    </div>
    
  );
}
```
Components/Header.tsx

```js
type Props = {
  title: String;  // title?: String; desta forma voçê poderá receber um nome diferente sem ser o title.
}

export const Header = (props: Props) => {
  return (
  <header>
  <h1> {props.title}</h1>
  <hr/>
  </header>
  );
}
```
Components/Header.tsx (Forma resumida)

```js
type Props = {
  title: String;
}

export const Header = ({ title }: Props) => {
  return (
  <header>
  <h1> {title}</h1>
  <hr/>
  </header>
  );
}
```

## 4 Exemplo: Neste exemplo vamos fazer, o exemplo 3 só que sem type script, metodo (CRA)

App.js

```js
import { Header } from './Components/Header'

export default function App() {

  return (

    <div className="App">
    <Header title="Este é um exemplo"/>

     Olá Mundo
  
    </div>
    
  );
}
```

Components/Header.js

```js
import React from 'react';

export const Header = (props) => {
  return (
  <header>
  <h1> {props.title}</h1>
  <hr/>
  </header>
  );
}
```

## 5 Enviando Imagem e Leganda via Props, Type script (vite)
Desta forma eu posso retornar somente um elemento, porque está dentro de uma div

App.tsx

```js
import { Header } from './components/Header2'
import { Photo } from './components/Photo'

export default function App() {

  return (

    <div className="App">
    <Header title="Este é um exemplo"/>
    <Header title="Este é um exemplo"/>
     
     Olá Mundo
     <Photo url="http://www.google.com.br/google.jpg" legend="Google" />
    </div>
    
  );
}
```
compoments/Photo

```js
type Props = {
url: string;
legend: string;
}

export const Photo = ({ url, legend }: Props) => {
return (
<div>
    <img src={url}/>
   <p>{legend}</p>
</div>
)
}
```
components/Header

```js
type Props = {
  title: String;
}

export const Header = ({ title }: Props) => {
  return (
  <header>
  <h1> {title}</h1>
  <hr/>
  </header>
  );
}

```

## Props, chamada Children, passando imagem e legenda em Type Script (vite)

App.tsx

```js
const App = () => {

  return (

    <div className="App">

    <Header title="Este é um exemplo"/>
    <Header title="Este é um exemplo"/>
     
     Olá Mundo

     <Photo legend= "Google">
     <img src="http://www.google.com.br/google.jpg" alt="" /> 
     </Photo>
    
     
    </div>
  );
}

export default App;
```

compoments/Photo

```js
import { ReactNode } from 'react'

type Props = {
legend: string;
children: ReactNode;
}

export const Photo = ({ legend, children }: Props) => {
return (
<>
   {children}
   <p>{legend}</p>
</>
)
}
```