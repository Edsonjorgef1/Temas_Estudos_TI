## Bootstrap

Site:

```js
https://getbootstrap.com
```

Comando:

```js
npm install --save bootstrap@3
```

@3 significa versão 3

ou

```js
npm install bootstrap --save
```

ou

```js
yarn add bootstrap
```

## Estilizando o Css, boostrap

Você também pode copiar o link, CSS

Site, Link

```js
https://getbootstrap.com/docs/5.1/getting-started/introduction/
```

React.js, copiar o link, dentro da pasta "public" depois entrar no arquivo
"index.html'

Copie e cole a folha de estilo <link> dentro do <head> para carregar o CSS, com
o bootstrap.

```js
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
```

Site:

```js
https://getbootstrap.com/
```

src/index.html

```js
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>GerenciadorTarefas</title>
    <base href="/" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link rel="icon" type="image/x-icon" href="favicon.ico" />

    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3"
      crossorigin="anonymous"
    />

  </head>
  <body>
    <app-root></app-root>
  </body>
</html>

```
