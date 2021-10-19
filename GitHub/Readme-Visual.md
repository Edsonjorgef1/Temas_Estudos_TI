Inscrevam-se: Canal, Engenheiro Youtuber

https://www.youtube.com/engenheiroyoutuber

## Criando repósitorio
Quando for criar o seu repositório, você terá que fazer um repositório com o nome do seu usuário para que você possa fazer a apresentação do seu github.

## Como deixar o visual mais bunito do readme do seu github

Quando você clicar no seu perfil, na opção Overview, abaixo vai conter alguns repositorios seus popular, a mais abaixo, vai conter um lugar escrito "contributions", neste lugar aonde está a quantidade e os dias que você está fazendo os commit, do lado direito escrito "contribution settings", clique na opção "Private contributions", ira começar a somar a quantidade de commit's que você faz no privado assim somando mais comit's.

## Guia de markdown

```js
https://docs.pipz.com/central-de-ajuda/learning-center/guia-basico-de-markdown#open

```

## Repositório do Github Stats

```js
https://github.com/anuraghazra/github-readme-stats
```

## Site emojis

Podem ser utilizados dentro do arquivo readme.md

```js
https://emojipedia.org/search/?q=bag
```

## Site de Badges 1

```js
https://dev.to/envoy_/150-badges-for-github-pnk
```

## Fazedor de gifs

```js
https://picrew.me/image_maker/338224
```

## Passo a passo de como adicionar a cobrinha do commit

Este comando coloque no Readme.md

```js
![Snake animation](https://github.com/USERNAME/USERNAME/blob/output/github-contribution-grid-snake.svg)
```

Arquivo README.md

```js
<div align="center">
<h2> Seja, bem vindo!</h2>
</div>
</br>
<div align="center">

  <div align="center">
  <a href="https://github.com/gilbertoreact">
    <img height="180em" src="https://github-readme-stats.vercel.app/api?username=gilbertoreact&show_icons=true&theme=dark&include_all_commits=true&count_private=true"/>
    </div>
</br>
  <div align="center">
    <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=gilbertoreact&layout=compact&langs_count=7&theme=dark"/>
</div>
</div>
</br>
 <div align="center">
<div style="display: inline_block"><br>
  <img align="center" alt="Rafa-Js" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-plain.svg">
  <img align="center" alt="Rafa-React" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg">
  <img align="center" alt="Rafa-HTML" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original.svg">
  <img align="center" alt="Rafa-CSS" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original.svg">
  <img align="center" alt="Rafa-Python" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg">
</div>
 </div>
</br>

 <div align="center">
  <a href="https://www.youtube.com/c/EngenheiroYoutuber/playlists" target="_blank"><img src="https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white" target="_blank"></a>
  <a href="https://www.instagram.com/engenheiroyoutuber" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white" target="_blank"></a>
  <a href = "mailto:gilberto-goncalves@outlook.com.br"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
  <a href="https://www.linkedin.com/in/gilberto-gon%C3%A7alves-a9a700131/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>
</div>

![Snake animation](https://github.com/gilbertoreact/gilbertoreact/blob/output/github-contribution-grid-snake.svg)
```

Para gerar o arquivo workflows, clique na opção, Actions, clique "New workflow"
depois vai gerar.
vai criar uma pasta chamada .github / workflows / main.yml

Arquivo main.yml

```js
name: Generate Datas

on:
schedule: # execute every 12 hours - cron: "\* _/12 _ \* \*"
workflow_dispatch:

jobs:
build:
name: nomedoseugithub
runs-on: ubuntu-latest
steps: # Snake Animation - uses: Platane/snk@master
id: snake-gif
with:
github_user_name: nomedoseugithub
svg_out_path: dist/github-contribution-grid-snake.svg

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
