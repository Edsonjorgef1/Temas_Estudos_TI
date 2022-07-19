Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ngOnInit()

O ngOnInit é um dos lifecycle hooks mais comuns por ser necessário para a maioria dos projetos. Ao criar um componente através do angular-cli, o ngOnInit é automaticamente implementado na classe.

É dentro do ngOnInit que o desenvolvedor poderá adicionar todo o código que precisa ser executado quando o componente for inicializado.

Uma dúvida muito frequente é: Porque não usar o construtor ao invés do ngOnInit()? O principal motivo é que o construtor da classe fica fora do controle do Angular. Por ser executado diretamente pela engine JavaScript do navegador, o Angular não tem como informar quando o construtor foi chamado/executado ou quando concluiu sua execução.

Por esse motivo o método ngOnInit existe: para informar que o componente foi inicializado, garantindo por exemplo, que todos os bindings estarão disponíveis para utilização.


Este evento é inicializado após o Angular exibir pela primeira vez as
propriedades vinculadas aos dados ou quando o componente foi inicializado. Este
evento é usado principalmente em um componente para inicializar dados em
componente.

Ele é executado após o Angular definir e exibir os dados das propriedades decoradas com @Input pela primeira vez. O ngOnInit é executado apenas uma vez após o primeiro ngOnChanges().

app.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-root",
  template: "<router-outlet></router-outlet>",
})
export class AppComponent implements OnInit {
  constructor() {}
  ngOnInit(): void {
    setTimeout(() => {
      console.log(1);
    }, 5000);
  }
}
```
