## Retorno de uma função


UpperCase, jogar para caixa alta a primeira letra

```js
function firstLetterUpperCase(name: string): string {
 let fistLetter = name.chartAt(0).toUpperCase() /* ChartAt, vai pegar a primeira letra na posição 0*/
 return firstLetter+name.substring(1)
}

let nome = firstLetterUpperCase('beto')
```

## Somando dois nomes

```js
function somar(n1, n2) {
    return n1 + n2
}

let alguma = somar('beto', 'Mae')
```

## Tipando a entrada e a saída

```js
function somar(n1: number, n2: number): number {
    return n1 + n2  
}

let alguma = somar(10, 30)
```