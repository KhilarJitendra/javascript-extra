---

## (16) Class Inheritance in JavaScript

---

## What is Class Inheritance?

**Class inheritance** allows one class (child) to **extend** another class (parent).

* Child class reuses parent behavior
* New functionality can be added
* Existing functionality can be overridden

```txt
Child IS-A Parent
```

---

## The `extends` Keyword

```js
class Animal {
  constructor(name) {
    this.speed = 0;
    this.name = name;
  }

  run(speed) {
    this.speed = speed;
    console.log(`${this.name} runs with speed ${this.speed}.`);
  }

  stop() {
    this.speed = 0;
    console.log(`${this.name} stands still.`);
  }
}
```

### Creating a Child Class

```js
class Rabbit extends Animal {
  hide() {
    console.log(`${this.name} hides!`);
  }
}

const rabbit = new Rabbit("White Rabbit");

rabbit.run(5);   // inherited
rabbit.hide();   // own method
```

✅ Rabbit has access to **both** `Animal` and `Rabbit` methods.

---

## How `extends` Works Internally (Prototype Chain)

`extends` uses **prototypal inheritance**:

```txt
rabbit
 ↓
Rabbit.prototype
 ↓
Animal.prototype
 ↓
Object.prototype
```

```js
Rabbit.prototype.__proto__ === Animal.prototype; // true
```

If a method isn’t found in `Rabbit`, JS looks up the chain.

---

## `extends` Can Accept Any Expression

```js
function f(msg) {
  return class {
    sayHi() {
      console.log(msg);
    }
  };
}

class User extends f("Hello") {}

new User().sayHi(); // Hello
```

📌 Useful for **advanced patterns** and **class factories**.

---

## Method Overriding

Child classes can override parent methods.

```js
class Rabbit extends Animal {
  stop() {
    console.log("Rabbit stopped");
  }
}
```

The child version **replaces** the parent version.

---

## Using `super`

Instead of replacing logic completely, we usually **extend it**.

### Calling Parent Methods

```js
class Rabbit extends Animal {
  stop() {
    super.stop(); // parent method
    this.hide();
  }

  hide() {
    console.log(`${this.name} hides!`);
  }
}
```

### `super` Rules

* `super.method()` → calls parent method
* `super()` → calls parent constructor
* `super()` **must be called before using `this`**

---

## Arrow Functions and `super`

Arrow functions:

* Do NOT have their own `this`
* Do NOT have their own `super`
* Inherit both from surrounding context

```js
class Rabbit extends Animal {
  stop() {
    setTimeout(() => super.stop(), 1000); // ✅ works
  }
}
```

❌ Regular function would fail:

```js
setTimeout(function () {
  super.stop(); // ❌ Error
}, 1000);
```

---

## Constructor Overriding (Very Important)

### What JS Generates Automatically

If child has **no constructor**:

```js
class Rabbit extends Animal {
  constructor(...args) {
    super(...args);
  }
}
```

---

### ❌ Common Mistake

```js
class Rabbit extends Animal {
  constructor(name, earLength) {
    this.name = name; // ❌ Error
    this.earLength = earLength;
  }
}
```

### ✅ Correct Way

```js
class Rabbit extends Animal {
  constructor(name, earLength) {
    super(name); // must be first
    this.earLength = earLength;
  }
}
```

📌 **Derived constructors do NOT create `this`**
👉 Parent constructor (`super`) does.

---

## Overriding Class Fields (⚠️ Tricky Behavior)

### Unexpected Result

```js
class Animal {
  name = "animal";

  constructor() {
    console.log(this.name);
  }
}

class Rabbit extends Animal {
  name = "rabbit";
}

new Animal(); // animal
new Rabbit(); // animal ❗
```

### Why?

**Field initialization order:**

1. Parent fields
2. Parent constructor
3. Child fields (after `super()`)

So parent constructor **never sees overridden fields**.

---

## Methods vs Fields (Important Difference)

### Methods behave as expected

```js
class Animal {
  showName() {
    console.log("animal");
  }

  constructor() {
    this.showName();
  }
}

class Rabbit extends Animal {
  showName() {
    console.log("rabbit");
  }
}

new Rabbit(); // rabbit ✅
```

📌 **Use methods/getters instead of fields** if override matters.

---

## `super` Internals – `[[HomeObject]]` (Advanced)

* Methods remember **where they were defined**
* Stored in internal `[[HomeObject]]`
* Used by `super` to resolve parent methods

```js
super.method();
```

➡️ Uses `[[HomeObject]]`, **not `this`**, to find parent

---

## Why Copying Methods with `super` is Dangerous

```js
let rabbit = {
  __proto__: animal,
  sayHi() {
    super.sayHi();
  }
};

let tree = {
  __proto__: plant,
  sayHi: rabbit.sayHi
};

tree.sayHi(); // ❌ Wrong result
```

📌 `[[HomeObject]]` still points to `rabbit`, not `tree`.

---

## Methods Must Be Declared as Methods

❌ This breaks `super`:

```js
eat: function() {}
```

✅ This works:

```js
eat() {}
```

Only **method syntax** sets `[[HomeObject]]`.

---

## Summary

### Inheritance Rules

* `class Child extends Parent`
* Methods are inherited via prototype chain
* `super()` required in derived constructors
* `super.method()` calls parent method
* Arrow functions inherit `super`
* Fields behave differently than methods
* `super` relies on `[[HomeObject]]`

---

## ⭐ Interview One-Liner

> JavaScript class inheritance is built on prototypes; `extends` links prototype chains, `super` calls parent logic, and derived constructors must call `super()` before accessing `this`.

---

## watch videos in seqeunce

- https://www.youtube.com/watch?v=gRILddYACkg&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=9
- https://www.youtube.com/watch?v=3Rst7G-5jQc&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=10


