Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## SASS

```js
https://sass-lang.com
https://sass-lang.com/install
https://sass-lang.com/guide
https://sass-lang.com/documentation
```

## Importando, uma cor que foi declarada

Aqui foi declarado algumas cor, depois vamos importar somente o nome, isso é
muito bom, pois tem projetos que já tem cores definidas, isso ajuda muito.

src/scss/variables.scss

```js
$primary-color: #af7eeb;
$secondary-color: #939cbd;
$tertiary-color: #ffffff;

//Vamos importar está cor olha que facil
$primary-background-color: #e3e9ff;

$secondary-background-color: $tertiary-color;
$tertiary-background-color: $primary-color;

$primary-text-color: $secondary-color;
$secondary-text-color: $tertiary-color;

$danger-color: #ff002e;
```

src/styles.scss

```js
//Aqui estamos importando o caminho, aonde foi declarada as cores
@import "./dist/scss/variables.scss";

//Olha que legal, eu importei a cor, primary-background-color, que foi declarada em variables.scss
body {
  background: $primary-background-color;
}
```

src/app/modules/componts/header/header.component.html

```js
<h1>header works!</h1>
```

src/app/modules/componts/header/header.component.css

```js
//Importando o caminho da fonte
@import "../../../../../dist//scss//variables.scss";

h1 {
  width: 100%;
  padding: 15px 0;

  text-align: center;
  font-size: 18px;
  //Aqui estou importando a cor, da fonte
  color: $secondary-text-color;
  //Aqui estou importando a cor do fundo
  background-color: $tertiary-background-color;
}
```
