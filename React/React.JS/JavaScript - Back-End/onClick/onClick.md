## onClick

## Exemplo 1

Renderiza um contador. Quando você clica no botão, ele incrementa o valor:
React.js

```js
import React, { useState } from "react"; // Aqui você deve importar o "useState" para que ele possa funcionar.
// Aqui também foi importado o React, tem que importar o React para o que estiver dentro do componente, no return em div, possa funcionar, que no caso é o jsx, o babel processador do javascript fica responsavel em fazer, funcionar o jsx por baixo dos panos sem menos você notar.

function Example() {
  // Component function component

  const [count, setCount] = useState(0); // Aqui é o modelo padrão do useState só que agora editamos.
  //Dentro do componente Example, declaramos uma nova variável de state chamando o Hook useState. Ele retorna um par de valores, no qual damos nomes. Estamos chamando nossa variável count porque ela mantém o número de cliques no botão. Inicializamos como zero passando 0 como o único argumento do useState. O segundo item retornado é a própria função. Ela nos permite atualizar o count então nomeamos para setCount.

console.log('Renderizou') // Repare, que sempre que o valor de estado precisa ser atualizado, o que React vai fazer vai atualizar o componente, assim vai escrever o
Renderizou no console, só para você entender, que o componente foi atualizado, para teste.

  return (
    <div>
      {/*Aqui dentro jsx, só está funcionando porque importamos o React*/}
      <p>You clicked {count} times</p>
      {/*Porque colocamos o count aqui, para ele monitorar, lembra o que é count, ele é o state, que foi explicado, acima, resumindo ele vai mostrar o que foi guardado, dentro dele, apenas a ultima atualização*/}
      <button onClick={() => setCount(count + 1)}>Click me</button>
      {/*Quando for clicado o button, que no caso é o botão, ele vai pegar o setCount que no caso é o setState lembra, ele vai pegar a atualização que foi feita e vai enviar para o state, que é o count, depois está somando mais um, o que estiver no state, e somar mais um.*/}
    </div>
  );
}
```