## Este exemplo, é como buscar variavel, com ..., Spred Operator

```js
//Exemplo, spred operator
const spred = ["a", "b", "c"];

//Copiando os dados do spred operator
const copiaspred = [...spred];

const App = () => {
  return (
    <Geral>
      <h1>Spred Operator</h1>
      <p>Aqui estou selecionando todos os array</p>
      {copiaspred}

      <p>
        Aqui estou selecionando somente uma posição do array, letra maiuscula
      </p>
      {copiaspred[1].toUpperCase()}

      <p>
        Aqui estou selecionando somente uma posição do array, letra minuscula
      </p>
      {copiaspred[1].toLowerCase()}

      <p>Quem está dentro desta array</p>
      {spred}

      <p>Quantidade de itens dentro da array</p>
      {copiaspred.length}
    </Geral>
  );
};

export default App;
```
