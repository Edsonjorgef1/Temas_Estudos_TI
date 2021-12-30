## Types Literais

Dentro desta variavel só pode ter isso, não pode mudar

```js
let nome: "beto" = "beto"
nome = "beto"
```

```js
const nome: string = "beto"
```

```js
function mostrarTexto(
    texto: string,
    alinhamento: 'left' | 'right' | 'center'
) {
    return `<div style="text-align: ${alinhamento}">${texto}</div>`
}

mostrarTexto('Bonieky', 'left')
mostrarTexto('Bonieky', 'rigth')
mostrarTexto('Bonieky', 'blabla')
```