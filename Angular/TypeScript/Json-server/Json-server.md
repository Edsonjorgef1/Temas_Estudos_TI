Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Consumindo Api arquivo Json

Para instalar localmente o json server

```js
npm install -g json-server
```

Para rodar

```js
json-server --watch db.json
```

FakeApi/db.json

```js
{
  "carros": [
    {
      "id": 3,
      "marca": "Fiat",
      "nome": "Uno"
    },
    {
      "marca": "Audi",
      "nome": "rx7",
      "id": 4
    },
    {
      "nome": "Aventador",
      "marca": "Lambo",
      "id": 5
    },
    {
      "nome": "Urus",
      "marca": "Lambo",
      "id": 6
    }
  ]
}
```
