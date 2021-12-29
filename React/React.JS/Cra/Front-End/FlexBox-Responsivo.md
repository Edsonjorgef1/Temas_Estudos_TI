Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## FlexBox, Responsivo (1)

Este metodo aqui, quando diminui a tela a div vai para baixo

App.js

```js
//Importando o react
import React from "react";

export default function App() {
  return (
    <>
      <div class="wrap">
        <div class="box">1</div>
        <div class="box">2</div>
        <div class="box">3</div>
      </div>
    </>
  );
}
```

App.css

```js
.wrap {
  display: flex;
}
.box {
  height: 150px;
  border: 1px solid green;
  flex: 1;
  margin: 25px;
  text-align: center;
  line-height: 150px;
  font-size: 36px;
}
.box:first-child {
  order: 1;
}
.box:nth-child(2) {
  order: 2;
}
.box:nth-child(3) {
  order: 3;
}
@media screen and (max-width: 760px) {
  .wrap {
    flex-direction: column;
  }
  .box:nth-child(2) {
    order: 3;
  }
  .box:nth-child(3) {
    order: 2;
  }
}
```

Link da consulta:

```js
https://stackoverflow.com/questions/31830731/div-re-order-with-css
```

## FlexBox Responsivo (2)

Este método é bem legal, você dimuni a tela e tudo que está
no meio da div, acompanha proporcionalmente.

App.js

```js
//Importando o react
import React from "react";

export default function App() {
  return (
    <>
      <div class="flex-container">
        <div class="flex-child magenta">Flex Column 1</div>

        <div class="flex-child green">Flex Column 2</div>
      </div>
    </>
  );
}
```

App.css

```js
.flex-container {
  display: flex;
}

.flex-child {
  flex: 1;
  border: 2px solid yellow;
}

.flex-child:first-child {
  margin-right: 20px;
}

```

Link da consulta:

```js
https://coder-coder.com/display-divs-side-by-side/#flexbox-method
```
