# Exemplo de um elemento em JSX

Arquivo, App.js

```js
//Importando o react
import React from "react";

//Elemento JSX
const elemento = 
  <div>
    <h1>Elemento</h1>
  </div>

//Componente Function Component
function ElementoJsx() {
  return (
    <div className="ElementoJsx">
      {elemento} {/*Repare que estou pegando os dados, fora do componente*/}
    </div>
  );
}

//Exportar componente
export default ElementoJsx;
```