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
     return (
    <div className="App">
    {mensagemCpf}
    </div>
  );
}
export default App_function_Component;
```
