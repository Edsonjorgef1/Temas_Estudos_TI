Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

Identação serve para organizar o código, uma das formas para você organizar é
selecionar o seu código e depois clicar com o botão direito e clicar em Format
Selection. Na parte inferior do VsCode, contém o nome chamado Space:aqui contém
o numero dos espaços da identação, se quiser mudar a quantidade de espaços só
clicar.

component (Sem identação, Não está organizado olhe como é ruim de acompanhar
aonde começa e termina a tag)

```js
import React from "react";
import { CartArea, CartHeader, CartIcon CartBody } from "./styled";

export default () => {
return (
<CartArea>
{/*Cabeça do meu carrinho*/}
<CartHeader>
<CartIcon src="/assets/cart.png" />
</CartHeader>
{/*Corpo do meu carrinho*/}
<CartBody></CartBody>
</CartArea>
);
};
```

component (Com identação, organizado, melhor para visualizar aonde abre a tag e
aonde fecha)

```js
import React from "react";
import { CartArea, CartHeader, CartIcon CartBody } from "./styled";

export default () => {
  return (
    <CartArea>
      {/*Cabeça do meu carrinho*/}
      <CartHeader>
        <CartIcon src="/assets/cart.png" />
      </CartHeader>
      {/*Corpo do meu carrinho*/}
      <CartBody></CartBody>
    </CartArea>
  );
};
```
