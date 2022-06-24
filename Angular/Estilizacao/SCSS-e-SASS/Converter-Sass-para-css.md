Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Converter Sass para Css

css/styles.css

//convertido depois do comando

```js
body { background-color: #d43a3a; width: 100%; heigth: 100%; }

.container { background: lightblue; }

h1 { color: #d43a3a; text-align: center; }

/_# sourceMappingURL=styles.css.map _/
```

Depois de convertido gera um arquivo, automático

css/styles.css.map

```js
{"version":3,"sourceRoot":"","sources":["../sass/styles.sass"],"names":[],"mappings":"AAGA;EACE,kBAJS;EAKT;EACA;;;AAEF;EACC;;;AAED;EACC,OAZU;EAaV","file":"styles.css"}
```

sass/styles.sass

```js
$bg-color: #CCC

body
  background-color:  $bg-color
  width: 100%
  heigth: 100%

.container
 background: lightblue

h1
 color: $bg-color
 text-align: center
```

index.html

```js
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <container>
      <h1>Olá</h1>
    </container>
  </body>
</html>

```

Comando para converter

```js
sass sass/styles.sass css/styles.css
```

Comando para converter de sass para css, assim que editar ele já converte e
atualiza automático no google crome, lembrando que estou utilizando a extensão
live server. Este --watch que foi adicionado no comando ele serve para ficar
olhando o código quando ele é alterado, assim convertendo em tempo real

```js
sass --watch sass/styles.sass css/styles.css
```
