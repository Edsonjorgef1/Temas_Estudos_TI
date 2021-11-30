Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Float, Responsivo

App.js

```js
//Importando o react
import React from "react";

export default function App() {
  return (
    <>
      <div class="float-container">
        <div class="float-child">
          <div class="green">Float Column 1</div>
        </div>

        <div class="float-child">
          <div class="blue">Float Column 2</div>
        </div>
      </div>
    </>
  );
}
```

App.css

```js
.float-container {
  border: 3px solid #fff;
  padding: 20px;
}

.float-child {
  width: 50%;
  float: left;
  padding: 20px;
  border: 2px solid red;
}
```

Link da consulta:

```js
https://coder-coder.com/display-divs-side-by-side/#flexbox-method
```
