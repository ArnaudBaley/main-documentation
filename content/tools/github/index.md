---
title: "GitHub"
date: 2021-05-18T15:55:39+02:00
draft: false
---

### Activate pages

-Repository -> Settings -> Options -> GitHub Pages

### Actions (workflow)

Create file : `.github/workflows/workflow.yml`

Example (auto build hugo static site generator on push) : 
```yml
name: CI
on: push
jobs:
  deploy:
    runs-on: ubuntu-18.04
    steps:
      - name: Git checkout
        uses: actions/checkout@v2

      - name: Update theme    
        run: git submodule update --init --recursive

      - name: Setup hugo
        uses: peaceiris/actions-hugo@v2

      - name: Build
        run: hugo

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          personal_token: ${{ secrets.TOKEN }}        
          publish_dir: ./public
          keep_files: true
          publish_branch: docs
```