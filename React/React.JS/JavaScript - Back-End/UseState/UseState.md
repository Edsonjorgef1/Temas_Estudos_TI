Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## UseState

Serve pra obter o valor inicial de uma constante ou utilizado para setar o Valor a uma constante
Podemos guardar uma string, numero, array com varios valores dentro, pode ser objeto com valores dentro tambpem.
Modelo Padrão:

```js
const [state, setState] = useState("");
```

Isto se chama Array.

```js
const [Aqui dentro se chama array] = useState("");
```

Valor inicial para o state

```js
//Passando um array vazio
useState([]);
ou;
//Passando uma string vazia
useState("");
ou
//Passando um objeto vazio
 useState({})
```

"State" = O state, em React, é onde guardamos os dados do nosso componente, ele são ambos objetos do javascript, é gerenciado de dentro do componente (como variáveis declaradas dentro de uma função).

"SetState" = Todas as alterações que fizer na variável, teria que usar está função, agenda uma atualização para o objeto state de um componente. Quando o state muda, o componente responde renderizando novamente

O nome "state", pode ser chamado o nome que desejar depois, exemplo o state pode chamar se eu quiser "count" de um contador, mas você pode dar o nome que você quiser.
O nome "setState", pode ser chamado o nome que desejar para ficar melhor a interpretação, exemplo poderia chamar de "setCount"
Esta é uma maneira de “preservar” alguns valores entre as chamadas de funções — useState é uma nova maneira de usar as mesmas capacidades que o this.state tem em uma classe. Normalmente, variáveis “desaparecem” quando a função sai mas variáveis de state são preservadas pelo React.

Modelo com nomes editados:

```js
const [count, setCount] = useState("");
```

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

## Exemplo 2

React.js:

```js
const [nome, setNome] = useState("Renata"); // Seta o valor inicial da state
const [troca, setTroca] = useState(false);

useEffect(() => {
  // Troca o valor da State
  setNome("Flavia");
}, [troca]); // Monitorando o estado da const

return (
  <div>
    <h1> {nome /*Recebe o valor inicial da State*/} </h1>
    <button onClick={setTroca(true)}>Botão troca nome</button>
  </div>
);
```

## Exemplo 2

React.native:

Padrão Useeffect

```js
useEffect(() => { }, [Array de dependência]
```

```js
const [nome, setNome] = useState("Renata"); // Seta o valor inicial da state
const [troca, setTroca] = useState(false);
useEffect(() => {
  // Troca o valor da State
  setNome("Flavia");
}, [troca]); // Monitorando o estado da const

return (
  <View>
    <Text> {nome /*Recebe o valor inicial da State*/} </Text>
    <TouchableOpacity onPress={setTroca(true)}>
      {" "}
      Botão troca nome{" "}
    </TouchableOpacity>
  </View>
);
```

## O que os Colchetes Significam?

Você pode ter percebido os colchetes quando declaramos a variável state:

```js
const [count, setCount] = useState(0);
```

Os nomes na esquerda não são parte da API do React. Você pode nomear suas próprias variáveis state:

```js
const [fruit, setFruit] = useState("banana");
```

Esta sintaxe do JavaScript é chamada de “atribuição via desestruturação”. Significa que estamos fazendo duas novas variáveis fruit e setFruit, onde fruit é definido para o primeiro valor retornado por useState, e setFruit é o segundo. É equivalente a este código:

```js
var fruitStateVariable = useState("banana"); // Retorna um par
var fruit = fruitStateVariable[0]; // Primeiro item do par
var setFruit = fruitStateVariable[1]; // Segundo item do par
```

Quando declaramos uma variável com useState, ela retorna um par — um array com dois itens. O primeiro item é o valor atual e o segundo é uma função que nos permite atualizá-la. Usar [0] e [1] para acessá-las é um pouco confuso porque elas tem um significado específico. É por isto que utilizamos atribuição via desestruturação no lugar.

## Usando Múltiplas Variáveis State

Declarar variáveis de state como par de [something, setSomething] também é útil porque nos permite dar diferentes nomes para diferentes váriaveis de state se quiséssemos usar mais de uma:

```js
function ExampleWithManyStates() {
// Declarar múltiplas variáveis de state!
  const [age, setAge] = useState(42);
  const [fruit, setFruit] = useState('banana');
  const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
```

No componente acima, temos age, fruit e todos como variáveis locais e podemos atualizá-las individualmente:

```js
function handleOrangeClick() {
  // Similar ao this.setState({ fruit: 'orange' })
  setFruit("orange");
}
```

## Exemplo como evitar atualizações no componente, performance

