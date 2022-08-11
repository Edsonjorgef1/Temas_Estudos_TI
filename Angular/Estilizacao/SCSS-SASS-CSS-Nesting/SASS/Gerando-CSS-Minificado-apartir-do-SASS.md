Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Gerando CSS Minificado a partir do SASS

Podemos gerar CSS minificado facilmente com o interpretador

Na saída do comando de watch, vamos mudar a extensão

De: styles.css

Para: styles.min.css

sass --watch sass/styles.sass:css/styles.min.css --style compressed

Irá gerar um arquivo mimificado, para ficar mais leve

arquivo gerado

styles.min.css

```js
body{background-color:#d43a3a;width:100%;heigth:100%}.container{background:#add8e6}#title{color:#d43a3a;text-align:center}/*# sourceMappingURL=styles.min.css.map */
```
