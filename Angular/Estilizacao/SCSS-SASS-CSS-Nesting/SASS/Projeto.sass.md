Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Projeto em Sass

index.html

```js
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="css/styles.css" />
    <title>Intro SASS</title>
  </head>
  <body>
    <div class="container">
      <h1 id="title">Olá</h1>
    </div>
  </body>
</html>

```

sass/styles.sass

No SASS não precisa de ; ele é mais resumido e também a {}

```js
$bg-color: #d43a3a
$font-color: #000

body
  background-color:  $bg-color
  width: 100%
  heigth: 100%

.container
 background: lightblue

#title
 color: $bg-color
 text-align: center
```
