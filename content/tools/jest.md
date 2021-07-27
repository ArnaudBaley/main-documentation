---
title: "Jest (Unit test)"
date: 2021-05-18T15:55:39+02:00
draft: false
---

#### Jest - Expect to throw error : 

**synchronous :**

```
expect(() => list.clickButton()).toThrow('incorrect param "action"');
```

**asynchronous :**
```
expect(list.clickButton()).rejects.toEqual(new Error('incorrect param "action"'));
```