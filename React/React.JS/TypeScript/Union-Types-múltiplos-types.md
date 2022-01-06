Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Union Types múltiplos types

```js
let idade: string | number = 90

idade = document.getElementById("idade").innerHTML
```

```js
function mostrarIdade(idade; string | number) {
    if(typeof idade === 'string') {
        console.log( idade.toUpperCase())
    } else {
    console.log(idade)
    }
}
mostrarIdade(90)
mostrarIdade('90')
```