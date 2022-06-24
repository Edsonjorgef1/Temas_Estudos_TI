Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

Arquivo karma.conf.js

Configuração dos testes do Karma

Dentro do nosso arquivo json está o karma e jasmine em nossas dependencias.

## Comando para testar

```js
ng test
```

src/app/app.component.spec.ts

Arquivo spec, é o arquivo de teste

```js
import { TestBed } from '@angular/core/testing';
import { RouterTestingModule } from '@angular/router/testing';
import { AppComponent } from './app.component';

describe('AppComponent', () => {
  //describe,irá testar meu AppComponent

  //berforeEach, o que ele faz, antes de cada coisa você irá fazer algo
  beforeEach(async () => {
    await TestBed.configureTestingModule({
      //import
      imports: [RouterTestingModule],
      //declaration
      declarations: [AppComponent],
    }).compileComponents(); //Este compileComponents, ira copilar, tudo
  });
  /********************************************************************** */
  // Aqui o it diz, vou testar se o nosso aplicativo foi criado
  it('should create the app', () => {
    //criando nosso AppComponent para testar
    const fixture = TestBed.createComponent(AppComponent);

    //Aqui está perguntando se a instancia do componente funcionou
    const app = fixture.componentInstance;
    //Aqui ele vai criar e vai falar se e verdadeiro
    expect(app).toBeTruthy();
  });

  /********************************************************************** */

  //Aqui o it diz, vou testar se o meu title está escrito App1
  it(`should have as title 'App1'`, () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app.title).toEqual('App1');
  });

  /********************************************************************** */

  //Aqui o it diz, vou testar se renderizou meu title
  it('should render title', () => {
    const fixture = TestBed.createComponent(AppComponent);
    //Eu quero detectar uma mudança
    fixture.detectChanges();
    const compiled = fixture.nativeElement as HTMLElement;
    //Aqui ele está entrando dentro da class(.content ) depois indo em span, ele veficado o texto
    expect(compiled.querySelector('.content span')?.textContent).toContain(
      'App1 app is running!'
    );
  });
});
/********************************************************************** */
```
