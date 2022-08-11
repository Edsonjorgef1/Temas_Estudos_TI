## ngAfterViewChecked


O ngAfterViewChecked é chamado após o Angular checar as views do componente, assim como as views filhas. Ou seja, é executado uma vez após o ngAfterViewInit() e a cada execução do ngAfterContentChecked().

Ele é executado toda vez que a visualização de um determinado componente foi
verificada pelo algoritimo de detecção de alterações do Angular.

```js
ngAfterViewChecked();
```