Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Retorno void

```js
function removerElemento(el: HTMLElement): {
    el.remove()
}

removerElemento(document.getElementById)('teste')) 
```


```js
function removerElemento(el: HTMLElement): void {
    if(el.classlist) {
    return
    }
    el.remove()
}

removerElemento(document.getElementById)('teste')) 
```

Não espera nada desta função que for utilizada deste type

```js
type QualquerFuncao = () => void

const algo: QualquerFuncao = () => {
    return "bla bla bla" /*Aqui você pode retornar o que você quiser, return true, return 30, qualquer coisa */
}

/*
const blabla = (): void => {
    /*Aqui eu tenho que não retornar nada
}
*/

let retorno = algo()
```

