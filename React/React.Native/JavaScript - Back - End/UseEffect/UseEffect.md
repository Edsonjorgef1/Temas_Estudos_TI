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

Exemplo React.native:

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
