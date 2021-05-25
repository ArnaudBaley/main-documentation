---
title: "Design Patterns"
date: 2021-05-18T15:55:39+02:00
draft: false
---

Sources : 
- [JavaScript Design Patterns (BetterProgramming)](https://betterprogramming.pub/javascript-design-patterns-25f0faaaa15)

## List

|  |  |  | |
| ----------- |----------- | ----------- | ----------- |
| **Module** | Organize code, encapsulation. |  | 
| **Observer** | Update an object when an another object changes (see : $emit et $broadcast in JS frameworks).|  | 
| **Prototype** | “skeleton” of an existing object to create or instantiate new objects. |  | 
| **Singleton** | Only one instance of a singleton class can exist |  | 
| **Constructor** |  Based on class. Execute code at class instantiation.  |  | 
| **Factoy** | Class with generic interface that delegates the responsibility of object instantiation to its subclasses. | Need to manage or manipulate collections of objects that are different yet have many similar characteristics. |
| **Strategy** | | |
| **Adapter** | | | 
| **Composite** | | |
| **Decorator** | | |
| **Façade** | | |
| **Flyweight** | | |
| **Proxy** | | |
| **Chain of Responsibility** | | |
| **Command** | | |
| **Iterator** | | |
| **Mediator** | | |
| **State** | | |
| **Template** | | |


### Singleton

```JavaScript

class Database {
  constructor(data) {
    if (Database.exists) {
      return Database.instance;
    }
    this._data = data;
    Database.instance = this;
    Database.exists = true;
    return this;
  }

  getData() {
    return this._data;
  }

  setData(data) {
    this._data = data;
  }
}

// usage
const mongo = new Database('mongo');
console.log(mongo.getData()); // mongo

const mysql = new Database('mysql');
console.log(mysql.getData()); // mongo
```

### Factory

```JavaScript
class BallFactory {
  constructor() {
    this.createBall = function(type) {
      let ball;
      if (type === 'football' || type === 'soccer') ball = new Football();
      else if (type === 'basketball') ball = new Basketball();
      ball.roll = function() {
        return `The ${this._type} is rolling.`;
      };

      return ball;
    };
  }
}

class Football {
  constructor() {
    this._type = 'football';
    this.kick = function() {
      return 'You kicked the football.';
    };
  }
}

class Basketball {
  constructor() {
    this._type = 'basketball';
    this.bounce = function() {
      return 'You bounced the basketball.';
    };
  }
}

// creating objects
const factory = new BallFactory();

const myFootball = factory.createBall('football');
const myBasketball = factory.createBall('basketball');

console.log(myFootball.roll()); // The football is rolling.
console.log(myBasketball.roll()); // The basketball is rolling.
console.log(myFootball.kick()); // You kicked the football.
console.log(myBasketball.bounce()); // You bounced the basketball.
```