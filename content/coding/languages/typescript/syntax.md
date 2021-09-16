---
title: "Syntax"
date: 2021-05-18T15:55:39+02:00
draft: false
weight: 1
---

**void** = function don't return value.  
**any** = function return something (not recommended).

**optional parameter** = ?
```ts
function objectParam(num: number, b?: string): boolean {
    return num % 2 === 0
}
```

**dual parameter + cast**
```ts
function dualParam(num: number | string): boolean {
    if (typeof num !== 'number') {
        num = parseInt(num, 10);
    }
    return <number>num % 2 === 0
}
```

**Enum**
```ts
enum UserResponse {
  No = 0,
  Yes = 1,
}
 
function respond(recipient: string, message: UserResponse): void {
  // ...
}
 
respond("Princess Caroline", UserResponse.Yes);
```