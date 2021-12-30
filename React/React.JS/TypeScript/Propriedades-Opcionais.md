## Types em Objetos

Nunca esquecer de tipar, o objeto que está sendo usado, no caso aqui é o nome e a idade

## Se eu mandar somente o nome e não mandar a idade, eu quero que a propriedade idade seja opcional, idade?:, tem que colocar a interrogação antes dos dois pontos 

```js
function resumo(usuario: {nome: string, idade?: number}) { 
    if(usuario.idade !== undefined) {
        return `Olá ${usuario.nome}, tudo bem? Você tem ${usuario.idade} anos`
    } else {
  return `Olá ${usuario.nome}, tudo bem?`
}
}

let u = {
    nome: 'Bonieky',
}
resumo(u)
```