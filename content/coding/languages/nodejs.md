---
title: "NodeJs"
date: 2021-05-18T15:55:39+02:00
draft: false
---

**Transform callback TO Promise -> util.promisify**

```javaScript
const util = require('util');

.....

const promisified = util.promisify(envoyerMailTemplateDynamique);
await promisified(codeMarqueBlanche, extraParams, to, template);
```