## Var

Var, variavel, mas o let, é mais atual.

App.js

```js
import React from "react"

var valorAtual = 10


console.log(valorAtual)

export default function App(){
return(
    <div className="App">
    {valorAtual}
    </div>
);
}
```