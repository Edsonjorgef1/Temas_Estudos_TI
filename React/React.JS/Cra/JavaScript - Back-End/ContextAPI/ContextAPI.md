Arquivo, App.js

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ContextAPI

Passando informação de um componente para o outro, vamos utlizar o provider aonde vai 
armazenar as informações nele, você vai colocar ele aonde você quer passar suas informações, 
tudo aquilo que for filho de um provider você consegue acessar as informações.
Provider não é global, ele é a partir do filho.

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