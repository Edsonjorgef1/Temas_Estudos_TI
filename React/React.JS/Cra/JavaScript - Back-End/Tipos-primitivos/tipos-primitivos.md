Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Tipos primistivos
Tipos primitivos

```js
//Metodo, React.js
import React from "react";

let nome = "Beto" // String literal
console.log(nome)

let idade = 20 // number literal, trabalhando com valores

let estadoAprovado = true // Bolean

let corSelecionado = null // Redenifinir um valor

//Componente Function Component
function ElementoJsx() {
  return (
    <div>
    {nome}
    {idade}
    {estadoAprovado}
    {corSelecionado}
    </div>
  );
}

//Exportar componente
export default ElementoJsx;
```