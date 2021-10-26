13:28

## Redux

### Prop Drilling

Problemas o Redux resolve, Prop Drilling.

Prop drilling é um estágio do desenvolvimento que acontece quando precisamos obter dados que estão em várias camadas na árvore de componente react.

Então o que eu faço para resolver este problema de Prop Drilling.
Exemplo: Resumindo: Se eu disparar uma ação, eu posso buscar estas informações, fora das camadas da árvore do componente react, assim direcionando, meu armazenamento em um lugar fixo, aonde posso buscar e alterar os dados.

### Fluxo de dados (Flux)

<img src="https://https://res.cloudinary.com/drimg72d1/image/upload/v1635287246/Redux_Imagem.png" />

Link do site para saber mais sobre o assunto:

```js
https://facebook.github.io/flux/
```

Data Store:
Sempre retorna um novo estado.

Componentes:
1.Recebe os dados via props.
2.Se inscreve para receber as mudanças, do Data Store
3.Toda vez que o DataStore tiver uma mudança, pode reagir, como você pode fazer isso, nosso componentes podem estar disparando "action", exemplo: Eventos, quando clica em um botão, tipo se você for clicar no botão para adicionar alguma coisa no carrinho. Pode buscar os dados em uma api, sem precisar clicar em lugar nenhum.
"action" vai ter um:
Type: ELa retorna um objeto, qual o nome da ação
Payload: Pode passar mais dados, como se fosse parametros para estar recebendo.
Action: Ela retorna um objeto e vai parar la no nosso reducer.
Reducer: Vai receber os dados da action, dentro dele vai conter toda a lógica de renderização dos dados.
Exemplo:
Action tem um type de "adicionar produtos ao carrinho" e o Payload tem o ID daquele determinado produto, então nosso reducer vai receber nossos dados da action, quando ele for mutar o Data Store, ele faz isso retornando, ele vai usar o Payload, para procurar la dentro do array de produtos e qual o produto exato para colocar no carrinho e mover ele para a lista do carrinho, como ele faz isso, ele retorna o novo estado da store.
