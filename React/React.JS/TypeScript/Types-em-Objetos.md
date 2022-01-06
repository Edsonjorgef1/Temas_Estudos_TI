Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Types em Objetos

Nunca esquecer de tipar, o objeto que está sendo usado, no caso aqui é o nome e a idade

```js
function resumo(
usuario: {nome: string, idade: number},
outro: {}
) { /*string; funciona, mas eu acho melhor, string,*/

    return `Olá ${usuario.nome}, tudo bem? Você tem ${usuario.idade} anos`
}

let u = {
    nome: 'Bonieky',
    idade: 90
}
resumo(u)
```