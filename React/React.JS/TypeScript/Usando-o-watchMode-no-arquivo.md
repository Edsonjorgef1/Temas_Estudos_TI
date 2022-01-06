Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Usando o watchMode no arquivo

Modo de escuta, monitorando o arquivo, verificando se contém erros, qualquer alteração, ele vai monitorar

tsc src/script.ts -w

Aqui estou monitorando este aquivo, quando eu salvo alguma alteração, ele vai monitorar o código

```js
const nome: string = 'Beto'

function blabla(n1: number): string {
    return 'O parâmetro era: '+n1'
}
blabla(12)
```