## ForEach

Vai fazer um loop dentro do array e vai fazer alguma coisa

```js
let names = ['beto', 'mae']

names.forEach(function(nome){
    console.log(nome.toUpperCase())
})
```
## Verificando string, dentro do array

```js
let names = ['beto', 'mae', 30]

names.forEach(function(nome){
    if(typeof nome === 'string') {
    console.log(nome.toUpperCase())    
    } else {
        console.log(nome)
    }
})
```
