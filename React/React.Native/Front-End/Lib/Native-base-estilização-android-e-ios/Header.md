Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Native Base, Header

```js
import React from "react";
import {
  Container,
  Header,
  Left,
  Body,
  Right,
  Title,
  Subtitle,
} from "native-base";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
`;

function App() {
  return (
    <Container>
      <Header>
        <Left />
        <Body>
          <Title>Title</Title>
          <Subtitle>Subtitle</Subtitle>
        </Body>
        <Right />
      </Header>
    </Container>
  );
}

export default App;
```
