---
title: "Hugo"
date: 2021-05-18T15:55:39+02:00
draft: false
---

## Sources

**Official guide** : [getting started](https://gohugo.io/categories/getting-started)

**Tutorials** :

- [Comment créer un site avec Hugo partie 1 : intro et configurations](https://bout2code.fr/tutos/creer-un-site-avec-hugo/comment-creer-un-site-avec-hugo-partie-1-la-configuration-initiale/)

* * *

## Tricks

#### Activate full search (not only menu items)

`config.toml` :
```toml
[outputs]
home = [ "HTML", "RSS", "JSON"]
```

#### Change order in menu

-keyword **weight** :
```
---
title: "Commands"
date: 2021-05-18T15:55:39+02:00
draft: false
weight: 1
---
```