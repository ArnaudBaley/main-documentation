---
title: "Git"
date: 2021-05-18T15:55:39+02:00
draft: false
---

### Git Submodules (nested repositories)

Test :
```shell
git submodule status
```

Add submodule `.gitmodules`: 
```
[submodule "themes/hugo-theme-learn"] 
  path = themes/hugo-theme-learn 
  url = git://github.com/matcornic/hugo-theme-learn
```