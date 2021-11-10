## Json

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

Arquivo, json.js

```js
import React from "react";
import data from "../data/data.json";

//Json
const Json = data.map((data) => {
  return (
    <div>
      {data.id}
      <br />
      {data.Nome}
      <br />
      {data.Cpf}
    </div>
  );
});

export default Json;
```

Arquivo, data.json

```js
[
  {
    id: 1,
    Nome: "Gilberto",
    Cpf: "31405459832",
  },
  {
    id: 2,
    Nome: "Elio",
    Cpf: "31405459865",
  },
];
```
