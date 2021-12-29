Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Map (1)

Este exemplo é bem legal, digamos que você tem varias pessoas em um array e
você quer dar bom dia, para cada pessoa

```js
import React from "react"; 

let nomes = ['Elio', 'Valdir', 'Fabio']
console.log(nomes)

let final = nomes.map(n => 'Bom dia' + n)
console.log(final)

function ElementoJsx() {   
  return (
    <div>
    <br/>
     {nomes}
     <br/>
     {final}
    </div>
  );
}

export default ElementoJsx; 
```

## Map (2)
Utilizando o map com template string

```js
import React from "react"; 
  let pessoas = [ 
    {
    nome:"Beto",
    profissao: "Engenheiro"
    },
    {
      nome:"Valdir",
      profissao: "Eletricista"
    },
    {
      nome:"Elio",
      profissao: "Programador"
    },
    ]
    const final = pessoas.map(pessoa => `${pessoa.nome} exerce a profissão de ${pessoa.profissao}`)

    function App_function_Component() {
  return (
    <div className="App_function_Component">
      {final}
    </div>
  );
}
export default App_function_Component;
```

## Renderização de listas

App.js

```js
import React from "react";
import { Pessoa } from "./components/Pessoa"


let list = [
  {name: 'Bonieky', age:'90'},
  {name: 'Beto', age:'80'}
]


const App = () => {
return (
  <div>
<h2>lista de presença</h2>
<ul>
{list.map((item, index)=>(    // index, serve para referencia o numero de cada nome, para não dar erro
// <li key={index}>{item.name.toUpperCase()} - {item.age} anos</li> este foi o teste anteriormente sem o outro arquivo pessoas
<Pessoa key={index} data={item}/>
))}

</ul>

  </div>
)
}

export default App
```

components/Pessoa.js

```js
import React from "react";


export const Pessoa = ({data}) => {
return (
    <li>
    {data.name} - {data.age} anos.
    </li>
)
}
```