# Object-Oriented Programming (OOP)

## Programming Paradigms

* **Procedural / Functional Programming**
* **Object-Oriented Programming (OOP)**

---

## What is OOP?

* **OOP is a programming paradigm** based on the concept of **objects**
* In OOP, we represent **real-world entities as objects**
* An object contains:

  * **Properties** → data / state
  * **Methods** → behavior

---

## Example: Object in JavaScript

```js
let user = {
  // Properties (data)
  name: "John",
  color: "black",

  // Methods (behavior)
  addUser() {
    // logic to add user
  },

  removeUser() {
    // logic to remove user
  }
};
```

---

## Core Components of OOP

### 1. Properties

* Variables that store data of an object
* Example: `name`, `color`

### 2. Methods

* Functions that define what an object can do
* Example: `addUser()`, `removeUser()`

---

## Four Pillars of OOP

### 1. Encapsulation

* **Hiding internal data** and exposing only what is necessary
* Achieved using access control and methods

📌 *Example:* User data can only be modified through methods, not directly.

---

### 2. Abstraction

* **Hiding implementation details**
* Showing only **essential functionality** to the user

📌 *Example:* Using `startCar()` without knowing how the engine works.

---

### 3. Inheritance

* Creating a **new class from an existing (parent) class**
* Promotes **code reusability**

📌 *Example:* `AdminUser` inherits from `User`

---

### 4. Polymorphism

* **Same method name, different behavior**
* Achieved via method overriding

📌 *Example:*
`login()` behaves differently for `User` and `Admin`

---

## OOP Support in JavaScript

* JavaScript **supports OOP**
* `class` in JavaScript is **syntactic sugar**
* Internally:

  ```js
  typeof class === "function"
  ```

---

## JavaScript Class Basics

```js
class User {
  constructor(name) {
    this.name = name; // field / property
  }

  sayHi() {
    console.log(this.name);
  }
}
```

### Key Points

* A class can have:

  * **Constructor**
  * **Fields (properties)**
  * **Prototype methods**
  * **Getters / Setters**
* Constructor:

  * Runs **automatically**
  * Used for **initialization**
  * Only **one constructor per class**
  * Optional

---

## Prototype Behavior

```js
Object.getOwnPropertyNames(User.prototype);
```

* Methods are stored in the **prototype**
* Methods are **non-enumerable**

```js
for (const key in user) {
  console.log(key);
}
```

✔ Only instance properties are logged
❌ Methods are skipped

---

## Classes in JavaScript

* Classes are always in **strict mode**
* Methods are added to the **prototype**
* Cannot be called without `new`

---

## Class Expressions

### Anonymous Class Expression

```js
let User = class {
  sayHi() {
    console.log("Hi");
  }
};
```

### Named Class Expression

```js
let User = class MyClass {
  sayHi() {
    console.log(MyClass); // accessible only inside class
  }
};
```

---

## `this` Keyword in Classes

* `this` refers to the **current instance**
* Depends on **how the method is called**

```js
class User {
  name = "John";

  sayHi() {
    console.log(this.name);
  }
}

const user = new User();
user.sayHi(); // John
```

---

## Common Pitfall: Losing `this`

```js
const hi = user.sayHi;
hi(); // ❌ undefined (this is lost)
```

### Fix using `bind`

```js
const hi = user.sayHi.bind(user);
hi(); // ✅ John
```


## Watch this videos in Sequence 

- https://www.youtube.com/watch?v=FMIuwvt0vGQ&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH
- https://www.youtube.com/watch?v=hZqKSFReHc8&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=2
- https://www.youtube.com/watch?v=vXnUn2UkSJI&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=3
- https://www.youtube.com/watch?v=kcElZorPa7c&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=4
- https://www.youtube.com/watch?v=gPi3nMF1u-Q&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=5
- https://www.youtube.com/watch?v=vmVAvNIaf6Q&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=6


