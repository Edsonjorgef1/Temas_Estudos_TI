Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Requisição get, fazendo uma requisição para o back-end

Para veficar melhor o aquivo json, procure no google, json viewer, uma extensão que eu gostei do google.
Só adicionar a extensão nop google crome após abrir o link, vai ficar bem organizado o arquivo json

```js
https://chrome.google.com/webstore/detail/json-viewer/gbmdgpbipfallnflgajpaliibnhdgobh/related?hl=pt-BR
```

Para verificar os dados do fetch, para saber se chegou sua requisição, clique f12, abrira o inspecionar do google, depois clique em network, depois em fetch, para verificar a requisição se ela chegou.
Network depois Fetch/XHR

App.js

```js
import { useState } from "react"

function App() {
const [movies, setMovies] = useState([])

 const loadMovies = () => {
 //Preciso acessar o endereço, para dar as informações, fetch
 //Quando estou fazendo a requisição preciso aguardar o retorno da requisição, 
 //then, então faça alguma coisa
 //response, é p resultado da minha url
 fetch('https://api.b7web.com.br/cinema/')
  .then((response) =>{
   return  response.json()
  })
  .then((json)=>{
  setMovies(json)
  })
 }

  return (
    <div className="flex">
      <button className="block" style={{ backgroundColor: "gray", padding: "10px", borderRadius: "10px"}} onClick={loadMovies}> Carregar Filmes </button>

      <div>
       Total de Filmes: {movies.length}
       {/*movies.length, vai mostrar a quantidade de filmes*/}
      </div>
    </div>
  );
}

export default App;

// https://api.b7web.com.br/cinema/


/*
//Dentro da api
// 20211215181534
// https://api.b7web.com.br/cinema/
[
  {
    "titulo": "Quarto 66 e os Segredos Templários - Escape Route",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/quarto-66-e-os-segredos-templarios-escape-route.jpg?"
  },
  {
    "titulo": "Alcatraz: Escapada Impossível 2.0 - Escape Route",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/alcatraz-escapada-impossivel-2-0-escape-route.jpg?"
  },
  {
    "titulo": "Pânico do Expresso do Oriente - Escape Route",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/panico-do-expresso-do-oriente-escape-route.jpg?"
  },
  {
    "titulo": "Eternos",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/eternos.jpg?"
  },
  {
    "titulo": "Encanto",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/encanto.jpg?"
  },
  {
    "titulo": "Ghostbusters: Mais Além",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/ghostbusters-mais-alem.jpg?"
  },
  {
    "titulo": "Clifford: O Gigante Cão Vermelho",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/clifford-o-gigante-cao-vermelho.jpg?"
  },
  {
    "titulo": "Casa Gucci",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/casa-gucci.jpg?"
  },
  {
    "titulo": "Homem-Aranha: Sem Volta para Casa",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/homem-aranha-sem-volta-para-casa.jpg?"
  },
  {
    "titulo": "Resident Evil: Bem-vindo a Raccoon City",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/resident-evil-bem-vindo-a-raccoon-city.jpg?"
  },
  {
    "titulo": "King Richard – Criando Campeãs",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/king-richard-criando-campeas.jpg?"
  },
  {
    "titulo": "Missão Resgate",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/missao-resgate.jpg?"
  },
  {
    "titulo": "Matrix",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/matrix.jpg?"
  },
  {
    "titulo": "Família Monstro 2",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/familia-monstro-2.jpg?"
  },
  {
    "titulo": "Amor, sublime amor",
    "avatar": "https://www.cinesystem.com.br/filmes/images/poster/amor-sublime-amor.jpg?"
  }
]
*/
```

## Este aqui é outro exemplo, como fazer uma requisição

Buscando um cep

```js
https://github.com/gilbertogoncalvesdelima/React-js-Hooks-Buscador-Cep-Api
```