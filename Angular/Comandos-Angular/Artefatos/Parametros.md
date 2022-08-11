## Como usar os parametros

Suponha que seja necessário criar um novo componente para seu projeto e você não deseja que seja criado um diretório ou arquivos de teste para ele. Para tal, você deve usar o comando abaixo:

```js
ng generate component Favorito --flat --spec false
```

Com esse componente criado, suponha que agora você precisa de um serviço para se comunicar com uma API externa para obter dados. Entretanto, você não quer arquivos de testes, mas gostaria que esse serviço fosse criado dentro de um diretório próprio. Para fazer isso, utilize o comando abaixo:


```js
ng generate service API --spec false --flat false
```

