Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Native Base, Button

```js
import React from "react";
import { Button, Text } from "native-base";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
`;

function App() {
  return (
    <NativeBaseProvider>
      <Page>
        <Button rounded danger>
          {" "}
          {/*rounded = É igual o border radius*/}
          <Text>Botão de teste</Text>
        </Button>
      </Page>
    </NativeBaseProvider>
  );
}

export default App;
/*
rounded = Arredondar os cantos
small = ficar menor
large = ficar maior
/*ler a
documentação do native base*/
```
