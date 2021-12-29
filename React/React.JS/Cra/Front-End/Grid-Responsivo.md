Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Grid Responsivo

App.js

```js
//Importando o react
import React from "react";

export default function App() {
  return (
    <>
      <div class="grid-container">
        <div class="grid-child purple">Grid Column 1</div>

        <div class="grid-child green">Grid Column 2</div>
      </div>
    </>
  );
}
```

App.css

```js
.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 20px;
}
```

Link da consulta:

```js
https://coder-coder.com/display-divs-side-by-side/#flexbox-method
```
