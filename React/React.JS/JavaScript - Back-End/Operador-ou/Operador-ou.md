Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Operadores logico OU, ||

```js
//Condição verdadeira
//(true && True)
//Condição verdadeira
//(false && true)
//Condição verdadeira
//(true && false)
//Condição falsa
//(false && false)

//Metodo, React.js
import React from "react"; 
let valorUm = false
let valorDois = false
let resultado = valorUm || valorDois 
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