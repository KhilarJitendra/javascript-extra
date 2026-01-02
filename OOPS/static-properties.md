---

## (13) Static Properties and Methods (JavaScript)

---

## What are Static Methods?

* **Static methods belong to the class itself**, not to instances
* Declared using the `static` keyword
* Called directly on the class

```js
class User {
  static staticMethod() {
    console.log(this === User);
  }
}

User.staticMethod(); // true
```

### Under the hood (equivalent code)

```js
class User {}

User.staticMethod = function () {
  console.log(this === User);
};

User.staticMethod(); // true
```

📌 `this` inside a static method refers to the **class constructor**, not an instance.

---

## Why Use Static Methods?

Static methods are used for:

* Utility / helper functions
* Logic related to the **class as a whole**
* Factory methods
* Database-style operations (find, create, delete)

They are **not tied to a specific object instance**.

---

## Example: Static Compare Method

```js
class Article {
  constructor(title, date) {
    this.title = title;
    this.date = date;
  }

  static compare(articleA, articleB) {
    return articleA.date - articleB.date;
  }
}

let articles = [
  new Article("HTML", new Date(2019, 1, 1)),
  new Article("CSS", new Date(2019, 0, 1)),
  new Article("JavaScript", new Date(2019, 11, 1))
];

articles.sort(Article.compare);

console.log(articles[0].title); // CSS
```

📌 `Article.compare` works **above instances**, not on them.

---

## Example: Static Factory Method

Used when you want **multiple ways to create objects**.

```js
class Article {
  constructor(title, date) {
    this.title = title;
    this.date = date;
  }

  static createTodays() {
    return new this("Today's digest", new Date());
  }
}

const article = Article.createTodays();
console.log(article.title); // Today's digest
```

📌 Factory methods:

* Improve readability
* Encapsulate creation logic
* Avoid constructor overloading (which JS doesn’t support)

---

## Example: Database-Style Static Methods

```js
class Article {
  static remove({ id }) {
    console.log(`Removing article with id ${id}`);
  }
}

Article.remove({ id: 12345 });
```

📌 Common in ORMs, services, repositories.

---

## Static Methods Are NOT Available on Instances

```js
article.createTodays(); 
// ❌ Error: article.createTodays is not a function
```

✔️ Static → class
❌ Instance → cannot access static methods

---

## Static Properties (Recent Addition)

Static properties belong to the class itself.

```js
class Article {
  static publisher = "Ilya Kantor";
}

console.log(Article.publisher); // Ilya Kantor
```

Equivalent to:

```js
Article.publisher = "Ilya Kantor";
```

---

## Inheritance of Static Properties and Methods

Static members **are inherited** by child classes.

```js
class Animal {
  static planet = "Earth";

  constructor(name, speed) {
    this.name = name;
    this.speed = speed;
  }

  static compare(a, b) {
    return a.speed - b.speed;
  }
}

class Rabbit extends Animal {}

const rabbits = [
  new Rabbit("White Rabbit", 10),
  new Rabbit("Black Rabbit", 5)
];

rabbits.sort(Rabbit.compare);

console.log(Rabbit.planet); // Earth
```

📌 `Rabbit.compare` comes from `Animal.compare`.

---

## How Static Inheritance Works (Prototype Chain)

When using `extends`, JavaScript creates **two prototype links**:

```js
class Animal {}
class Rabbit extends Animal {}

// Static inheritance
Rabbit.__proto__ === Animal; // true

// Instance method inheritance
Rabbit.prototype.__proto__ === Animal.prototype; // true
```

### Summary of Prototype Links

| Purpose          | Prototype Chain                       |
| ---------------- | ------------------------------------- |
| Static methods   | `Rabbit → Animal`                     |
| Instance methods | `Rabbit.prototype → Animal.prototype` |

---

## ⭐ Interview One-Liner

> Static methods and properties belong to the class itself, not instances, and are commonly used for utility logic, factory methods, and class-level operations.
> Count the frequency whenever object is created

```js
class Counter {
  static #count = 0;
  constructor() {
    Counter.#count++;
  }

  static getCount() {
    return Counter.#count;
  }
}

const ob1 = new Counter();
const ob2 = new Counter();
const ob3 = new Counter();

console.log(Counter.getCount());

```

---

### watch videos in sequence 

- https://www.youtube.com/watch?v=3037A244awI&list=PL1BztTYDF-QOvKYBBYdjzHISCeaYCAEfH&index=7

