---
title: "Commands"
date: 2021-05-18T15:55:39+02:00
draft: false
weight: 1
---


## Create site :

- Create **site** "documentation": 
    ```shell
    hugo new site documentation
    ```

- Launch **server** (with autoreload) :
    ```shell
    hugo server
    ```

 http://localhost:1313


## Install a theme :

- Install **theme** :
    ```shell
    cd /themes
    git clone https://github.com/matcornic/hugo-theme-learn.git
    ```

- Activate new theme in `config.toml` :
    ```toml
    theme = "hugo-theme-learn"
    ```

## Create first post :

- Create chapter **(contains post)** `static-website-generators`
    ```shell
    cd ..
    hugo new --kind chapter static-website-generators/_index.md
    ```

- Create post `hugo` in chapter `static-website-generators` :
    ```shell
    hugo new static-website-generators/hugo.md
    ```

## Deploy

- Build : 
    ```shell
    hugo
    ```
Build result in `/public`
