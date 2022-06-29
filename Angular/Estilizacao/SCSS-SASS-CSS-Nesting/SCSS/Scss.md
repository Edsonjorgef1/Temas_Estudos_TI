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
$bg-color: #eee;
$title-backgroud: #333;
$main-color: #fff;
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
<div class="container">
  <h1 id="title">oi</h1>
</div>
<div class="container-bottom">
  <p>Teste</p>
</div>
<router-outlet></router-outlet>
```

src/app/modules/componts/header/header.component.scss

```js
//Importando o caminho da fonte
@import "../../../../../dist//scss//variables.scss";

.container {
  background-color: $bg-color;
  padding: 20px;

  #title {
    background-color: $title-backgroud;
    color: $main-color;
    text-align: center;
    padding: 10px;
  }
}
.container-bottom {
  background-color: blue;
  padding: 50px;
  text-align: center;
}
```
