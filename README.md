<h2 align="left">Hi 👋! My name is Bilal El_qaqei and I'm an Embedded software engineer.</h2>

###

<img align="right" height="150" src="https://scontent.faly2-1.fna.fbcdn.net/v/t39.30808-6/321100615_734900751330502_7804165094549757365_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=5f2048&_nc_ohc=2Q0dksbStPcAX9pc6Qx&_nc_ht=scontent.faly2-1.fna&oh=00_AfCp8j7FhktOG-YDbh1EWByCkdDTcmCeDiMDgjHDMDduGw&oe=653C617B"  />

###

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" height="30" alt="python logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" height="30" alt="c logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg" height="30" alt="cplusplus logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/matlab/matlab-original.svg" height="30" alt="matlab logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/visualstudio/visualstudio-plain.svg" height="30" alt="visualstudio logo"  />
</div>

###

<div align="left">
  <a href="https://www.instagram.com/bilal_k3ka3y/?hl=ur" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Instagram&logo=instagram&label=&color=E4405F&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="instagram logo"  />
  </a>
  <a href="https://mail.google.com/mail/u/0/?hl=ar#inbox" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Gmail&logo=gmail&label=&color=D14836&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="gmail logo"  />
  </a>
  <a href="https://www.linkedin.com/in/bilal-mohamed-el-qeqei-9681a3211/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="linkedin logo"  />
  </a>
  <a href="https://www.facebook.com/profile.php?id=100011705387780" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Facebook&logo=facebook&label=&color=1877F2&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="facebook logo"  />
  </a>
</div>

###

<br clear="both">

<img src="https://raw.githubusercontent.com/Bilalmhmd/Bilalmhmd/output/snake.svg" alt="Snake animation" />

###

name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - master

jobs:
  generate:
    runs-on: ubuntu-latest

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v2
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v2.6.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
