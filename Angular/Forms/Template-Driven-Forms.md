Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Template-Driven forms

Template-Driven forms é um tipo de formulário mais simples de implementar, dada a sua proximidade em relação a como criamos formulários apenas com HTML. Por exemplo, nessa abordagem uma das formas de validação dos campos pode ser feita no próprio template do componente, usando um atributo de validação, como required, nativa do próprio HTML. Nessa forma de criar formulários usamos a diretiva ngModel para fazer a vinculação (two-way data bindings) entre o componente e o elemento do template.

O projeto angular que usaremos como exemplo para demonstrar as capacidades básicas de cada forma de criar formulários será um cadastro com poucos campos, nome, telefone e endereço. Ao clicar no botão "Gravar" será exibido o valor de cada campo no console.

Em um projeto Angular já criado, devemos configurar o módulo responsável pelo funcionamento desse tipo de formulário para então termos acesso as suas funcionalidades. Para fazer isso deveremos adicionar a diretiva import { FormsModule} from '@angular/forms'; no arquivo app.module.ts, conforme a Linha 3 do Código 1.

app.module.ts

```js
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule} from '@angular/forms'; //Linha 3
import { AppComponent } from './app.component';
import { TemplateFormsComponent } from './template-forms.component';

@NgModule({
  declarations: [
    AppComponent,
    TemplateFormsComponent
  ],
  imports: [
    BrowserModule,
    FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Agora, podemos criar o nosso formulário.

No template de um componente devemos inserir o HTML contendo as diretivas e atributos de formulário, conforme o Código 2.

```js
<form (ngSubmit)="onSubmit(f)" #f="ngForm">
   <div>
      <label for="nome">Nome:</label>
      <input id="nome" name="nome" ngModel type="text">
   </div>
   <div>
      <label for="telefone">Telefone:</label>
      <input id="telefone" name="telefone" ngModel type="tel">
   </div>
   <div>
      <label for="endereco">Endereco:</label>
      <input id="endereco" name="endereco" ngModel type="texto">
   </div>
   <div>
      <button type="submit">Gravar</button>
   </div>
</form>
```

Explicando o código, na tag <form> colocamos uma variável chamada #f, que usaremos para acessar os campos do formulário e realizar ações baseadas em seus valores, tais como permitir que o botão de enviar fique ativo se estiverem preenchidos. Feito isso, em cada tag <input> adicionamos a diretiva ngModel para que o bind possa acontecer.

Agora, no nosso código do componente criaremos a função onSubmit() (Código 3), que vai apenas ler os valores dos inputs por enquanto.

```js
import { Component,OnInit } from '@angular/core';
import { NgForm } from '@angular/forms';

@Component({
  selector: 'app-template-forms',
  templateUrl: './template-forms.component.html',
  styleUrls: ['./template-forms.component.css']
})
export class TemplateFormsComponent implements OnInit {
  constructor() { }
  ngOnInit() { }

  onSubmit(form: NgForm) {
    let dados = `
    Nome: ${form.value.nome}
    Telefone: ${form.value.telefone}
    Endereço: ${form.value.endereco}`;

    console.log(dados);
  }
}
```

Observando a função onSubmit() vemos que nela recuperamos qualquer valor digitado nos inputs, por meio da variável form.value, concatenado com o nome do campo e com isso conseguimos exibi-los no console.

Da forma como implementamos o código não temos nenhuma validação ainda. Se clicarmos no botão “Gravar” os nomes dos campos serão exibidos no console sem seus respectivos valores, caso estejam em branco, pois não implementamos nenhuma restrição quanto a isso.

Para corrigir esse comportamento, vamos adicionar o atributo de validação required nos campos para habilitar o botão “Gravar” passará a estar inicialmente desabilitado através do atributo disabled. Assim, somente quando os campos forem preenchidos e o formulário for considerado válido o botão “Gravar” será habilitado. Para isso, faremos algumas alterações no template, conforme o Código 4.

Código 4. Adição dos atributos de validação no formulário

```js
<form (ngSubmit)="onSubmit(f)" #f="ngForm">
   <div>
      <label for="nome">Nome:</label>
      <input id="nome" name="nome" ngModel type="text" required>
   </div>
   <div>
      <label for="telefone">Telefone:</label>
      <input id="telefone" name="telefone" ngModel type="tel" required>
   </div>
   <div>
      <label for="endereco">Endereco:</label>
      <input id="endereco" name="endereco" ngModel type="texto" required>
   </div>
   <div>
      <button type="submit" [disabled]="f.form.invalid">Gravar</button>
   </div>
</form>
```

A parte mais importante desse código é quando atribuímos a expressão f.form.invalid o atributo disabled do elemento button. Dessa forma, utilizamos o mecanismo de validação nativo do HTML para que disabled seja true enquanto o formulário for inválido. No momento em que o formulário passar a ser válido, disabled receberá false e o botão poderá ser clicado.

Com isso, conseguimos implementar o Template-Driven form em nosso projeto.