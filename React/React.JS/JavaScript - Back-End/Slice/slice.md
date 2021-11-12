Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Slice
Com ele você pode fatiar seu array, podendo selecionar o inicio e o fim aonde desejar fatiar.

```js

let frutas = ["Maça", "Banana", "Melancia", "Acerola", "Limão", "Laranja"]
//              0        1          2           3         4         5
 

let resultado = frutas.slice(2, 4)
// 2, posição inicial para fatiar
// 4, posição final para fatiar

console.log(resultado)

function App_function_Component() {
     return (
    <div className="App">
    {resultado}
    </div>
  );
}
export default App_function_Component;
```