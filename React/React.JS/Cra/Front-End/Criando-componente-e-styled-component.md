Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

src/Header/index.js

```js
import React from "react";
import { Container } from "./styled";

export default () => {
  return <Container></Container>;
};
```

src/Header/styled.js

```js
import styled from "styled-components";

export const Container = styled.di``;
```

src/App.js

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
