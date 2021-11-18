Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Jsx

Você pode inserir qualquer expressão JavaScript válida, dentro das chaves em JSX

### Exemplo 1

Pegando os dados, fora do componente, elemento em Jsx

```js
//Importando o react
import React from "react";

const name = "Beto";

//Elemento JSX
const elemento = (
  <div>
    <h1>Elemento{}</h1>
  </div>
);

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
