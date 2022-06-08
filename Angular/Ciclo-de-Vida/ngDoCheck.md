Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ngDoCheck

Este evento é disparado sempre que as propriedades de entrada de um componente
são verificadas

```js
ngDoCheck();
```

Filhos

## ngAfterContentInit

Este método de ciclo de vida é executado quando o Angular realiza qualquer
projeção de conteúdo as visualizações do componente.

```js
ngAfterContentInit();
```

## ngAfterContentChecked

Este método de gancho de ciclo de vida é executado sempre que o conteúdo do
componente é verificado pelo mecanismo de detecção de alteração do Angular.

```js
ngAfterContentChecked();
```

## ngAfterViewInit

Este método de gancho de ciclo de vida pe executado quando a visualização do
componente foi totalmente inicializada

```js
ngAfterViewInit();
```

## ngAfterViewChecked

Ele é executado toda vez que a visualização de um determinado componente foi
verificada pelo algoritimo de detecção de alterações do Angular.

```js
ngAfterViewChecked();
```

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

```
