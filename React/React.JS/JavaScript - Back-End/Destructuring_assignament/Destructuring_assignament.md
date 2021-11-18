Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Destructuring_assignament

Atribuição destriturada

```js
//Metodo, React.js
import React from "react";

let numeros = [1, 2];
/*
//Este exemplo, é um metodo mais antigo
console.log(numeros)
const num1 = [0]
console.log(num1)
const num2 = [1]
console.log(num2)
*/
//Destructuring assignament, atribuição destriturada, (resumido)
//       [0] ,  [1]
const [num1, num2] = numeros;

function ElementoJsx() {
  return (
    <div>
      <h1>
        Jogando o resultado de uma posição de um array, dentro de uma variavel
      </h1>
      {num1}
      {num2}
    </div>
  );
}
export default ElementoJsx;
```
