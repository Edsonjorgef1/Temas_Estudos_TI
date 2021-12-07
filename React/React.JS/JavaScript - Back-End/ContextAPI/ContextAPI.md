Arquivo, App.js

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ContextAPI

Passando informação de um componente para o outro, vamos utlizar o provider aonde vai 
armazenar as informações nele, você vai colocar ele aonde você quer passar suas informações, 
tudo aquilo que for filho de um provider você consegue acessar as informações e tem os consumer que são quem vai consumir estas informações, tudo o que for consumer consegue acessar uma informação do provider, lembrando que ele deve estar abaixo ou dentro deste provider na arvore de componentes.
Digamos que você tem um formulario de usuarios que você tem a sua barrinha de navegação la em cima que tem o nome do seu usuario imagina que você salvo e atualizo seu nome no formularios de usuarios e você quer replicar esta infomação, ai você utiliza o provider.

### Replicando, o nome Engenheiro youtuber

```js
import React, { createContext, useContext } from 'react';
import './App.css';

const ValueContext = createContext();


const Other1 = () => {
const value = useContext(ValueContext)
return <div>Valor1: {value} </div>;
};

const Other2 = () => {
  const value = useContext(ValueContext)
  return <div>Valor2: {value} </div>;
  };


export default function App() {
  const value = "Engenheiro Youtuber";
  return (
    
    <ValueContext.Provider value={value}>

    <div className="App">
    <Other1 />
    <Other2 />
    </div>
    </ValueContext.Provider>
 
  );
}
```