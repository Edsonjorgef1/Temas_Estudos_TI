Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Operador-NOT=!
Invertendo o estado anterior

```js
// Operadores logico, NOT = !

//Metodo, React.js
import React from "react"; 
let valorUm = false
let valorDois = false
let resultado = valorUm || valorDois 
console.log(resultado)

let final = !resultado  ? "True" : "False"
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