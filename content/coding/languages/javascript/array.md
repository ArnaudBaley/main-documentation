---
title: "Array"
date: 2021-05-18T15:55:39+02:00
draft: false
---

#### **Extract part** of an array or a string  (new array) -> **slice()**
```js
const array = 'hello world';
const result = array.slice(0,5);
console.log(result); // hello
```

#### **Remove part** of an array (replace array) -> **splice()**
```js
const array = ['h','e','l','l','o'];
const result = array.splice(0, 3);
console.log(result); // hel
```

#### **Split** string by **separator** -> **split()**
```js
const string = 'hello,world';
const result = string.split(",");
console.log(result); // ["hello", "world"]
```