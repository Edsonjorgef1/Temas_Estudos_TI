Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Inferência literal


```js
function fazerRequisicao(url: string, method; 'GET' | 'POST') {
    // ....
}

type Methods = 'GET' | 'POST'

let url = "https://google.com.br"
let method: Methods = 'GET'
fazerRequisicao(url, method)
```


```js
function fazerRequisicao(url: string, method; 'GET' | 'POST') {
    // ....
}

type RequestDetails = {
    url: string,
    method: 'GET' | 'POST'
}

let req: RequestDetails = {
    url: 'https://www.google.com.br',
    method: 'GET'
}

req.method = 'POST'

fazerRequisicao(req.url, req.method)
```