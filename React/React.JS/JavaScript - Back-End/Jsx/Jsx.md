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
const idade = 90;

//Elemento JSX
const elemento = (
  <div>
    <h1>Elemento</h1>
  </div>
);

//Componente Function Component
function ElementoJsx() {
  return (
    <div className="ElementoJsx">
      {elemento} 
      <h1>Meu nome é {name} idade {idade}</h1>
    </div>
  );
}

export default ElementoJsx;
```

## Exemplo 2

```js
//Importando o react
import React from "react";

function formatarNome(usuario) {
return usuario.nome+' '+usuario.sobrenome
}

function App() {
let usuario = {
  nome: "Beto",
  sobrenome: 'Lacerda'
}
return <>
    <div>Meu nome é {formatarNome(usuario)}</div>
  </>
}

export default App
```


