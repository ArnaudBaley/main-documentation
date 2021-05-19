---
title: "GitHub"
date: 2021-05-18T15:55:39+02:00
draft: false
---

### Activate pages

-Repository -> Settings -> Options -> GitHub Pages

### Actions (workflow)

Create file : `.github/workflows/workflow.yml`

Example (auto build hugo static site generator on master push) : 
```yml
name: Build Site

on:
  push:
    branches:
      - master

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repo
        uses: actions/checkout@master
        with:
          submodules: true
      - name: Build Site
        uses: chabad360/hugo-actions@master
```