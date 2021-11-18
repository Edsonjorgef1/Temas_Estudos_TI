Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## FormatName(user)

### Exemplo 1

o exemplo abaixo, incorporamos o resultado da chamada de uma função JavaScript,
formatName(user), dentro de um elemento <h1>.
Uma das vangagens, este exemplo, é muito util, quando você precisa replicar o mesmo nome em vários
lugares assim deixando seu codigo menor

```js
import React from "react";

function formatName(user) {
  return user.firstName + " " + user.lastName;
}

const user = {
  firstName: "Harper",
  lastName: "Perez",
};

const element = <h1>Hello, {formatName(user)}!</h1>;

function App_function_Component() {
  return (
    <div className="App_function_Component">
      <h1>Teste</h1>
      {element}
    </div>
  );
}
export default App_function_Component;
```
