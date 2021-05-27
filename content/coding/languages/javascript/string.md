---
title: "String"
date: 2021-05-18T15:55:39+02:00
draft: false
---

#### **Extract part** of an array or a string  (new array) -> **slice()**
```js
const array = 'hello world';
const result = array.slice(0,5);
console.log(result); // hello
```

#### **Split** string by **separator** -> **split()**
```js
const string = 'hello,world';
const result = string.split(",");
console.log(result); // ["hello", "world"]
```