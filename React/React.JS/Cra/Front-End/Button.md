Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Button, praticamente é um botão

## Exemplo 1, CLicando e fazendo um alert

Aqui foi criado uma função, com constante.

App.js

```js
const App = () => {
  const handleButtonClick = () => {
    alert("O botão foi clicado");
  };

  return (
    <div className="App">
      <h1>Executando a função assim que clicar no botão</h1>
      <button onClick={handleButtonClick}>clique aqui</button>
    </div>
  );
};

export default App;
```
