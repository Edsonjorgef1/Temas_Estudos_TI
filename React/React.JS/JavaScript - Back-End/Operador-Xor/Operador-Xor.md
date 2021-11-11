Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Operador-Xor

Diferente = true
Igual = false

```js

// Operadores logico, Xor = ^

//Valores igual, false, valores diferente, true
// Operadores logico E, &&
//Condição false
//(true && True)
//Condição true
//(false && true)
//Condição true
//(true && false)
//Condição falsa
//(false && false)
//Metodo, React.js
import React from "react"; 
let valorUm = true
let valorDois = false
let resultado = valorUm ^ valorDois 
console.log(resultado)

let final = resultado  ? "True" : "False"
console.log(final)

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