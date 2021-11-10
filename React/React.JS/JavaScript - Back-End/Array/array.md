## Array

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

```js
//Metodo, React.js
import React from "react"; 

let numeros = [10,20,30,40,50] 
let nomes = ['Beto', 'Fabio', 'Elio', 'Valdir', 'Ingrid']

console.log(nomes) 

function ElementoJsx() {   
  return (
    <div>

      <h1>Quantidade total de Números</h1>
      {numeros.length} 
      
      <h1>Número selecionado</h1>
      {numeros[0]} 
      
      <h1>Quantidade Total dos nomes</h1>
      {nomes.length} 
     
      <h1>Nome Selecionado</h1>
      {nomes[0]} 

    </div>
  );
}

export default ElementoJsx;  
```