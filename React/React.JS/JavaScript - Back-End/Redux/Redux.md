## Redux

Comando para instalar o Redux

```js
yarn add react-redux redux
ou
npm install react-redux redux
```

Redux TypeScript

Comando para instalar

```js
npm install @types/react-redux
```

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
  /* State, Aqui iniciamos com zero, a primeira vez, que renderiza a tela, está em zero, as demais acões vai ser substituido o state.
  Action, Toda vez que meu componente dispara, alguma
  action de algum lugar da aplicação, ela vai ser retornada
  para nosso reducer, ou seja a cada modificação do estado
  da aplicação nós vamos executar o metodo reducer*/
  switch (
    // Aqui estamos utilizando o [Switch e Case]
    action.type // Aqui estamos, especificando, que abaixo, será o type, o nome que foi especificado no aquivo, store/Calculator/Calculator.action.js
  ) {
    case "SUM": // Aqui estamos buscando a informação no arquivo, store/Calculator/Calculator.action.js, type: "SUM", // Nome da ação, aqui você especifica qual o tipo, quem é, para depois abaixo retornar o que você deseja fazer.
      return action.payload[0] + action.payload[1]; // Aqui estamos buscando a informação, no Arquivo, store/Calculator/Calculator.action.js, payload: [a, b], // ID do produto, [a=0, b=1] = Array, e estamos retornando a soma para eles, igual está aqui.

    case "SUBTACT": // este aqui é igual o exemplo anterior do SUM, lógica parecida, só muda agora que está subtraindo
      return action.payload[0] - action.payload[1];

    default:
      // Caso meu case, não existir, permaneço no estado atual
      return state;
  }
}
```

### Configuração do redux, aonde vou estar armazenando meu store

Arquivo, store/Calculator/Calculator.store
createStore = Cria uma loja Redux que contém a árvore de estado completa do seu aplicativo. Deve haver apenas uma única loja em seu aplicativo.
combineReducers = Conforme seu aplicativo fica mais complexo, você desejará dividir sua função de redução em funções separadas, cada uma gerenciando partes independentes do estado .

A combineReducers função auxiliar transforma um objeto cujos valores são diferentes funções de redução em uma única função de redução que você pode passar createStore.

O redutor resultante chama cada redutor filho e reúne seus resultados em um único objeto de estado. O estado produzido por combineReducers()namespaces os estados de cada redutor em suas chaves, conforme passado paracombineReducers()

```js
import { createStore, combineReducers } from "redux";
import calculatorReducer from "./Calculator/Calculator.reducer";

const rootReducer = combineReducers({
  // de onde vem o combineReducers
  calculator: calculatorReducer, // o valor da propriedade calculator vai ser o calculatorReducer, que é o arquivo
});

const store = createStore(rootReducer); // Criando uma store, nos dados que combinamos, const store recebe o valor do createStor e passando o ootReducer

export default store;
```

### Como fazer a conecção com o redux, (1 Opção, forma antiga)

Arquivo, Calculator.jsx

```js
//Como fazer a conecção redux

import React from "react";
// Conectando meu estado
import { connect } from "react-redux"; // connect vai permitir que eu pegue algumas
// propriedades la no redux, aquivo store.js

function Calculator({ result }) {
  return (
    <>
      <input type="text" placeholder="a" />
      <input type="text" placeholder="b" />

      <button>somar</button>
      <button>subtrair</button>

      <div>{result}</div>
    </>
  );
}
function mapStateToProps(state) {
  return {
    result: state.calculator,
  };
}
export default connect(mapStateToProps)(Calculator); // uma função retornando outra função

/*
A connect()função conecta um componente React a uma loja Redux.

Ele fornece a seu componente conectado as partes dos dados de que precisa da loja e as funções que pode usar para despachar ações para a loja.

Ele não modifica a classe de componente transmitida a ele; em vez disso, ele retorna uma nova classe de componente conectado que envolve o componente que você transmitiu.

// Exemplos connect, site link


https://react-redux.js.org/api/connect
*/
```

### Como fazer a conecção com o redux, (2 Opção, forma mais atual)

Arquivo, Calculator.jsx

```js
import React from "react";
import { useSelector } from "react-redux";

function Calculator() {
  /*const result = useSelector(function(state){
  return state.calculator
  })
  */
  /*ou*/

  const result = useSelector((state) => state.calculator);

  return (
    <>
      <input type="text" placeholder="a" />
      <input type="text" placeholder="b" />

      <button>somar</button>
      <button>subtrair</button>

      <div>{result}</div>
    </>
  );
}

export default Calculator;

/*
"useSelector"
Esse método, que também deve ser importado de ‘react-redux’, recebe um callback como parâmetro. Esse callback deve retornar o state novo. Se o state novo for diferente do anterior, então o componente irá renderizar o novo valor na tela. Tentei deixar a explicação simples.

O useSelector será executado sempre que houver um dispatch de uma action
*/

/*
"useDispatch"
Muito parecido com o dispatch do redux sem react, nos dá a possibilidade de disparar uma action.

Estas são algumas possibilidades que temos usando o hooks, mas agora vamos voltar para o Redux.

Já que apresentei todos os conceitos necessários, vou construir o mesmo código que fizemos no artigo anterior, só que agora usando react-redux. Os comentários terão propósitos didáticos para reforçar o que vimos até aqui.
*/
```

Site para exemplo mais completo, UseSelector e Dispatch

```js
https://serfrontend.com/blog/redux-com-react-para-iniciantes/index.html
```

Arquivo, index.js

```js
import React from "react";
import ReactDOM from "react-dom";
import store from "./store/store";
import { Provider } from "react-redux"; // O React Redux inclui um componente <Provider />, que disponibiliza a loja Redux para o resto do aplicativo, conecta esta store dentro de nossa aplicação, provider ele é um componente.

ReactDOM.render(
  <React.StrictMode>
    <Provider store={store} />
    {/* Eu não preciso ficar passando o store varias vezes, não vai ser passado como props, só preciso passar minha store em volta do provider e pronto e encapsula minha aplicação*/}
  </React.StrictMode>,
  document.getElementById("root")
);
```

React Redux fornece um par de ganchos React personalizados que permitem que seus componentes React interajam com a loja Redux.

### useSelector

lê um valor do estado da loja e assina atualizações, enquanto

### useDispatch

retorna

### dispatchmétodo

Permitir que você despache ações.

## Exemplo 2

```js
import React from "react";
import { useSelector, useDispatch } from "react-redux";
import {
  decrement,
  increment,
  incrementByAmount,
  incrementAsync,
  selectCount,
} from "./counterSlice";
import styles from "./Counter.module.css";

export function Counter() {
  const count = useSelector(selectCount);
  const dispatch = useDispatch();

  return (
    <div>
      <div className={styles.row}>
        <button
          className={styles.button}
          aria-label="Increment value"
          onClick={() => dispatch(increment())}
        >
          +
        </button>
        <span className={styles.value}>{count}</span>
        <button
          className={styles.button}
          aria-label="Decrement value"
          onClick={() => dispatch(decrement())}
        >
          -
        </button>
      </div>
      {/* omit additional rendering output here */}
    </div>
  );
}
```

Site para mais exemplos de redux

```js
https://react-redux.js.org/api/hooks
```
