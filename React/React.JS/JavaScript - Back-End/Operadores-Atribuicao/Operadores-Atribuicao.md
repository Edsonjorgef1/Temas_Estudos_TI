Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

##  Operadores de Atribuição

```js

//Metodo, React.js
import React from "react"; 

let valorCasa = 2
let valorCasaX = 2
let valorAluguel = 2
let valorAluguelX = 2

function ElementoJsx() {   
  return (
    <div>

      <h1>Valor de atribuição +=</h1>
      {valorCasa += valorCasa} 
      
      <h1>Valor de atribuição Real</h1>
      {valorCasaX = valorCasaX + valorCasaX}

      <h1>Valor de atribuição -=</h1>
      {valorAluguel -= valorAluguel}

      <h1>Valor de atribuição Real</h1>
      {valorAluguelX = valorAluguelX - valorAluguelX}

    </div>
  );
}

export default ElementoJsx;  
```