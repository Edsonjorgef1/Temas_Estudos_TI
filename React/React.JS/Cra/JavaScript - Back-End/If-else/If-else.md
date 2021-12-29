## If e Else

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

### Validação simples de um cpf

```js
import React from "react";

let cpf = "123.456.789-12";
let mensagemCpf = "";

if (cpf.length === 14) {
  mensagemCpf = "Correto_Cpf";
} else {
  mensagemCpf = "Verificar_CPF";
}

function App_function_Component() {
  return <div className="App">{mensagemCpf}</div>;
}
export default App_function_Component;
```

## Abreviação somente, true

```js
//Importando o react
import React from "react";

let isGirl = true;
let resultado = "";

//Tradicional
/*
if (isGirl === true){
  resultado =  "True"
} else {
  resultado =  "False"
}
*/

//Forma Abreviada
if (isGirl) {
  // repare que aqui não coloquei true mais ele ja entendeu true assim
  resultado = "True";
} else {
  resultado = "False";
}

function App_function_Component() {
  return <div className="App">{resultado}</div>;
}

export default App_function_Component;
```
