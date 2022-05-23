Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Native Spiner

```js
import React from "react";
import { Container, Header, Content, Spinner } from "native-base";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
`;

function App() {
  return (
    <Container>
      <Header />
      <Content>
        <Spinner color="red" />
        <Spinner color="green" />
        <Spinner color="blue" />
      </Content>
    </Container>
  );
}

export default App;
```
