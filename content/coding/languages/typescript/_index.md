---
title: "TypeScript"
date: 2021-05-18T15:55:39+02:00
draft: false
---

#### Intro :

-Created by Microsoft  
-Code will be transpiled in JavaScript  
-Strongly typed


#### Doc :

- [Official doc](https://www.typescriptlang.org/)

#### Tuto :

- [Tuto vidéo Typescript - Grafikart](https://grafikart.fr/tutoriels/typescript-781)

#### Setup :

```shell
npm install -g typescript
```

**Check version**
```shell
tsc -v
```

#### Transpile :

**ES3 (by default)

```shell
tsc filename.ts
```

**ES5 
```shell
tsc filename.ts --target es5
```

#### Hot reload :

```shell
tsc -w --pretty filename.ts --target es5
```

#### Configuration file : 

Create `tsconfig.json` at project's root.

```json
{
    "compilerOptions": {
        "target": "ES5",
        "pretty": true,
        "outDir": "./build"
    },
    "files": [
        "demo.ts",
        "class.ts"
    ],
    "exclude": ["node_modules"]
}
```

Launch transpiler : 
```shell
tsc -w
```