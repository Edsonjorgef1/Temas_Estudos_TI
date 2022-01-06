Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Parametros de funções

```js
UpperCase, jogar para caixa alta a primeira letra

function firstLetterUpperCase(name: string) {
 let fistLetter = name.chartAt(0).toUpperCase() /* ChartAt, vai pegar a primeira letra na posição 0*/
 return firstLetter+name.substring(1)
}

firstLetterUpperCase(90)
```