Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Operadores Aritméticos (Matemática)

```js
//Metodo, React.js
import React from "react"; 


let salario = 2
// + Soma
// - Subtração
// * Multiplicação
// / Divisão
// ++ Incremento
// -- Decremento

function ElementoJsx() {   
  return (
    <div>

      <h1>Soma</h1>
      {salario + salario}

      <h1>Subtração</h1>
      {salario - salario}

      <h1>Multiplicação</h1>
      {salario * salario}
      
      <h1>Dividir</h1>
      {salario / salario}
      
      <h1>Incremento</h1>
      {++salario}

      <h1>Decremento</h1>
      {--salario}
  
    </div>
  );
}

export default ElementoJsx;  
```