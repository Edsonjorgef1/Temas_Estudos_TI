Inscrevam-se: Canal, Engenheiro Youtuber

https://www.youtube.com/engenheiroyoutuber

## Criando meu repositório no Github e enviando minhas alterações feitas no VsCode

## GitHub

Logar com sua conta no GitHub.

```js
https://github.com/
```

Depois va até a opção Repositório no GitHub e clicar e new.
Coloque o nome do seu repositório
Descrição
Publico ou Privado
Depois clique em Create Repository

```js
https://github.com/new

```

Depois de criado um repositório, no GitHub, vai aparecer, assim:

```js
echo "# Nome_Do_Seu_Projeto" >> README.md // Linha 1
git init // Linha 2
git add README.md // Linha 3
git commit -m "first commit" // Linha 4
git branch -M main // Linha 5
git remote add origin https://github.com/seu_loguin/nome_do_seu_projeto.git // Linha 6
git push -u origin main // Linha 7
```

## VsCode, vamos agora, enviar seu projeto do VsCode para o GitHub.

A forma que o seu projeto foi desenvolvido, fica a seu critério, este modelo é padrão, independente do jeito que você fez o seu projeto.
Lembrando, que você pode usar o terminal, que você desejar, Git Bash o terminal do vscode e outros.
Lembrando, você deve estar dentro da pasta de seu projeto, que você criou.
Windos, comandos para acessar a pasta caso desejar ir pelo terminal até seu projeto.

Para criar uma pasta pelo terminal.

```js
mkdir (Nome do seu projeto)
mkdir App1
```

Entrando dentro, da sua pasta criada

```js
cd (Nome da sua pasta criada)
cd App1
```

Depois que você tiver dentro da sua pasta criada, você deve criar seu projeto.
Escolha uma opção, qual o projeto que você vai fazer.
Para abrir seu projeto, depois que estiver dentro da pasta
Quando você der o comando code ., vai abrir seu projeto, no vscode.

```js
code .
```

## Criando o projeto em React.Js (Web)

Lembre-se de instalar, o node para rodar este projeto
Se quiser pode instalar o yarn, o yarn é um pouco mais rápido do que o npm,
npm já vem instalado quando você cria o projeto.

Criando um novo projeto em react.js

```js
npx create-react-app (Nome do projeto)
```

ou

React.js (Typescript)

```js
npx create-react-app (Nome do Projeto) --template typescript
```

Pode rodar o projeto, já criado com o comando abaixo

```js
npm start
ou
yarn start
```

## Criando um projeto em React.Native (Aplicativo)

Para rodar o projeto, você pode utilizar o android studio ou o mais indicado o expo, pois pode espelhar no seu celular o projeto, assim ficando mais leve, pois os emuladores hoje, são um pouco pesado e nem todos tem um computador bom para rodar estes emuladores principalmente que está aprendendo

```js
npx create-react-native-app (Nome do projeto)
```

ou

Typescript

```js
npx react-native init (Nome do projeto) --template react-native-template-typescript
```

## Projeto do zero em html5

Para rodar o projeto, deste jeito, você pode instalar a extensão abaixo

```js
live server
```

Você deve criar, a estrutura do html e organizar seu CSS e JavaScript, da forma que você achar melhor.

Aqui está um exemplo, criar a estrutura de um projeto do zero, padrão:

Arquivo, criado, index.html

```js
<!DOCTYPE html>
<html lang="en">  {/* en, significa em português*/}
<head> {/* Head, é a cabeça do Html*/}

  {/* Conectando o arquivo criado em CSS, para ficar mais organizado*/}
  <link rel="stylesheet" href="style.css" />

  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>Document</title>

</head>

<body>  {/* Body, é o corpo do Html*/}
<p class = "engenheiroyoutuber">Parágrafo com class</p>
<p id = "engenheiroyoutuber">Parágrafo com id</p>

{/* Conectando o arquivo criado em javascript, para ficar mais organizado*/}
<script src="nomedoarquivojavascript.js"></script>

</body >
</html>
```

Arquivo, criado, nomedoarquivojavascript.js
Lembrando, que este arquivo está conectado, porque adicionamos ele no corpo do html do body, igual está acima, o nome tem que ser igual, foi colocado no copor do html dentro de script, acima, <script src="nomedoarquivojavascript.js"></script>

```js
Aqui dentro, agora você pode programar em JavaScript
```

Arquivo, criado, style.css
Lembrando, que este arquivo está conectado, porque adicionamos ele no corpo do html do head, igual está acima, o nome tem que ser igual, foi colocado na cabeça do html, dentro de link, acima, <link rel="stylesheet" href="style.css" />

```js
// Aqui dentro, vai ser estilizado o se projeto em CSS

//Chamando com Class
.engenheiroyoutuber {
color: BLue;
}
//Chamando com Id
#engenheiroyoutuber {
color: BLue;
}
```

## Enviando seu projeto para o GitHub

