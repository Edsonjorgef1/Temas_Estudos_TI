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

mostrarTexto('beto', 'left')
mostrarTexto('Beto', 'rigth')
mostrarTexto('Beto', 'blabla')
```

```js
type VerdadeiroOuFalso = true | false /*ou = boolean*/ 

function temNome(nome: string): VerdadeiroOuFalso {
    if(nome !== '') {
        return true
    } else {
        return false
    }
}
```

```js
type Opcoes = {
    width: numer,
    heigth: numer
}

function configurar(props:{width: Opcoes | 'auto') {

}

configurar({width: 100, heigth: 200})
configurar('auto')
configurar('automatico') /*Não funciona, porque não foi configurado*/
```