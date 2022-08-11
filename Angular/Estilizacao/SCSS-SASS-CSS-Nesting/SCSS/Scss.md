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

## Aqui vou demonstrar, outro forma de chamar uma variavel no scss (:root {}) (body { background-color: var(--body)})

src/app/core/components/header/header.component.html

```js
<body class="dark-theme">
  <h1> Theme Dark Teme </h1>
</body>
```

src/app/styles.css

```js
:root {
  --primary: #1976d2;
  --body: #fff; // Branco
  --text-menu: #fff;
  --text-body: #4b4b4;
}
:root .dark-theme {
  --primary: #0d47a1;
  --body: #4b4b4b; // Cinza
  --text-menu: #fff;
  --text-body: #fff;
}
body {
  //Repare que legal, eu estou utilizando a var(--body), quando meu body, for igual dark-theme, ele irá ficar cinza se não for ficara branco.
  background-color: var(--body);
}
```

## Neste exemplo estou mostrando como funciona o &, basicamente ele referência a tag

src/app/core/components/header/header.component.html

```js
<body class="dark-theme">
  <header>
    <img src="./assets/angular.svg" alt="Logo da empresa Angular" />

    <ul>
      <li>
        <a [routerLink]="['']">Home</a>
      </li>
      <li>
        <a [routerLink]="['sobre']">Sobre</a>
      </li>
      <li>
        <button type="button" (click)="toggle()">
          <img
            src="./assets/{{ icon }}.svg"
            alt="Clique aqui e mude o Theme do Site para{{ textTheme }}"
          />
        </button>
      </li>
    </ul>
  </header>
</body>
```

src/app/core/components/header/header.component.scss

```js
:host {
  header {
    background-color: var(--primary);
    width: 100%;
    height: 50px;
    padding: 0 20px;

    &, //Referenciando o header, e depois entra no ul, & basicamente é igual a letra e, e depois de estar na tag tal entre na ul.
    ul {
      display: flex;
      align-items: center;
      justify-content: space-between;
      box-sizing: border-box;
    }
    ul {
      li {
        padding: 0 15px 0 0;
        font-weight: 700;
        font-size: 12px;

        &,
        a {
          color: var(--text-menu);
        }
        &:last-child {
          padding: 0;
          button {
            img {
              width: 21px;
            }
          }
        }
      }
    }
  }
}
```

## Passando uma cor, dentro da class

src/app/core/components/footer/footer.component.html

```js
<div>
  <span> Desenvolvido </span>
  <i class="red"> favorite </i>
  <strong>
    Beto <span class="red">Legal</span>
  </strong>
</div>
```

src/app/core/components/footer/footer.component.scss

```js
.red {
  color: rgb(227, 94, 107);
}
```
