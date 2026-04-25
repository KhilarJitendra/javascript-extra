# OOPS (Object Oriented Programming)

## 1. What is OOPS?

OOPs is an Object Oriented Programming paradigm that structures code using objects that contain data (properties) and behaviour (methods).  
Instead of writing everything as separate functions, we can create a blueprint (class).

### Four Core Principles
- Encapsulation (Data hiding)
- Abstraction (Show only necessary details)
- Inheritance (Reuse code)
- Polymorphism (Same method behaves differently)

### In JavaScript
Class is syntactic sugar over prototypes.

```js
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function () {
  return `Hello my name is ${this.name}`;
};

const p1 = new Person('John', 25);
````

---

## 2. Inheritance

```js
class Animal {
  speak() {
    return `Animal makes sound`;
  }
}

class Dog extends Animal {
  bark() {
    return `Dog barks`;
  }
}
```

### Example with constructor

```js
class Person {
  constructor(name) {
    this.name = name;
  }
}

class Employee extends Person {
  constructor(name, role) {
    super(name);
    this.role = role;
  }
}

// const obj1 = new Employee('Jitendra', "FE role");
```

---

## 3. Getter and Setter

* Getter and setter method names must be same
* We can have multiple getters and setters in a class

```js
class Student {
  constructor(name, city) {
    this._name = name;
    this._city = city;
  }

  get name() {
    return this._name.toUpperCase();
  }

  set name(value) {
    this._name = value.trim();
  }

  get city() {
    return this._city;
  }

  set city(value) {
    this._city = value;
  }
}

const obj2 = new Student('Jitendra');

obj2.name = '    john    ';
obj2.city = 'RKL';

console.log(obj2.name);
console.log(obj2.city);
```

---

## 4. Private and Protected

* Private → `#balance`
* Protected → `_balance` (convention, no strict enforcement)

```js
class BankAccount {
  #balance = 0;

  deposit(amount) {
    this.#balance += amount;
  }

  getBalance() {
    return this.#balance;
  }
}

const cust1 = new BankAccount();
cust1.deposit(900);
cust1.deposit(1900);
console.log(cust1.getBalance());
```

---

## 5. Static Properties

Belongs to class, not object

```js
class Mathutil {
  static add(a, b) {
    return a + b;
  }
}

console.log(Mathutil.add(12, 10));
```

---

## 6. Instance Counter Example

```js
class Programming {
  static counter = 0;

  constructor() {
    Programming.counter += 1;
  }

  static counterValue() {
    return Programming.counter;
  }
}

const obj11 = new Programming();
const obj22 = new Programming();

console.log(Programming.counterValue());
```
