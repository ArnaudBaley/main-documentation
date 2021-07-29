---
title: "Jest"
date: 2021-05-18T15:55:39+02:00
draft: false
---

#### Boilerplate : 

```Javascript
import errorUtil from '../../../src/public/utils/errorUtil';

describe('detectNetworkError', () => {
    test('detectNetworkError : wrong parameters', () => {
        expect(errorUtil.detectNetworkError()).toBe(null);
    });
});
```