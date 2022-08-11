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

# Exemplo, teste de calculadora

calculadora.service.ts

```js
/**
 * Serviço responsável por executar as operações da
 * calculadora.
 *
 * @author Beto<gilberto-goncalves@outlook.com.br>
 * @since 1.0.0
 */

import { Injectable } from '@angular/core';

@Injectable()
export class CalculadoraService {
  /* Define as constantes utilizadas
     para identificar as operações de cálculo */
  static readonly SOMA: string = '+';
  static readonly SUBTRACAO: string = '-';
  static readonly DIVISAO: string = '/';
  static readonly MULTIPLICACAO: string = '*';

  constructor() {}

  /**
   * Método que calcula uma operação matemática dado
   * dois números.
   * Suporta as operações soma, subtração, divisão,
   * e multiplicação.
   *
   * @param num1 number
   * @param num2 number
   * @param operacao string Operação a ser executada
   * @return number Resultado da operação
   */
  calcular(num1: number, num2: number, operacao: string): number {
    let resultado: number; // armazena o resultado da operação

    switch (operacao) {
      case CalculadoraService.SOMA:
        resultado = num1 + num2;
        break;
      case CalculadoraService.SUBTRACAO:
        resultado = num1 - num2;
        break;
      case CalculadoraService.DIVISAO:
        resultado = num1 / num2;
        break;
      case CalculadoraService.MULTIPLICACAO:
        resultado = num1 * num2;
        break;
      default:
        resultado = 0;
    }

    return resultado;
  }
}

```

calculadora.service.spec.ts

```js
import { TestBed, inject } from "@angular/core/testing";

import { CalculadoraService } from "./calculadora.service";

describe("CalculadoraService", () => {
  beforeEach(() => {
    TestBed.configureTestingModule({
      providers: [CalculadoraService],
    });
  });

  it("should ...", inject(
    [CalculadoraService],
    (service: CalculadoraService) => {
      expect(service).toBeTruthy();
    }
  ));

  it("deve garantir que 1 + 4 = 5", inject(
    [CalculadoraService],
    (service: CalculadoraService) => {
      let soma = service.calcular(1, 4, CalculadoraService.SOMA);
      expect(soma).toEqual(5);
    }
  ));

  it("deve garantir que 1 - 4 = -3", inject(
    [CalculadoraService],
    (service: CalculadoraService) => {
      let subtracao = service.calcular(1, 4, CalculadoraService.SUBTRACAO);
      expect(subtracao).toEqual(-3);
    }
  ));

  it("deve garantir que 1 / 4 = 0.25", inject(
    [CalculadoraService],
    (service: CalculadoraService) => {
      let divisao = service.calcular(1, 4, CalculadoraService.DIVISAO);
      expect(divisao).toEqual(0.25);
    }
  ));

  it("deve garantir que 1 * 4 = 4", inject(
    [CalculadoraService],
    (service: CalculadoraService) => {
      let multiplicacao = service.calcular(
        1,
        4,
        CalculadoraService.MULTIPLICACAO
      );
      expect(multiplicacao).toEqual(4);
    }
  ));

  it("deve retornar 0 para operação inválida", inject(
    [CalculadoraService],
    (service: CalculadoraService) => {
      let operacaoInvalida = service.calcular(1, 4, "%");
      expect(operacaoInvalida).toEqual(0);
    }
  ));
});
```
