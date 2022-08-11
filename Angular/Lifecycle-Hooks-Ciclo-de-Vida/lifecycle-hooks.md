## Lifecycle Hooks

Todo componente no angular tem um conjunto de eventos de ciclo de vida(lifecycle hooks) que ocorrem quando um componente é criado, renderizado, tem o valor de suas propriedades alteradas ou é destruído. o Angular invoca uma séries de métodos (hooks), que são executados no momento em que esses eventos são acionados. Uma aplicação de loja com um carrinho de compras por exemplo, poderia utilizar os lifecycle hooks para detectar mudanças, como adição ou remoção de produtos do carrinho, e atualizar esses dados na tela.

## Conhecendo os lifecycle Hooks

Agora que já vimos a definição dos Lifecycle hooks, vamos conhecer métodos que mencionamos anteriormente. Cada método listado abaixo está associado a uma interface, e cada interface possui apenas um método associado a ela. Cada método possui uma ou mais condições para ser executado, além de ter uma posição fixa (ordem) na sequência do ciclo. A seguir descrevemos os métodos, que estão listados na ordem em que são executados pelo Angular. Os métodos do lifecycle hooks possuem uma nomeclatura própria que utiliza o nome da interface junto do prefixo ng. A interface OnInit por exemplo, possúi um método chamado ngOnInit()

## Exemplo:

app/app.component.ts

```js
import {
  AfterContentChecked,
  AfterContentInit,
  AfterViewInit,
  Component,
  DoCheck,
  OnInit,
} from '@angular/core';

@Component({
  selector: 'app-root',
  template: `{{ valor }}
    <button (click)="adicionar()">Adicionar</button>
    <router-outlet></router-outlet>`,
})
export class AppComponent
  implements
    OnInit,
    DoCheck,
    AfterContentInit,
    AfterContentChecked,
    AfterViewInit
{
  public valor: number = 1;

  constructor() {}

  public adicionar(): number {
    return (this.valor += 1);
  }

  ngOnInit(): void {}

  ngDoCheck(): void {
    console.log('ngDoCheck');
    // Verificando se teve alguma alteração
  }
  ngAfterContentInit(): void {
    console.log('ngAfterContentInit');
    // Carrega no inicio
  }
  ngAfterContentChecked(): void {
    console.log('ngAfterContentChecked');
    //Sempre quando tiver uma alteração, ele vai alterar, ele vai ser chamado ou invocado caso precise
  }
  ngAfterViewInit(): void {
    console.log('ngAfterViewInit');
    //Quando ele ter uma alteração concreta na view ele vai inicia e vai chama a função
  }
  ngAfterViewChecked(): void {
    console.log('ngAfterViewChecked');
    // Carrega no inicio
  }
}