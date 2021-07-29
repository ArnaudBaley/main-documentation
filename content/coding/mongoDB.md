---
title: "MongoDB"
date: 2021-05-18T15:55:39+02:00
draft: false
---

**Execute script file in mongo shell**

```
mongo localhost:27017/acommeassure aca_parametrage.js
```


**Array not empty :**
```
db.getCollection('acaDocument').find({
    'associations.contrats': { $exists: true, $not: {$size: 0} }
})
```

**Date > :**
```
'historiqueDocument.creation.date': {"$gte":new Date("2020-01-01")}
```