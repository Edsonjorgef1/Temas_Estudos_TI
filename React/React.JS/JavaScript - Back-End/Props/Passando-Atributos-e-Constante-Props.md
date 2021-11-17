Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## 1 Exemplo:

Arquivo, Dados.js

Passando conteúdo de uma constante

```js
//Importando o react
import React from "react";
import Dados from "./componentes/Dados";

export default function App() {
  const cnl = "Engenheiro Youtuber";
  const yt = "youtube.com/engenheiroyoutuber";
  const crs = "React.js";

  return (
    <div className="App">
      <section>
        <Dados canal={cnl} youtube={yt} curso={crs} />
      </section>
    </div>
  );
}
```

Arquivo, App.js

Passando atributos para a props

```js
//Importando o react
import React from "react";

export default function Dados(props) {
  // Este (props), aqui desta linha tem que ir para, poder passar atributos para o componente
  return (
    <div className="App">
      <section>
        <p> Canal:{props.canal} </p>
        <p> Youtube: {props.youtube} </p>
        <p> Curso: {props.curso} </p>
      </section>
    </div>
  );
}
```

## 2 Exemplo:

Função que depende das propriedades, retornando um elemento qualquer
valor enviado via props

```js
//Importando o react
import React from "react";

//Função que depende das propriedades, retornando um elemento qualquer
//valor enviado via props
const Display = (props) => {
  return <h1>{props.title}</h1>;
};

function App_function_Component() {
  return (
    <div className="App_function_Component">
      <h1>Componente principal</h1>
      <Display title="teste" />
    </div>
  );
}
//Exportando Componente
export default App_function_Component;
```
