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

## Destructuring_assignament, para objetos

```js
//Metodo, React.js
import React from "react";
//Destructuring assignament, objeto
const a = {
  loading: true,
  data: 10,
};
/*
//Metodo antigo
const loading = a.loading
console.log(loading)
const data = a.data
console.log(data)
*/
//Metodo Atual
const { loading } = a;
// Template string
//Let variavel = ` Texto ${variavel}`
let resultado = `Olá ${loading}`;

console.log(loading);
const { data } = a;
console.log(data);

function ElementoJsx() {
  return <div>{resultado}</div>;
}
export default ElementoJsx;
```
