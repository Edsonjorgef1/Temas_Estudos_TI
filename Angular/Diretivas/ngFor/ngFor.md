Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## NgFor

Repete um nó para cada item de uma lista

## Lista 1

app/primeiro-componente/primeiro-componente.component.html

```js
<!--ngFor = literar uma lista de intens, repetindo elementos aonde ela é usada -->
<div class="div">
  <ul>
    <li *ngFor="let item of [1, 2, 3]">valor: {{ item }}</li>
  </ul>
</div>
```




