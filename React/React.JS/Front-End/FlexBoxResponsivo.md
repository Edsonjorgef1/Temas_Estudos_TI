Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## FlexBox Responsivo

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
