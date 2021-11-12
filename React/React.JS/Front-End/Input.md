Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Input

A tag <input> especifica um campo de entrada onde o usuário pode inserir dados.

Site para mais exemplos, do "input"

```js
https://www.w3schools.com/tags/tag_input.asp
```

Exemplo do input

```js
<input type="text" name="name" />
```

ou

```js
<input type="text" name="name"></input>
```

Exemplo dentro do componente do React, Hooks

```js
import React from "react";

function App() {
  return (
    <div>
      <label>
        Nome:
        <input type="text" name="name" />
      </label>
      <input type="submit" value="Enviar" />
    </div>
  );
}

export default App;
```

O elemento <input> pode ser exibido de várias maneiras, dependendo do atributo type.

Caixa de seleção (Quadrado)

```js
type = "checkbox";
```

Caixa de seleção (Redonda)

```js
type = "radio";
```

Número

```js
type = "number";
```

Texto

```js
type = "text";
```

Senha

```js
type = "password";
```
