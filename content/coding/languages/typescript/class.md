---
title: "Class"
date: 2021-05-18T15:55:39+02:00
draft: false
weight: 2
---

### Prerequirement

-Activate transpilation in ES5

### General

Scope : 
- public
- private
- protected

- static

#### Basic class

```ts
class Demo {

    private _element

    constructor () {
        
    }

    // Getter & setter
    set element (value: string) {
        this._element = value
    }

    get element (): string {
        return this._element
    }

}

let d = new Demo()

// Getters & setters are automatically called
d.element = 'Salut'
console.log(d.element);
```

#### Heritage

```ts
class Animal {
  move() {
    console.log("Moving along!");
  }
}
 
class Dog extends Animal {
  woof(times: number) {
    for (let i = 0; i < times; i++) {
      console.log("woof!");
    }
  }
}
 
const d = new Dog();
// Base class method
d.move();
// Derived class method
d.woof(3);
```

#### Interface

**Interface for param :**
```ts
interface LabeledValue {
  label: string;
}
 
function printLabel(labeledObj: LabeledValue) {
  console.log(labeledObj.label);
}
 
let myObj = { size: 10, label: "Size 10 Object" };
printLabel(myObj);
```

**Interface for class :**
```ts
interface ClockInterface {
    currentTime: Date;
    setTime(d: Date): void;
  }
   
  class Clock implements ClockInterface {
    currentTime: Date = new Date();
    setTime(d: Date) {
      this.currentTime = d;
    }
    constructor(h: number, m: number) {}
  }
```