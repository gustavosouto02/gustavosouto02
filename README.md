### Olá! Eu sou o Gustavo Souto 👋

#### Sobre mim:
Dev em formação, Cursando Ciências da Computação atualmente no 3° Semestre, na Universidade Católica de Brasília

#### Tecnologias que eu uso:
<div style="display: inline-block"><br/>
<img align="center" alt= html5 src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" />
<img align="center" alt= css src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" />
<img align="center" alt= c/c+ src="https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white" />
<img align="center" alt= python src="https://img.shields.io/badge/Python-14354C?style=for-the-badge&logo=python&logoColor=white" />
<img align="center" alt= javascript src="https://img.shields.io/badge/Javascript-14354C?style=for-the-badge&logo=javascript&logoColor=white" />


</div>
name: Generate Datas

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"
  workflow_dispatch:

jobs:
  build:
    name: Jobs to update datas
    runs-on: ubuntu-latest
    steps:
      # Snake Animation
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: rafaballerini
          svg_out_path: dist/github-contribution-grid-snake.svg

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
