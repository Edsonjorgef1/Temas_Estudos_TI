13:28

## Redux

Se você não sabe como funciona o (props), tem uma pasta acima desta aqui chamada, props, leia ela antes de proceguir, lendo este tutorial.
Se você não conhece um componente em react e não sabe como funciona, tem uma pasta acima desta chamada componentes, estude ela antes de processeguir com este tutorial.

### Prop Drilling

Problemas o Redux resolve, Prop Drilling.

Prop drilling é um estágio do desenvolvimento que acontece quando precisamos obter dados que estão em várias camadas na árvore de componente react.

Então o que eu faço para resolver este problema de Prop Drilling.
Exemplo: Resumindo: Se eu disparar uma ação, eu posso buscar estas informações, fora das camadas da árvore do componente react, assim direcionando, meu armazenamento em um lugar fixo, aonde posso buscar e alterar os dados.

### Fluxo de dados (Flux)

<img src="https://res.cloudinary.com/drimg72d1/image/upload/v1635287246/Redux_Imagem.png" style=" width:500px ; height:300px " />

Link do site para saber mais sobre o assunto:

```js
https://facebook.github.io/flux/
```

Data Store:
Sempre retorna um novo estado.

```js
Componentes:

1.Recebe os dados via props.

2.Se inscreve para receber as mudanças, do Data Store

3.Toda vez que o DataStore tiver uma mudança, pode reagir, como você pode fazer isso, nosso componentes, podem estar disparando "action", exemplo: Eventos, quando clica em um botão, tipo se você for clicar no botão para adicionar alguma coisa no carrinho. Pode buscar os dados em uma api, sem precisar clicar em lugar nenhum.

4."action" vai ter um:

"Type": ELa retorna um objeto, qual o nome da ação
"Payload": Pode passar mais dados, como se fosse parametros para estar recebendo.
"Action": Ela retorna um objeto e vai parar la no nosso reducer.
"Reducer": Vai receber os dados da action, dentro dele vai conter toda a lógica de renderização dos dados.

Exemplo:
"Action" tem um type de "adicionar produtos ao carrinho" e o "Payload" tem o ID daquele determinado produto, então nosso "reducer" vai receber nossos dados da "action", quando ele for mutar o "Data Store", ele faz isso retornando, ele vai usar o "Payload", para procurar la dentro do array de produtos e qual o produto exato para colocar no carrinho e mover ele para a lista do carrinho, como ele faz isso, ele retorna o novo estado da store.
```

## Exemplo de uma aplicação, Redux

Se você não conhece o que é Opeadores Aritméticos, assista a aula antes de continuar, lendo.

```js
https://www.youtube.com/watch?v=7RMtfwYDbDE&list=PLb8jL9jtpafkJAs5U5bc1lgmHIE6c_OK_&index=11
```

### Action creator

Aqui vai conter todas as nossas ações, Action creator é uma função, que retorna uma action, cria uma ação.

Exemplo:

Arquivo, store/Calculator/Calculator.action.js

Se você não sabe o que é um array, assista a aula, antes de continuar lendo.

```js
https://www.youtube.com/watch?v=uYp2m7KU-KU&list=PLb8jL9jtpafkJAs5U5bc1lgmHIE6c_OK_&index=25
```

```js
export function sum(a, b) {
  // Recebe os dados via props.
  return {
    // Ela retorna um objeto e vai parar la no nosso reducer, que esta no proximo arquivo no Calculator/Calculator.reducer.js
    type: "SUM", // Nome da ação
    payload: [a, b], // ID do produto, [a=0, b=1] = Array
  };
}

export function subract(a, b) {
  return {
    type: "SUBTACT",
    payload: [a, b],
  };
}
```

### Reducer

Arquivo, store/Calculator/Calculator.reducer.js

Se você não sabe o que é [Switch e Case], do javascript, assista esta aula antes de continuar lendo.

```js
https://www.youtube.com/watch?v=CqC6pEgXgWI&list=PLb8jL9jtpafkJAs5U5bc1lgmHIE6c_OK_&index=34
```

```js
"Reducer": Vai receber os dados da action, "Arquivo, store/Calculator/Calculator.action.js" dentro dele vai conter toda a lógica de renderização dos dados.
Uma função que retorna nosso estado, está função retorna o "state", e o segundo "action State" se refere ao estado atual de minha aplicação.
Toda vez que meu componente dispara, alguma action
de algum lugar da aplicação, ela vai ser retornada
para nosso reducer, ou seja a cada modificação do estado
da aplicação nós vamos executar o metodo reducer.
ele devolve um novo estado para o nosso date store.
Action, é nosso objeto que acabou retornando dentro
do arquivo Calculator.action.js.
Agora preciso retornar um estado com o type de nossa ação
```

```js
export default function (state = 0, action) {
  // Aqui iniciamos com zero, a primeira vez, que renderiza a tela, está em zero, as demais acões vai ser substituido o state.
  switch (
    // Aqui estamos utilizando o [Switch e Case]
    action.type
  ) {
    case "SUM":
      return action.payload[0] + action.payload[1];

    case "SUBTACT":
      return action.payload[0] - action.payload[1];

    default:
      return state;
  }
}
```

### Configuração do redux, aonde vou estar armazenando meu store

Arquivo, store/Calculator/Calculator.reducer

```js
import { createStore, combineReducers } from "redux";
import calculatorReducer from "./Calculator/Calculator.reducer";

const rootReducer = combineReducers({
  calculator: calculatorReducer,
});

const store = createStore(rootReducer);

export default store;
```

Arquivo, index.js

```js
import React from "react";
import ReactDOM from "react-dom";
import store from "./store/store";
import { Provider } from "react-redux";

ReactDOM.render(
  <React.StrictMode>
    <Provider store={store} />
  </React.StrictMode>,
  document.getElementById("root")
);
```
