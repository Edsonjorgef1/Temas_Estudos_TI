Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Reactive Forms

Reactive forms é um tipo de formulário pelo qual temos todo o controle do comportamento dos campos do formulário via componente. Nesse caso, moldamos as validações e o bind dos campos programaticamente pelo TypeScript e vinculamos no template.

Neste tipo de formulário não usamos a diretiva ngModel para fazermos o bind. Em vez disso temos diversas classes que permitem a manipulação dos elementos de formulário, que possibilitam a customização deles.

Neste artigo vamos destacar as duas dessas classes, FormControl e FormGroup.

FormControl permite a criação dos campos que usaremos em nosso formulário, ao criar uma instância, podemos definir se o campo terá alguma validação.
FormGroup usamos para agrupar os campos criados (FormControl). Ao criarmos um objeto dessa classe, iremos fazer a referência no arquivo do templateUrl na tag <form>.
Vamos ver na prática como isso tudo funciona.

Em um projeto Angular já criado, teremos que implementar o módulo responsável pelo funcionamento desse tipo de formulário. Para fazer isso, deveremos adicionar a diretiva import { ReactiveFormsModule } from '@angular/forms'; no arquivo app.module.ts, conforme o Código 5.

Código 5. Colocar o import ReactiveFormsModule no arquivo app.module.ts

```js
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { ReactiveFormsModule } from '@angular/forms';
import { AppComponent } from './app.component';
import { ReactiveFormsComponent } from './reactive-forms.component';

@NgModule({
  declarations: [
    AppComponent,
    ReactiveFormsComponent
  ],
  imports: [
    BrowserModule,
    ReactiveFormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Para fins didáticos, colocaremos no construtor do componente as funcionalidades para montar o formulário. Nesse caso, usaremos a classe FormGroup e passaremos para quais serão os campos que vão compor o formulário. Aqui, já poderemos definir quais serão os campos obrigatórios usando no construtor da classe FormControl o atributo Validators.required, de acordo com o Código 6.

```js
import { Component,OnInit } from '@angular/core';
import { FormGroup, FormControl, Validators } from '@angular/forms';

@Component({
  selector: 'app-reactive-forms',
  templateUrl: './reactive-forms.component.html',
  styleUrls: ['./reactive-forms.component.css']
})
export class ReactiveFormsComponent implements OnInit {

formularioCadastro : FormGroup;

  constructor() {

  this.formularioCadastro = new FormGroup({
    'nome': new FormControl(null, Validators.required),
    'telefone': new FormControl(null, Validators.required),
    'endereco': new FormControl(null, Validators.required)});
  }

  ngOnInit() { }

  onSubmit(){
    let dados = `
    Nome: ${this.formularioCadastro.value.nome}
    Telefone: ${this.formularioCadastro.value.telefone}
    Endereço: ${this.formularioCadastro.value.endereco}`;

    console.log(dados);
  }
}
```

Código 6. Criação dos campos que pertencerão ao formulário e suas validações

Na função onSubmit() do código acima, conseguimos recuperar os valores que digitamos nos campos do templateUrl que estão vinculados ao formularioCadastro (FormGroup), logo eles serão exibidos no console.

Agora, no arquivo do templateUrl, deveremos fazer a referência aos campos que definimos. Para isso colocaremos na tag <form> o nome do formGroup (formularioCadastro) adicionando a propriedade [formGroup], e em cada tag <input>, deveremos por formControlName com os mesmos nomes que criamos na inicialização do formulário no Construtor do Component. Código 7.

Código 7. Adaptação do templateUrl para poder trabalhar com Reactive form

```js
<form [formGroup]="formularioCadastro" (ngSubmit)="onSubmit()">
    <div>
        <label for="nome">Nome:</label>
        <input id="nome" name="nome" type="text" formControlName="nome">
    </div>
    <div>
        <label for="telefone">Telefone:</label>
        <input id="telefone" name="telefone" type="tel" formControlName="telefone">
    </div>
    <div>
        <label for="endereco">Endereco:</label>
        <input id="endereco" name="endereco" type="texto" formControlName="endereco">
    </div>
    <div>
        <button type="submit" [disabled]="formularioCadastro.invalid">Gravar</button>
    </div>
</form>
```

Para complementar, colocaremos uma validação no botão. Na tag <button> usaremos o atributo [disabled] para somente habilitá-lo quando os campos forem preenchidos, assim evitando que no console seja exibido os valores dos campos vazios ao pressionar o botão.

Com isso, conseguimos implementar o Reactive form em nosso projeto.

Como vimos neste artigo, tivemos uma visão geral dos tipos de formulário disponíveis na API do Angular e como implementar em um projeto existente. Nesse caso cabe ao desenvolvedor escolher qual irá atender melhor a sua necessidade.

Conclusão

A API do Angular nos permite utilizar duas abordagens para a criação de formulários em um mesmo projeto, as quais vimos neste artigo.

O Template-Driven Form é recomendável em formulários mais simples, sem validações muito complexas, atendo a maioria dos casos. Para formulários mais elaborados é recomendável utilizar o Reactive Form, pois permite um maior controle no comportamento do formulário via código TypeScript.