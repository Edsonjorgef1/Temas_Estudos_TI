
Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Fragment 
Ele serve para você, retornar um elemento quando você, 
precisar por exemplo retornar só um elemento, passando via props.
Você pode importar o Fragment e no lugar da div adicionar Fragment ou utilizar <> </> no lugar da div

## Exemplo Metodo type Script (Vite)

compoments/Photo.tsx

```js
import { Fragment } from 'react';

type Props = {
url: string;
legend: string;
}

export const Photo = ({ url, legend }: Props) => {
return (
<Fragment>
    <img src={url}/>
   <p>{legend}</p>
</Fragment>
)
}
```
ou

compoments/Photo.tsx

```js

type Props = {
url: string;
legend: string;
}

export const Photo = ({ url, legend }: Props) => {
return (
<>
    <img src={url}/>
   <p>{legend}</p>
</>
)
}
```


App.tsx

```js
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

compoments/Header.tsx

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