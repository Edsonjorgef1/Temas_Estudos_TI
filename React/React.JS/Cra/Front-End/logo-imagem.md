Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

src/Header/index.js

```js
import React from "react";
import { Container, Logo } from "./styled";

export default () => {
  return (
    <Container>
      <Logo src="assets/logo.png" />
    </Container>
  );
};
```

src/Header/styled.js

```js
import styled from "styled-components";

export const Container = styled.div`
  background-color: #136713;
  border-radius: 10px;
  padding: 20px;
  display: flex;
`;

export const Logo = styled.img`
  width: auto;
  height: 70px;
`;
```

scr/App.js

```js
import React from "react";
import Header from "./Header";

export default () => {
  return (
    <Container>
      <Header />
    </Container>
  );
};
```
