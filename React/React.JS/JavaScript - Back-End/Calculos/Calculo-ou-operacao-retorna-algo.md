Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Faz um calculo ou operação e retorna algo

```js
//Metodo, React.js
import React from "react"; 

//Multiplicar

function MultiplicarPorDois(valor) {
  return valor * 2 // Devolvendo para que seja usado em outro luagar esta função
}

let resultado = MultiplicarPorDois(5)


//Assim temos o resultado desta função, dentro desta variavel
function ElementoJsx() {   
  return (
    <div>

      <h1>Resultado, dentro da Variavel</h1>
      {resultado} 
      
      <h1>Resultado Retornando</h1>
      {MultiplicarPorDois(5)} 

    </div>
  );
}

export default ElementoJsx;  
