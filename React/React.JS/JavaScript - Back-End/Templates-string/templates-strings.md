Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Template String

### Exmplo: 1

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

### Exemplo: 2

Vamos dar outro exemplo, você poderia buscar os dados, com o redux, utilizando o useSelector

```js
import React from "react";
import { useSelector } from "react-redux";

function AppHeader() {
  //Passando o meu resultado para o header, olha que está em lugares diferente mesmo assim foi possivel verificar o 
  //valor do resultado, o redux está assecivel em toda aplicação

	const resutado = endereco.length > 1 ? 'mais de um' : 'um' 
	const Texto = `Localizamos que você possui ${resultado} endereço em Cadastro.`
  

  const endereco = useSelector((state) => state.pessoas);
  return (
    <Wrapper>
      <span>{endereco}</span>
    </Wrapper>
  );
}

export default AppHeader;
```
