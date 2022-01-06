
Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Comando converter, js para typescript

tsc mais o nome do arquivo que você deseja fazer a tradução
tsc script.ts

ou

src/script.ts --outDir public, deste jeito vai para a pasta correta dele

ou

tsc src/script.ts

Ele vai converter o arquivo e vai aparecer como script.js, depois impressionante

Agora se der erro na tradução, temos que configurar, para colocar regras

tsc src/script.ts --noEmitOnError
Se tiver algum erro ele vai parar a execução e não vai gerar o arquivo