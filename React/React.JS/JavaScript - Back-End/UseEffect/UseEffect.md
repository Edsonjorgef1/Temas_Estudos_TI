Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## UseEffect

Roda uma função toda vez que o componente é iniciado ou quando está monitorando um comportamento de uma state ou um componente.

O useEffect seria pode ser renderizado quando o componente é iniciado e dentro de sua estrutura tem um array de dependencias, neste array de dependência é renderizado novamente o conteúdo que está dentro do useEffect.
Quando renderiza pela primeira vez o Useeffect, o componente e toda alteração no array também será alterada

```js
useEffect(() => { Função que será executada, corpo de uma função de um componente de maut, componente update, resumindo o codigo que será executado }, [Em qual circunstancias este paramentro deve ser executado, Array de dependência, o efeito só será ativado se os valores na lista forem alterado, podendo ser um useState, uma variavel qualquer, ou qualquer coisa que possa sofrer alteração, useEffect só será disparado quando a variavel que estiver aqui dentro mudar, dentro desta array podemos passar varias variaveis ]
```

Exemplo React.js:

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
## Rodando alguma coisa quando o componente e colocado na tela

```js
useEffect(() => {
  
  setNome("Flavia");
}, []); // Dependencia vazia
```

## Se eu quero que atualize o componente sempre, em um trecho de codigo

```js
useEffect(() => {
  
  setNome("Flavia");
}); // tiro as dependencia como um todo
```

## Se eu quero refletir somente uma mudança de uma variavel ou de um intem de estado

```js
useEffect(() => {
  
  setNome("Flavia");
}, [Varial ou Estado]); 
```