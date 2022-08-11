Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```
## String-Interpolation

Quando optamos por realizar o binding dos atributos da classe com os atributos HTML dos elementos do template utilizando string interpolation, fazemos uso da mesma sintaxe utilizada para exibir dados ao usuário. Isto é, utilizamos a sintaxe {{ atributo_da_classe }} onde desejamos que o valor desse atributo seja impresso:


interpolation.component.html

```js
<img src="{{ imgURL }}" alt="Imagem" />

<a href="{{ url }}" title="Acessar">Acessar</a>
```

interpolation.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-contador',
  templateUrl: './contador.component.html',
  styleUrls: ['./contador.component.scss'],
})
export class ContadorComponent implements OnInit {
  public imgURL = 'https://devmedia.com.br/logo.png';
  public url = 'https://engenheiroyoutuber.com.br';

  constructor() {}

  ngOnInit(): void {}
}
```

No exemplo acima, usamos o nome do atributo normalmente e atribuímos a ele uma propriedade da classe do componente usando {{ }} entre aspas.