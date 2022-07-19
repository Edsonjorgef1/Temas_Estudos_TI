Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ngDoCheck

O ngDoCheck() detecta e age mediante mudanças que o Angular não consegue detectar sozinho. Entretanto é sempre bom ficar atento a utilização desse método, pois uma simples troca de foco de um campo de texto por exemplo, já seria suficiente para disparar esse método, o que pode prejudicar o desempenho da sua aplicação. Isso ocorre porque o ngDoCheck() é executado sempre que o detector de mudanças do angular é chamado, mesmo que não haja nenhuma alteração. Esse método é executado executado sempre após o ngOnChanges()

É recomendado que nunca se utilize o ngDoCheck() e o ngOnChanges() para checar mudanças em propriedades @Input ao mesmo tempo, pois isso poderá causar problemas.

Este evento é disparado sempre que as propriedades de entrada de um componente
são verificadas

```js
ngDoCheck();
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
