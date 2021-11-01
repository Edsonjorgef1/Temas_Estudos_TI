## Pesquisar, um titulo, com um link de uma URL

link para visualizar este projetinho

```js
https://pesquise-filter.netlify.app/
```

```js
import React, { useState } from "react";

const Search = (props) => {
  return (
    <div>
      <label htmlFor="search">
        <strong>Pesquise uma empresa de Elétrica:</strong>
      </label>{" "}
      <input id="search" type="text" onChange={props.onSearch} />
    </div>
  );
};

const List = ({ list }) =>
  list.map((item) => (
    <div key={item.objectID}>
      <span>
        <a href={item.url}>{item.title}</a>
      </span>
      <span>{item.author}</span>
      <span>{item.num_comments}</span>
      <span>{item.points}</span>
    </div>
  ));

export default function App() {
  const [searchTerm, setSearchTerm] = useState("");
  const stories = [
    {
      title: "Dimensão",
      objectID: 1,
      url: "https://dimensaoeletricistas.com.br/?gclid=CjwKCAjwoP6LBhBlEiwAvCcthC7vBqGDC7ScW6Lpf5wnNrJUFDae1ZPvdNol7fOVK33Sx4bmetsJ5hoCPr0QAvD_BwE",
    },
    {
      title: "Cardoso",
      objectID: 2,
      url: "https://www.cardosoengenharia.com.br/",
    },
    {
      title: "Abine",
      objectID: 3,
      url: "http://www.abinee.org.br/",
    },
  ];

  const handleSearch = (event) => {
    setSearchTerm(event.target.value);
  };

  const searchStories = stories.filter((story) => {
    return story.title.includes(searchTerm);
  });

  return (
    <div>
      <h1>Pesquise uma empresa!</h1>
      <Search onSearch={handleSearch} />
      <hr />
      <List list={searchStories} />
    </div>
  );
}
```

## Buscando um item, dentro de uma matriz Json

```js
//Importando o react
import React from "react";

const products = [
  {
    PartNumber: "ALM-GN001",
    ProductName: "GNSS Filter-LNA Front-End Module",
    productline: "GPS/GNSS Wireless Amplifiers",
    AV_47_Frequency_GHz: "1.575",
    AV_47_NF: "",
  },
  {
    PartNumber: "ALM-GP001",
    ProductName: "GPS Filter-LNA-Filter Front-End Module",
    productline: "GPS/GNSS Wireless Amplifiers",
    AV_47_Frequency_GHz: "1.565 - 1.606",
    AV_47_NF: "",
  },
  {
    PartNumber: "ALM-GA001",
    ProductName:
      "High-Gain, Low-Current LNA with Variable Current and Shutdown Function",
    productline: "GPS/GNSS Wireless Amplifiers",
    AV_47_Frequency_GHz: "1.606",
    AV_47_NF: "0.97",
  },
  {
    PartNumber: "ALM-GN002",
    ProductName:
      "GNSS LNA-Filter Front-End Module with Optional Differential Outputs",
    productline: "GPS/GNSS Wireless Amplifiers",
    AV_47_Frequency_GHz: "1.565",
    AV_47_NF: "0.97",
  },
];

const result = products.map((product) => product.PartNumber);

console.log(result);

const App = () => {
  return <div>{result}</div>;
};

export default App;
```

## Filtrando, valores pequenos

Os exemplos a seguir usam filter() para criar um array filtrado em que
todos os elementos com valores menores que 10 são removidos.

```js
//Importando o react
import React from "react";

function isBigEnough(value) {
  return value >= 10;
}
var filtered = [12, 5, 8, 130, 44].filter(isBigEnough);
// filtered is [12, 130, 44]

const App = () => {
  return <div>{filtered}</div>;
};

export default App;
```
