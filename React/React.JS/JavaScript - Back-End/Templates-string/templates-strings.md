## Template String

```js
//Importando o react
import React from "react";


//Um exemplo bem simples de "template string"
let nome = "Beto"
nome = `Meu nome é ${nome}`
//  ` Texto  ${variavel}`  // Template string


//Componente Function Component
function ElementoJsx() {
  return (
    <div className="ElementoJsx">
      {nome} {/*Repare que estou pegando os dados, fora do componente*/}
    </div>
  );
}

//Exportar componente
export default ElementoJsx;
```