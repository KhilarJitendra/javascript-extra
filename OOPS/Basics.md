---

# Object-Oriented Programming (OOPs) in JavaScript

---

## (1) What is OOPs?

**Object-Oriented Programming (OOP)** is a programming paradigm that organizes code around **objects** (data + functions) to model real-world entities.

* Objects combine **state (properties)** and **behavior (methods)**
* Promotes reusable, maintainable, and scalable code
* Uses core concepts like:

  * **Classes**
  * **Encapsulation**
  * **Inheritance**
  * **Polymorphism**
  * **Abstraction**

---

## (2) OOPs in JavaScript

* JavaScript supports OOP, but with its **own flavor**
* It is **prototype-based**, not class-based at the core
* `class` syntax is **syntactic sugar over prototypes**

### ❌ Not Supported Like Classical OOP Languages (Java / C++)

JavaScript does **NOT natively support**:

* ❌ Method Overloading
* ❌ Multiple Inheritance
* ❌ Interfaces
* ❌ Abstract Classes (native keyword)
* ❌ Protected Access Modifier
* ❌ Static Typing

> ⚠️ **Correction (important):**
> **Method Overriding IS supported in JavaScript**, via prototype chain and `extends`.

---

## (3) What is a Class (JS-specific)?

* A **class** is a blueprint to create multiple similar objects
* In JavaScript, a class is actually a **function under the hood**

A class groups:

* `constructor`
* Prototype methods
* Getters / Setters
* Fields (properties)

```js
typeof User; // "function"
```

---

## (4) Basic Class Syntax

```js
class MyClass {
  constructor() {}
  method1() {}
  method2() {}
}
```

Key points:

* `new` is used to create objects
* `constructor()` runs automatically
* Methods are added to the **prototype**

---

## (5) Object Creation Flow (`new` keyword)

```js
new User("John");
```

Internally, JavaScript does:

1. Creates a new empty object `{}`
2. Sets `this` → new object
3. Calls `constructor()`
4. Links object to `User.prototype`
5. Returns the object

---

## (6) Constructor Rules

* Only **one constructor** per class
* Constructor is **optional**
* Used only for **initialization**

```js
constructor(name) {
  this.name = name;
}
```

If omitted, JS adds an empty constructor automatically.

---

## (7) Where Do Methods Live?

* All methods live on `ClassName.prototype`
* Instances **do not copy methods**

```js
User.prototype.sayHi;
```

```js
Object.getOwnPropertyNames(User.prototype);
// ["constructor", "sayHi"]
```

---

## (8) Class Methods Are Non-Enumerable

```js
for (let key in user) {
  console.log(key);
}
```

* Only **instance properties** are logged
* Methods are skipped (non-enumerable)

---

## (9) Classes Are Always in Strict Mode

* Code inside classes runs in **`"use strict"`**
* Prevents:

  * Undeclared variables
  * Silent errors
  * Accidental globals

(No need to write `"use strict"` manually)

---

## (10) Class Expressions

### Anonymous class expression

```js
let User = class {
  sayHi() {}
};
```

### Named class expression

```js
let User = class MyClass {
  sayHi() {
    console.log(MyClass); // visible only inside class
  }
};
```

* Class name is **scoped to class body only**

---

## (11) Class Fields vs Constructor Assignment

### Class Field

```js
class User {
  name = "John";
}
```

### Constructor Assignment

```js
class User {
  constructor() {
    this.name = "John";
  }
}
```

✅ Both are valid
📌 Class fields are cleaner for defaults
📌 Constructor is better for dynamic values

---

## (12) `this` in Class

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
user.sayHi(); // "John"
```

### Common Pitfall

```js
const hi = user.sayHi;
hi(); // ❌ undefined (this lost)
```

### Fix with binding

```js
const hi = user.sayHi.bind(user);
hi(); // "John"
```

---

## (13) Watch this videos in Sequence 

- https://www.youtube.com/watch?v=FMIuwvt0vGQ&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH
- https://www.youtube.com/watch?v=hZqKSFReHc8&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=2
- https://www.youtube.com/watch?v=vXnUn2UkSJI&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=3
- https://www.youtube.com/watch?v=kcElZorPa7c&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=4
- https://www.youtube.com/watch?v=gPi3nMF1u-Q&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=5
- https://www.youtube.com/watch?v=vmVAvNIaf6Q&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=6


