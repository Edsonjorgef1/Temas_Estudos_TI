Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Exibindo lista e scroll

App.js

```js
import React from "react";
import styled from "styled-components/native";
import lista from "./src/lista";

const Page = styled.SafeAreaView`
  flex: 1;
`;
const Scroll = styled.ScrollView`
  width: 300px;
  max-height: 300px;
  background-color: #ff0000;
  /* flex: 1; */
`;
const Item = styled.View`
  padding: 10px;
`;
const ItemText = styled.Text`
  font-size: 15px;
`;

function App() {
  return (
    <Page>
      <Scroll>
        {lista.map((item, index) => {
          return (
            <Item key={index}>
              <ItemText>{item.task}</ItemText>
            </Item>
          );
        })}
      </Scroll>
    </Page>
  );
}

export default App;
```

src/lista.js

```js
export default [
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
  { task: "Fazer XYZ", done: false },
  { task: "Fazer ABC", done: true },
  { task: "Fazer YUI", done: false },
];
```
