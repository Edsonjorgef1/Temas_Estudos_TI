Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

assets/bg.png Dentro da pasta assets, vai conter uma imagem bg.png

App.js

```js
import React from "react";

import { PageBody } from "./AppStyled";

export default () => {
  return <PageBody></PageBody>;
};
```

AppStyled.js

```js
export const PageBody = styled.div`
  display: flex;
  background-color: #00980d;
  background-image: url("/assets/bg.png");
  flex: 1;
`;
```
