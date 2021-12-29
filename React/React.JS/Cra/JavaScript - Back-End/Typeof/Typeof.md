Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Typeof

O operador typeof retorna uma string indicando o tipo de um operando.

Pesqui site:

```js
https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/typeof
```

Descrição
Esta tabela resume os possíveis valores que são retornados pelo typeof:

```js
// Números - Numéricos
typeof 37 === "number";
typeof 3.14 === "number";
typeof Math.LN2 === "number";
typeof Infinity === "number";
typeof NaN === "number"; // Apesar de ser "Não-Numérico"
typeof Number(1) === "number"; // mas nunca utilize desta forma!

// Strings - Seqüências de caracteres
typeof "" === "string";
typeof "bla" === "string";
typeof typeof 1 === "string"; // typeof sempre retorna uma string
typeof String("abc") === "string"; // mas nunca utilize desta forma!

// Booleans - Lógicos booleanos
typeof true === "boolean";
typeof false === "boolean";
typeof Boolean(true) === "boolean"; // mas nunca utilize desta forma!

// Undefined - Indefinidos
typeof undefined === "undefined";
typeof blabla === "undefined"; // uma variável indefinida

// Objetos
typeof { a: 1 } === "object";
typeof [1, 2, 4] === "object"; // use Array.isArray ou Object.prototype.toString.call para diferenciar os objetos das arrays
typeof new Date() === "object";

typeof new Boolean(true) === "object"; // isto é confuso, portanto não use desta forma!
typeof new Number(1) === "object"; // isto é confuso, portanto não use desta forma!
typeof new String("abc") === "object"; // isso também é confuso, assim evite usar esta construção!

// Funções
typeof function () {} === "function";
typeof Math.sin === "function";
```

### Exemplo 1

```js
//Importando o react
import React from "react";

let mensagem = "s";

/*
if ((typeof mensagem) === "string") {
mensagem = "string"
} else {
  mensagem = "não é string"
}
//ou
*/

//Operador ternario
let texto =
  typeof mensagem === "string"
    ? (mensagem = "String")
    : (mensagem = "não é uma string");

function App_function_Component() {
  return <div className="App">{texto}</div>;
}

export default App_function_Component;
```

### Exemplo 2

```js
import React from "react";

let number = 10;
let resultado = "";

if (
  typeof number !== "undefined" &&
  number !== "" &&
  number !== null &&
  number !== 0 &&
  number !== false
) {
  resultado = "Variavel True";
} else {
  resultado = "Variavel false";
}

function App_function_Component() {
  return <div className="App">{resultado}</div>;
}

export default App_function_Component;
```
