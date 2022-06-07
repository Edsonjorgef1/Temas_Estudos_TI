Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Criando nosso service

```js
ng g s \gerandoDentroDesteDiretório\nomeDoService
```

Aqui está sem o arquivo para teste unitário

```js
ng g s \users\users --spec=false
```

ou Com o arquivo para teste unitário

```js
ng g s \users\user
```

## Arquivo Criado

app/usersuser.service.ts

```js
import { Injectable } from "@angular/core";

@Injectable({
  providedIn: "root",
})
export class UsersuserService {
  constructor() {}
}
```
