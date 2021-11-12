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