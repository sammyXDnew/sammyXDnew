<h1 align="center">Hi there! I'm Samuel Santoso 👋</h1>
<h3 align="center">Informatics Engineering Student | Web Developer | AI & Computer Vision Enthusiast</h3>

<br/>

- 🔭 Saat ini sedang mengembangkan arsitektur **GEED Clip** (SaaS kliping video otomatis) dan proyek segmentasi citra Aksara Jawa.
- 🌱 Fokus mendalami **Machine Learning** (TensorFlow, scikit-learn) dan ekosistem **Next.js** / **Tailwind CSS**.
- 📹 Di luar coding, saya mengelola channel YouTube **sammyXD** dan meracik konten digital.
- ⚡ **Fun fact:** Saya menggunakan *script* Python untuk mengotomatisasi pembuatan e-book resep masakan internasional!

---

### 🛠️ Tech Stack & Tools

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Next-black?style=for-the-badge&logo=next.js&logoColor=white" />
  <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" />
  <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" />
  <img src="https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=Power%20BI&logoColor=white" />
</p>

---

### 📊 GitHub Stats

<p align="left">
  <img src="https://github-readme-stats.vercel.app/api?username=SamuelSantoso-code&show_icons=true&theme=radium" alt="Samuel's GitHub Stats" />
</p>

---

### 🐍 GitHub Snake Game (Contribution Graph)

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/SamuelSantoso-code/SamuelSantoso-code/output/github-contribution-grid-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/SamuelSantoso-code/SamuelSantoso-code/output/github-contribution-grid-snake.svg">
  <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/SamuelSantoso-code/SamuelSantoso-code/output/github-contribution-grid-snake.svg">
</picture>

name: Generate Snake Animation

on:
  schedule:
    - cron: "0 */24 * * *" 
  workflow_dispatch:
  push:
    branches:
    - main

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    steps:
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}