## Array, com string

Sem typeScript

```js
let nomes = ['beto', 'pedro', 'augusto']
```

Com typeScript

```js
let nomes: string[] = ['beto', 'pedro', 'augusto']
```

let nomes: (Aqui declara qual o tipo da minha variavel, que no caso é string[]) = ['beto', 'pedro', 'augusto']

## Array, com number

Sem typeScript

```js
let idades = [90, 15, 20]
```

Com typeScript

```js
let idades: number[] = [90, 15, 20]
```

let idades: (Aqui declara qual o tipo da minha variavel, que no caso é number[]) = [90, 15, 20]

ou

Com typeScript, é a mesma coisa de cima, só outra forma

```js
let idades: Array<number> = [90, 15, 20]
```

## Passando, um número para dentro do array

Com typeScript

```js
let idades: number[] = [90, 15, 20]
```

Digamos que você vai passar um numero para dentro array, você pode. Agora se for passar string ele vai dar erro

```js
numeros.push(15)
```


