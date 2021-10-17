# Comandos CSS

## align-items: center; 
(Centraliza, no meio), exemplo se você utilizar o flex-direction: column;, ai você vai centralizar verticalmente, se usar o, flex-direction: row; você irá centralizar horizontalmente, utilizando o comando abaixo, Obs: Só que você tem que ter pelo menos uma linha para fazer o alinhamento

```js
align-items: center;
```
## align-content: center; 
(Centraliza, no meio), exemplo se você utilizar o flex-direction: column;, ai você vai centralizar verticalmente, se usar o, flex-direction: row; você irá centralizar horizontalmente, utilizando o comando abaixo, Obs: Só que neste caso, pode alinhar mais de uma linha

```js
align-content: center;
```
## align-content: space-between; 
(Fazer o alinhamento entre as linhas do elemento)

```js
align-content: space-between;
```
## align-items: flex-start; 
(Centraliza, no começo, em cima do lado esquerdo.

```js
align-items: flex-start;
```
## align-items: flex-end; 
(Centraliza, no final em cima, do lado direito).

```js
align-items: flex-start;
```
## align-self: flex-end; 
(Centraliza, do lado direito, somente um elemento, os demais ficaram, alinhados).

```js
align-items: flex-start;
```
## animation-name: animacao; 
(animation-name propriedade especifica um nome para a animação @keyframes)

```js
animation-name: animacao;
```

## animation-duration: 
(Especifique que a animação deve completar um ciclo de 20 segundos)

```js
animation-duration: 20s;
```

## animation-iteration-count: infinite; 
(Propriedade especifica o número de vezes que uma animação deve ser reproduzida, infinite significa infinito, agora se colocar numero, vai fazer quantas vezes foi determinado)

```js
animation-iteration-count: infinite;
```

## background-color: 
(Cor de Fundo)

```js
background-color: #ededed;
```

## background: transparent; 
(Tirando a cor de fundo, ficando transparent)

```js
background: transparent;

```

## border-bottom:
(Borda botton)

```js
border-bottom: 1px solid #eee;
```

## border-color: 
(Cor da borda dos icones)

```js
border-color: rgb(255, 255, 255);
```

## box-shadow:
(Deslocamento lateral, Deslocamento vertical, Espalhamento, Cor)

```js
box-shadow: 5 px 5px 10px green;
```

## box-sizing: 
(Tamanho da caixa, moldura)

```js
box-sizing: border-box;
```

## border-radius: 
(Arredondar os lados)

```js
border-radius: 20px
```

## border-right: 
(Borda Lateral)

```js
border-right: 1px solid #ddd;
```

## border-style: 
(Estilo da borda)

```js
border-style: solid;
```

## border-width: 
(Largura da borda)

```js
 border-width: 2px;
```

## box-sizing: border-box; 
(Tamanho da caixa, moldura, o preenchimento e a borda serão incluídos na largura e na altura, ambos div tem o mesmo tamanho agora)

```js
box-sizing: border-box;
```

## border-style: solid; 
(Estilo da borda)

```js
border-style: solid;
```

## color: 
(Cor da fonte)

```js
color: white;
```

## cursor: pointer; 
(Pode clicar neste item)

```js
cursor: pointer;
```

## display: flex; 
(Para que um item, fique do lado do outro)

```js
display: flex;
```

## display: block; 
(Quando a tela tiver menor, menu vai aparecer)

```js
display: block;
```

## display: none; 
(Deixando invisivel, Ocultar)

```js
display: none;
```

exemplo:

```js
/*Deixando chekbox, invisivel*/
#bt_menu{
display: none; /*Ocultar*/
}
```

## flex-direction: column; 
(Itens um abaixo do outro, verticalmente)

```js
flex-direction: column;
```
## flex-direction: row; 
(Itens um do lado do outro, horizontalmente)

```js
flex-direction: row;
```


## flex-wrap: wrap; 
(Quebra, do elemento, quando passar da tela ele automaticamente, vai para baixo, exemplo que você tem um alinhamento 
horizontal e não cabe na tela, quanto você faz este comando ele ajusta automaticamente para parte de baixo.

```js
flex-wrap: wrap;
```

## flex: 1; 
(Pegar o espaço disponivel, quer dizer que este elemento box, ele é flexivel, quer dizer ele vai flexionar sua largura e altura, para sempre caber no container pai)

```js
flex: 1;
```

ou

```js
flex: 1 1 200px; /*Flex: Espandir, Ficar menor, Base para a foto*/
```

## font: 
(Espessura) (Tipo de fonte)

```js
font: normal 15 pt Arial
```

## font-family: 
(Tipo de fonte)

```js
font-family: 'Montserrat', sans-serif;
```

ou

```js
font-style: italic;
```

## font-size: 
(Tamanho da fonte)

```js
font-size: 12pt;
```

## font-weight: normal; 
(Espessura da fonte)

```js
font-weight: normal;
```

## flex: 
(Flex: Espandir, Ficar menor, Base para a foto)

```js
flex: 1 1 200px;
```

## height:
 (Altura)

```js
height: 100%;
```

## justify-content: space-between; 
(Vai deixar um espaço igual para todos os elementos, só no primeiro em cima e embaixo que não tem espaço)

```js
justify-content: space-between;
```
## justify-content: space-around; 
(Vai deixar um espaço igual para todos os elementos, só no primeiro em cima vai ter um espaço também igual e embaixo tambem vai ter um espaço igual)

```js
justify-content: space-between;
```

## justify-content: center; 
(Alinhamento)

```js
justify-content: center;
```

## list-style: none; 
(Sem marcador)

```js
 list-style: none;
```

## line-height: 
(Altura da linha)

```js
line-height: 1.35em;
```

## margin: auto; 
(Centralizar no meio da tela, a margem)

```js
margin: auto;
```

ou

```js
margin: 0 auto;
```

ou

```js
margin: 10px; /*Espaço entre a foto
```

## margin-top: 
(Margem superior)

```js
 margin-top: 5px;
```

## margin-bottom: 
(Margem inferior)

```js
margin-bottom: 18px;
```

## margin: 
(Margem, espaço lateral do botão)

```js
margin: 1em 0;
```

## margin-left: 
(Margem esquerda)

```js
margin-left: auto;
```

## margin-rigth: 
(Margem direita)

```js
margin-right: auto;
```

## margin-top: 
(Margem superior)

```js
margin-top: 5px;
```

## max-width: 
(Maxima Largura)

```js
max-width: 415px;
```
## @media
Media query, ele serve para deixar seu site responsivo, de acordo com a necessidade do seu projeto.
No google crome, quando você clicar com a tecla f12, do lado direito da tela vai aparecer umas opções, 
você vai clicar na opção aonde parece um quadrado e dentro um formato de celular, quando você clicar a primeira vez,
você poderá diminuir e aumentar a tela manualmente e ver o tamanho da tela em pixel, se clicar outra vez, vai aparecer 
varios tipos de modelos de celular e tablet, para você deixar seu site responsivo, caso não tiver todos os modelos é só clicar em
editar, e adicionar outros modelos de celular e tablet. Isto é uma ferramenta do google crome.

Media query, estilizando o CSS, dentro de um arquivo .CSS (Projeto básico do React, após criado o projeto, 1 Opção)

/*Dimensões de um Ipad, 768px / 1024px*/
Com este exemplo, está configurado um Ipad, quando tiver configurado, você tem que dizer o que vai fazer.

Arquivo App.js

```js
//Importando o react
import React from "react";
import "./App.css";

function App_function_Component() {
  return (
    <div className="App_function_Component">
     <h1>Olá Mundo</h1>
    </div>
  );
}

//Exportando Componente
export default App_function_Component;

```

Arquivo App.css
Neste exemplo, repare que tem a minima largura (min-width: 768px) e maxima largura (max-width: 1024px)

```js
@media (min-width: 768px) and (max-width: 1024px) {
  .App_function_Component {
    background-color: blue; 
  }
  .app_function_component,
  h1 {
    color: white;
  }
}
```

Mas você poria também determinar, somente a largura máxima, depois que passar do valor da largura máxima, 
não faça mais nada, abaixo do valor determinado, vai fazer o que você desejar

```js
@media (max-width: 100px) {
  .App_function_Component {
    background-color: blue; 
  }
  .app_function_component,
  h1 {
    color: white;
  }
}
```
Aqui você pode determinar a largura mínima, como funciona, quando passar acima do valor determinado da largura mínima, vai fazer o que você deseja, 
abaixo do valor determinado da largura minima não faça nada

```js
@media (min-width: 100px) {
  .App_function_Component {
    background-color: blue; 
  }
  .app_function_component,
  h1 {
    color: white;
  }
}
```
Se você for usar o media query com styled component, aqui está um exemplo:

Comando para instalar o styled component

```js
yarn add styled-components
```

Arquivo App.js

```js
import React from "react";
import * as St from "./style";

function App() {
  return (
    <div>
      <St.Title>Hello Word</St.Title>
    </div>
  );
}

export default App;
```

Arquivo, style.js

```js
import styled  from "styled-components"

export const Title = styled.h1`
  @media (min-width: 768px) and (max-width: 1024px) {
    color: white;
    background-color: blue; 
  }
`;
```

Agora para você determinar quando o celular está em pé ou deitado:
Landscape, celular em pé.
Portrait celular deitado.

Arquivo, style.js

```js
import styled  from "styled-components"

export const Geral = styled.div`
  font-family: sans-serif;
  height: 100vh;
  display: flex;
  justify-content: center;
`;

export const Title = styled.h1`
text-align: center;
color: white;

  @media (min-width: 768px) and (max-width: 1024px) {
  @media (orientation: landscape) {
    background-color: orange; 
  }
  @media (orientation: portrait) {
    background-color: blue; 
  }
}
`;
```

## min-height: 
(Altura minima)

```js
min-height: 500px;
```
se você colocar 100vh, ai vai pegar toda a area disponivel da tela.
```js
min-height: 100vh;
```

## min-width: 
(Largura minima)

```js
min-width: 500px;
```

## opacity: 0; 
(Opacity especifica a trasparencia de um elemento, isto é, o grau no qual o background atrás do elemento é sobreposto)

```js
opacity: 0;
```

## opacity: 1; 
(Totalmente opaco)

```js
opacity: 1;
```
## outline: none; 
(Esboço)

```js
outline: none;
```

## outline: 0;
(Tirando todo o tipo de animação, apos clicado em cima)

```js
outline: 0;
```

## padding: 
(Distancia entre os lados, 0, encima e embaixo, 15px distancia entre os dois lados)

```js
padding: 0 15px;
```
## padding-botton: 
(Descolar o texto da borda)

```js
padding-botton: 20px;
```
## padding-Horizontal: 
(Distancia entre os lados, horizontal)

```js
padding-horizontal: 20;
```

## position: relative; 
(As propriedade position pode assumir 4 valores diferentes: Static, Relative, Absolute e Fixed Utilizando o position relative o elemento passa a aceitar as propriedades Top, Botton, Left e Rigth. Com elas você pode alterar o posicionamento do elemento*/ overflow: visible; /*A propriedade overflow define o comportamento de um elemento quando suas dimensões são excedidas pelo conteúdo Hidden, O Conteudo excedido não ficará visível)

```js
position: relative;
```

## position:absolute; 
(Com ele você pode posicionar qualquer elemento)

```js
position: absolute;
```

## position: fixed; 
(Quando clicado, fixar a imagem no meio da tela, independente se rolar para baixo ou para cima)

```js
position: fixed;
```

## text-align: center; 
(Centralizar no meio da tela, o titulo)

```js
text-align: center;
```

## text-align: left; 
(Centralizar do lado esquerdo)

```js
text-align: left; 
```
## text-align: right; 
(Centralizar do lado direito)

```js
text-align: right; 
```

## text-decoration: none; 
([none (Sem decoração)], [underline red (sublinhado red)], [underline wavy cor (Sublinhado ondulado cor)] )

```js
text-decoration: none;
```
## text-decoration: line-through;
(Criar uma linha, riscando o texto)

```js
text-decoration: line-through;
```


## transition: 
(Tempo, após passado o mouse, vai carregando a cor no tempo)

```js
transition: all 0.35s;
```

Exemplo: Adicionando efeito ao botão

```js
input[type="button"]:hover,
input[type="button"]:focus {
background-color: #b10b7f; /*Cor apos passado o mouse em cima do botão*/
border-color: #850909; /*Cor da borda após passado em cima do botão*/
transition: all 0.35s; /*Tempo, após passado o mouse, vai carregando a cor no tempo*/
```
## Unidades de medida do CSS
```js
Layout Fixo px - Pixels
Layout Fluido % - Porcentagem auto - Automática vh - Viewport Height vw - Viewport Width
Textos fixos 1px = 0.75pt 16px = 12pt
Texto fluidos em - multiplicado pelo pai rem - multiplicado pelo root
```
## visibility: hidden;
 (O elemento está oculto mas ainda ocupa espaço)

```js
visibility: hidden;
```

## width: 
(Largura )

```js
width: 100%;
```