```js
import { useState } from "react";

const stateComponent = () => {
  const [user, setUser] = useState({ username: joao });

  console.log("Renderizando!");

  const updateUser = (newUser) => {
    if (newUser.username !== user.username) {
      setUser(newUser);
    }
  };
  return (
    <>
      <div>User: {user.username}</div>
      <button onClick={() => updateUser({ username: "engenheiro youtuber" })}>
        Update User
      </button>
    </>
  );
};
export default StateComponent;
```

Você não tem que usar muitas variáveis de state. Elas podem conter objetos e arrays muito bem. Portanto você ainda pode juntar dados relacionados. De qualquer maneira, diferente de this.setState em classe, ao atualizar uma variável de state, ela sempre é substituida ao invés de incorporada.


## Outro exempo bem simples, clicando e trocando o nome

```js
import { useState } from "react";

const App = () => {

  const [name, setName] = useState("Gilberto")
  

  const handleButtonClick = () => {
    //alert("O botão foi clicado")
    setName("Pedro")
    }
  

  return (

    <div className="App">
    
    Meu nome é {name}

   <h1>Executando a função assim que clicar no botão</h1>
   <button onClick={handleButtonClick}>clique aqui</button>
   
   
    </div>
  );
}

export default App;
```

## Exemplo, Clicando e atualizando o valor, muito simples

```js
import { useState } from "react";

const App = () => {

 const [n, setn] = useState(0)

 const handleMinus = () => {
 setn(n-1)
 }

 const handleMore = () => {
 setn(n+1)
 }
  
  return (

    <div className="App">
    
    <button onClick={handleMinus}>-</button>
    <div>
    {n} 
    </div>
    <button onClick={handleMore}>+</button>
   
    </div>
  );
}

export default App;
```

## Criando um input com useState (TypeScript)


```js
import React, { useState } from "react";

const App = () => {

  const [name, setName] = useState ('Pedro')

  const handleInput = (event: React.ChangeEvent<HTMLInputElement>) => {
  setName(event.target.value)
  }
  
  return (

    <div className="App">
    Nome: 
    <input type="text" value={name} onChange={handleInput}/>
    
    <hr/>
    Seu nome é: {name}
   
    </div>
  );
}

export default App;
```
## Criando um input com useState (CRA)

```js
import { useState } from "react";

const App = () => {

  const [name, setName] = useState ('Pedro')

  const handleInput = (event) => {
  setName(event.target.value)
  }
  
  return (

    <div className="App">
    Nome: 
    <input type="text" value={name} onChange={handleInput}/>
    
    <hr/>
    Seu nome é: {name}
   
    </div>
  );
}

export default App;
```

## Criando um input com useState, nome, sobrenome, idade (CRA)

```js
import { useState } from "react";

const App = () => {
  
  //Nome
  const [name, setName] = useState ('')

  const inputName = (event) => {
  setName(event.target.value)
  }

  //Sobrenome
  const [sobrenome, setSobrenome] = useState (' ')

  const inputSobrenome = (event) => {
  setSobrenome(event.target.value)
  }

  //Idade
  const [idade, setIdade] = useState ('')

  const inputIdade = (event) => {
  setIdade(event.target.value)
  }

  return (

    <div className="App">
    
    <div>
    Nome: <br/>
    <input type="text" value={name} onChange={inputName}/>
    </div>

    
    <div>
    Sobrenome: <br/>
    <input type="text" value={sobrenome} onChange={inputSobrenome}/>
    </div>

    <div>
    Idade: <br/>
    <input type="text" value={idade} onChange={inputIdade}/>
    </div>
    

    <hr/>
    Olá: {name + sobrenome}, tudo bem? 
    <br/>
    Você tem {idade} anos
   
    </div>
  );
}

export default App;
```

## Monitorando duas variaveis, dois input, com o useEffect

```js
import { useEffect, useState } from "react";

function App() {
  const [name, setName] = useState("");
  const [lastName, setLastName] = useState("");
  const [fullName, setFullName] = useState("");

  useEffect(() => {
  setFullName(`${name} ${lastName}`)
  }, [name, lastName])

  const handleNameChange = (event) => {
  setName(event.target.value)
  }

  const handleLastNameChange = (event) => {
  setLastName(event.target.value)
  }

  return (
    <div className="flex">
      <input type="text" placeholder="Digite seu Nome" value={name} onChange={handleNameChange} />
      <input type="text" placeholder="Digite seu Sobrenome" value={lastName} onChange={handleLastNameChange}/>
      <p>Nome Completo: {fullName}</p>
    </div>
  );
}

export default App;
```