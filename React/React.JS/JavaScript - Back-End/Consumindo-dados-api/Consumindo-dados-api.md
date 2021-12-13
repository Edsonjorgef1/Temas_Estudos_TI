Arquivo, App.js

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Consumindo dados api com React

Vamos utilizar uma api externa, vai estar retornando os dados para nossa aplicação web, nossa aplicação 
web vai estar manipulando os dados e apresentando para o usuário.
Primeiro será apresentado como utilizar o axios para conectar React com API.
Em seguida como consumir com React os dados retornado da API.
Para finalizar será apresentado como listar os registros retornado da API.

Pegando api deste site:
tvmaze.com/search?q=star+wars

Api:
api.tvmaze.com/search/shows?q=star%20wars

Para buscar determinado, nome, você deve deixar o link da api assim:
api.tvmaze.com/search/shows?q=
Adicionar no arquivo api.js


Site, descrição e como instalar o axios:
https://www.npmjs.com/package/axios#axios-api

Instalando axios:
npm install axios

App.js

```js
import React, { Component } from "react";
import api from './api'

class App extends Component{

state={
filmes: [],
}

//ComponetDidMount, serve para buscar os dados da api, chamado imediatamente apos alguma atualização ocorrer
async componentDidMount(){

const response = await api.get('batman') // Aqui dentro vai a busca, poderia fazer um input, e fazer a busca ai dentro

//console.log(response.data)

this.setState({ filmes: response.data})
} 

render(){

  const { filmes } = this.state

return(
<div>
<h1>Listar os Filmes</h1>
{/* {console.log(filmes)} */}
{filmes.map(filme => (
<li key={filme.show.id}> 
<h2>
<strong>Título: </strong>
{filme.show.name}
</h2>
<p>
{filme.show.url}
</p>


</li>
))}
</div>
)
}
}

export default App;
```

api.js
```js
import axios from 'axios';

const api = axios.create({
baseURL: 'https://api.tvmaze.com/search/shows?q='  // 1 - Aqui se você colocar o link completo ele pucha os dados, name e url. 2 Agora se deseja pesquisar algumam coisa dentro do link, deve deixar o link, desta forma, depois do =, tiramos, o resto, ai só adicionar, no codigo acima 
//const response = await api.get('batman')
})

export default api
```