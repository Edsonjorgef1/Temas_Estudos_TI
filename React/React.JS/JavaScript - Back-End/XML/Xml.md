Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```
## Xml

//npm install --save react-xml-viewer

```js
import React, { Component } from "react";
import XMLViewer from "react-xml-viewer";

const xml = "<hello>World</hello>"; // Xml = <hello>World</hello>
const customTheme = {
  attributeKeyColor: "#FF0000",
  attributeValueColor: "#000FF",
};

export default class App extends Component {
  render() {
    return (
      <div>
        <XMLViewer xml={xml} theme={customTheme} />
      </div>
    );
  }
}
```
