Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Diferente, ==!

```js
// !==, Se for difente faça alguma coisa

import React from "react"; 
let valorUm = "fabio"
let valorDois = "beto"
let resultado = valorUm !== valorDois 
console.log(resultado)

let final = resultado  ? "Diferente" : "Igual"
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