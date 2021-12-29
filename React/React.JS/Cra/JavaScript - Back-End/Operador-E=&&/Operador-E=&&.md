Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Operador E = &&
```js
// Operadores logico E, &&
//Condição verdadeira
//(true && True)
//Condição falsa
//(false && true)
//Condição false
//(true && false)
//Condição falsa
//(false && false)

//Metodo, React.js
import React from "react"; 
let valorUm = true
let valorDois = true
let resultado = valorUm && valorDois 
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