Agora que você escolheu um metodo acima, vamos enviar seu projeto

Lembra quando criamos um repositório e apareceu assim.

Depois de criado um repositório, no GitHub, vai aparecer, assim:

```js
echo "# Nome_Do_Seu_Projeto" >> README.md // Linha 1
git init // Linha 2
git add README.md // Linha 3
git commit -m "first commit" // Linha 4
git branch -M main // Linha 5
git remote add origin https://github.com/seu_loguin/nome_do_seu_projeto.git // Linha 6
git push -u origin main // Linha 7
```

## Linha 1

Digite no terminal (Tem aque estar na opção master)

```js
echo "# minhas_series_react_js" >> README.md // Linha 1
```

## Linha 2

Digite no terminal

```js
git init // Linha 2
```

obs: caso aparecer um erro, dizendo,

```js
Reinitialized existing Git repository in C:/Projetos/nomedoprojeto/.git/
```

Este comando vai resolver seu problema, para adicionar uma nova url.

Verificando qual URL do repositório está.

```js
git remote -v
```

Removendo URL do repositorio que estava

```js
git remote remove origin
```

## Linha 3

Git add, Digite no terminal, (Quando faz (git add .) todos os arquivos são enviados) (Para adicionar somente um arquivo, exemplo: git add README.md)

```js
 git add .
 ou
 git add READMe.md
```

## linha 4

git commit -m "Nome do commit"

Digite no terminal (Agora você deu o nome do seu commit, o nome da versão que você editou)

```js
git commit -m "Primeiro Commit"
```

## Linha 5

Para criar uma branch, caso queira.
Está opção serve se você estiver trabalhando remotamente com mais de uma pessoa, assim você pode fazer alteração na sua branch no seu nome, para não interferir no projeto principal, ai a pessoa responsavel pelo projeto, vai subir para o projeto pricipal a Master só aquilo que for correto para o projeto, para todos visualizar como está o projeto atual, apenas com os commit corretos.

```js
git checkout -b (Nome da Branch)
```

Para voltar para a Master no Github

```js
git checkout master
```

## Linha 6

Adicionando uma nova URL

```js
git remote add origin https://github.com/seu_loguin/nome_do_seu_projeto.git // Linha 6
```

## Linha 7

git push -u origin master

Digite no terminal (Enviando para o github)

```js
 git push -u origin master
```

### Outros comandos, não é necessario fazer, caso não precise

1-Digite no terminal (Agora vai aparecer na cor verde, todos os arquivos adicionados, para ser comitado, depois de ter feito o git add)
2-Depois de ter dado o git commit, se fazer o git status não vai aparecer mais nada
3- Digite no terminal (Verificando arquivos que você pode adicionar, vai estar na cor vermelha)

```js
git status -u
```

### Configurando e-mail e nome, se for seu primeiro repositório

OBS: Se for sua primeira vez, vai aparecer uma observação para você configurar seu e-mail e seu nome assim:

Configuração global para todos os projetos

E-mail

```js
git config --global user.email "e-mail do seu github"
```

Nome

```js
git config --global user.name "Seu nome"
```

Para configurar somente um projeto
E-mail

```js
git config user.email "E-mail github"
```

Nome

```js
git config user.name "Seu Nome"
```

### Caso pedir username

Digite no terminal (Se no terminal, pedir o username, você coloca o usuario do github)

Exemplo:
Usuário

```js
Username for 'https://github.com': (Usuario github)
```

Password

```js
Password for 'https://seu e-mail': (Digite sua senha do github)
```

## Vamos agora, alterar o projeto depois de configurado a primeira vez

Agora você deve está, perguntando já fiz tudo mais agora quero fazer uma alteração no meu projeto o que eu faço, ja fiz todos os passos, tenho que fazer tudo outra vez!

(Subir todos os aquivos)

```js
git add.
```

Ou você pode escolher o nome do arquivo, expecifico exemplo: index.html

```js
git add. Index.html
```

Comitando, dando o nome da alteração do seu projeto

```js
git commit -m "Nome da alteração do seu projeto"
```

Enviando as alterações do seu projeto

```js
git push origin (nome da branch)
```

## Para clonar um projeto do GitHub

Basta você copiar a URL, do projeto que deseja,
você vai achar na opção <code>, depois clique em Code, opção HTTPS, ai você
copia a URL, e faz o comando abaixo.

```js
git clone (URL do projeto que deseja clonar)
```

Lembre-se que, se o projeto for em React, depois de clonar o projeto você deve
fazer.

```js
yarn
ou
npm install
```

Para que fazer, yarn start ou npm start, para você instalar as dependencias do
projeto padrão do react, que é a pasta node_modules, ai depois de fazer isso você deverá, verificar no arquivo package.json, se contém alguma dependencia instalada, exemplo: bootstrap, ai você deverá instalar todas as dependencias do projeto que você copiou para ele funcionar.
