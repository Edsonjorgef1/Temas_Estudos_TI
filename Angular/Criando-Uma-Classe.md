Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Para emular o projeto

```js
ng serve -o
```

ou

```js
ng serve --open
```

## Criando uma classe

```js
ng generate class pessoa
```

Repare que o nome pessoa, você pode dar o nome que você quiser

Ele irá criar dois arquivos

pessoa.spec.ts

```js
import { Pessoa } from "./pessoa";

describe("Pessoa", () => {
  it("should create an instance", () => {
    expect(new Pessoa()).toBeTruthy();
  });
});
```

pessoa.ts

```js
export class Pessoa {}
```
