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

## Operadores Aritméticos, utilizando uma função

```js
import React from 'react';



let n1 = 10
let n2 = 3 

function somar(n1, n2) {
return n1 + n2
}



export default function App() {

  return (

    <div className="App">
     Somar:{somar(n1, n2)}  {/*esta linha pode ser assim tambem, Somar:{somar(n1, n2) + n1} */}
    </div> 
    
  );
}
```