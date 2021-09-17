---
title: "Tests"
date: 2021-05-18T15:55:39+02:00
draft: false
---

### BDD - Behavior Driven Development

[SOURCE](https://en.wikipedia.org/wiki/Behavior-driven_development)

-**Collaborate** with business to assess the need  
-**specify behavior** in terms of user stories :
```
**As a** store owner,
    **I want** to add items back to inventory when they are returned or exchanged,
        **so that** I can track inventory.

**Scenario 1**: Items returned for refund should be added to inventory.
    **Given** that a customer previously bought a black sweater from me
    **and** I have three black sweaters in inventory,
    **when** they return the black sweater for a refund,
    **then** I should have four black sweaters in inventory.

**Scenario 2**: Exchanged items should be returned to inventory.
    **Given** that a customer previously bought a blue garment from me
    **and** I have two blue garments in inventory
    **and** three black garments in inventory,
    **when** they exchange the blue garment for a black garment,
    **then** I should have three blue garments in inventory
    **and** two black garments in inventory.
```


### TDD - Test Driven Development

Sources :
* [Apprendre le TDD - blog.ippon.fr](https://blog.ippon.fr/2020/02/12/apprendre-le-tdd/)

-Improve code quality, velocity

-3 phases : RED -> GREEN -> Refactor - >  .....  
-short cycle (minutes)

#### RED

-Think about business need.  
-Write test.  
-Test must not passed.  

#### RED

-Write most direct code to pass the test.

#### Refactor

-Improve code.