## Styles e Class

## Estilos inline

app.component.html

```js
<!-- 1 Forma de estilização -->
<div style="color: #00ff00">Texto 1</div>

<!-- 2 Forma de estilização -->
<div
  [style]="{
    width: '100px',
    heigth: '100px',
    fontSize: tamanhoFonte,
    backgroundColor: 'blue'
  }"
>
  Texto class 1
</div>

<!-- 3 Forma de estilização -->
<div [style.width.px]="100">Texto 3</div>
```

## Estilos Class

```js
<!-- 4 Forma de estilização (Vericar como adicionar class nas divs) -->
<div [class]="{ class1: false, class2: false }">Texto Class</div>

<!-- 5 Forma de estilização -->
<div [class]="{ menu: true, ativo: false }">Texto menu 1</div>
<div [class]="{ menu: true, ativo: true }">Texto menu 2</div>

<!-- 6 Forma de estilização  -->
<div [class.teste]="true">Texto</div>

<!-- 7 Forma de estilização  -->
<div [class]="{ menu: false }">Texto</div>
```

## Estilos Class 2 Opção

app.component.html

```js
<div class="bg">
  <h3>Esse é meu primeiro componente</h3>
  <p>Que legal</p>
</div>
```

app.component.css

```js
.bg {
  background-color: #cccccc;
}
```

## Estilos ID

app.component.html

```js
<div id="bg">
  <h3>Esse é meu primeiro componente</h3>
  <p>Que legal</p>
</div>
```

app.component.css

```js
#bg {
  background-color: #cccccc;
}
```
