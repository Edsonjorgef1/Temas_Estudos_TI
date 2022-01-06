Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Type e Interface como usar e diferenças

```js
type NomeCompleto = string
```

```js
let nome: string = "Beto"
```

```js
type Idade = string | number
let idade: Idade = 90
```

```js
function mostrarIdade(i: Idade): Idade {
    return i
}
```

```js
function resumo(usuario: {nome: string, idade: number}) {
    return `Olá ${usuario.nome}, você tem ${usuario.idade} anos`
}
resumo({
    nome: "Beto",
    idade: 90
})
```
## Definindo types

Desta forma ele não é alteravel

```js
type User = {
    nome: string,
    idade: number
}

function resumo(usuario: User) {
    return `Olá ${usuario.nome}, você tem ${usuario.idade} anos`
}
resumo({
    nome: "Beto",
    idade: 90
})
```

## Definindo com Interfaces 1

Desta forma ele é alteravel

```js
interface User {
    nome: string,
    idade: number
}

function resumo(usuario: User) {
    return `Olá ${usuario.nome}, você tem ${usuario.idade} anos`
}
resumo({
    nome: "Beto",
    idade: 90
})
```

## Definindo com Interfaces 2

Desta forma ele é alteravel

```js
interface User {
    nome: string
}

interface User {
    idade: number
}

function resumo(usuario: User) {
    return `Olá ${usuario.nome}, você tem ${usuario.idade} anos`
}
resumo({
    nome: "Beto",
    idade: 90
})
```









