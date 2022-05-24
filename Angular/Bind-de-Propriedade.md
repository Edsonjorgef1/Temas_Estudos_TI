Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Topicos

.Imput, algumas forma do value input

.Utilizando uma expressão, somátoria com o value

.Imagem, abrindo uma imgem, com uma url

app.component.html

```js
<h1>{{ title }}</h1>
<h4>Sub-legenda legal</h4>

<p>Total de nomes: {{ nomes.length }}</p>
<p>Nome Principal: {{ nomePrincipal.nome }}</p>

<div *ngIf="nomes.length <= 4">
  <input type="text" />
  <button>Adicionar</button>
</div>

<ul>
  <li *ngFor="let item of nomes" style="color: #ff0000">
    {{ item.nome }} - {{ item.idade }} anos - {{ item.getTipo() }}
  </li>
</ul>

<p *ngIf="nomes.length > 2">Tem muitos nomes cadastrados</p>

<div *ngIf="showAviso">{{ avisoMsg }}</div>

<!-- Formas de como utilizar o value no input -->
<!-- <input type="text" value="nome" /> -->
<!-- ou -->
<!-- <input type="text" value="{{ nomePrincipal.nome }}" /> -->
<!-- ou -->

<!-- Passando uma empressão -->
<input type="text" [value]="1 + 2" />

<!-- Passando uma variavel -->
<input type="text" [value]="nomePrincipal.nome" />
<!-- ou -->
<!-- Passando uma variavel -->
<input type="text" bind-value="nomePrincipal.nome" />

<!-- Condicional, baseado em alguma variavel especifica -->
<input type="text" [disabled]="true" />

<!-- ou -->

<input type="text" [disabled]="hideInput" />

<br />
<!-- Aparecendo imagem, atual hoje -->
<img src="{{ imagem }}" />
<!-- Aparecendo imagem, outro jeito, atual hoje -->
<img [src]="imagem" />
<!-- Aparecendo imagem, outro jeito, bind é antigo -->
<img bind-src="imagem" />
```
