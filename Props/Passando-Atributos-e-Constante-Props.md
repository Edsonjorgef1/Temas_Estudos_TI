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
        <Dados canal={cnl} youtube={yt} curso={srs} />
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
