Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Operadores Igualdade
```js
// Operadores Igualdade
// === compara o valor e o tipo
// (1 === 1 ) True, ('1' === 1) False

//Metodo, React.js
import React from "react"; 

let valorUm = '3'
let valorDois = 3

let resultado = valorUm === valorDois
console.log(resultado)

let final = resultado  ? "True" : "False"

function ElementoJsx() {   
  return (
    <div>
      <div>
      {final}
      </div>
    </div>
  );
}

export default ElementoJsx;  
```