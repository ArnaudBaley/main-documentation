---
title: "MongoDB"
date: 2021-05-18T15:55:39+02:00
draft: false
---

**Projection**

```
db.getCollection('myCollection').find({
    id: ObjectId("60c75a631e130a5b9dfc00a0")
    },{ 'myNode.field': 1 })
```

**Sort by date**

```
db.getCollection('mycollection').find().sort({$natural:-1});
```

**Execute script file in mongo shell**

```
mongo localhost:27017/mydatabase parametrage.js
```


**Array not empty :**
```
db.getCollection('mycollection').find({
    'associations.contrats': { $exists: true, $not: {$size: 0} }
})
```

**Date > :**
```
'historiqueDocument.creation.date': {"$gte":new Date("2020-01-01")}
```