Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Listagem ul

lista desordenada, não tem uma orden específica

## Listagem ol

lista ordenada, irá identificar os números da lista

```js
import React from "react"; // importando o React

//Componente Function Componente
function App() {
  const numbers = ["Beto", 6, 3, 4, 5];

  const updatedNums = numbers.map(number => {
    return <li>{number}</li>;
  });
  console.log(updatedNums);

  return (
    <div>
      {/*Aqui dentro JSX, ja está funcionando agora, porque importamos o react*/}
      <h1>Lista de bolo:</h1>
      <ul>{updatedNums}</ul>
    </div>
  );
}

export default App;
```
