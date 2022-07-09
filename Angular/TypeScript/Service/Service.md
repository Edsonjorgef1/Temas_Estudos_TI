Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Criando nosso service

Nosso service é responsavel por todas as operações relacionadas a tarefas,
listagem, cadastro, edição, remoção, atualização de status e o que for
necessario, ficará neste aquivo.

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
