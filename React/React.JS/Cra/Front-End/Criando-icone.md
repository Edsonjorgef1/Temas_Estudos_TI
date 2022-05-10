Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

assets/cart.png Dentro da pasta assets, vai conter uma imagem cart.png

components/Cart/index.js

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

App.js

```js
import React from "react";
import { Container, Menu, PageBody } from "./AppStyled";

import HomeScreen from "./pages/HomeScreen";
import Tela2Screen from "./pages/Tela2Screen";

import PrivateRoute from "./components/PrivateRoute";
import MenuItem from "./components/MenuItem";
import Cart from "./components/Cart";

export default () => {
  const name = useSelector(state => state.user.name);

  return (
    <BrowserRouter>
      <Container>
        <Menu>
          <MenuItem icon="/assets/store.png" link="/" />
          <MenuItem icon="/assets/order.png" link="/orders" />
          <MenuItem icon="/assets/profile.png" link="/profile" />
        </Menu>
        <PageBody>
          <Switch>
            <Route exact path="/">
              <HomeScreen />
            </Route>

            <PrivateRoute path="/orders">
              <div>Tela de Pedidos</div>
            </PrivateRoute>

            <PrivateRoute path="/profile">
              <div>Tela de Perfil</div>
            </PrivateRoute>

            <Route path="/tela2/:nome">
              <Tela2Screen />
            </Route>
          </Switch>
        </PageBody>
        <Cart />
      </Container>
    </BrowserRouter>
  );
};
```

AppStyled.js

```js
import styled from "styled-components";

export const CartArea = styled.div`
  background-color: #136713;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
  position: fixed;
  bottom: 0;
  right: 30px;
`;

export const CartHeader = styled.div`
  width: 290px;
  height: 50px;
  display: flex;
  align-items: center;
  cursor: pointer;
`;

export const CartIcon = styled.img`
  width: 23px;
  height: auto;
  margin-left: 10px;
  margin-right: 10px;
`;

export const CartBody = styled.div``;
```
