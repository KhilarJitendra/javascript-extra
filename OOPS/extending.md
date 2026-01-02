---

## (15) Extending Built-in Classes (Array, Map, Set, etc.)

---

## Extending Built-in Classes

JavaScript allows extending **built-in classes** such as:

* `Array`
* `Map`
* `Set`
* `Date`
* `Error`

This enables adding **custom behavior** on top of native objects.

---

## Example: Extending `Array`

```js
class PowerArray extends Array {
  isEmpty() {
    return this.length === 0;
  }
}

const arr = new PowerArray(1, 2, 5, 10, 50);

console.log(arr.isEmpty()); // false
```

---

## Built-in Methods Preserve the Derived Type

A very important behavior:

```js
const filteredArr = arr.filter(item => item >= 10);

console.log(filteredArr); // PowerArray [10, 50]
console.log(filteredArr.isEmpty()); // false
```

📌 Methods like `map`, `filter`, `slice` return **objects of the derived class**.

Why?

```js
arr.constructor === PowerArray; // true
```

Internally, JS uses:

```
new arr.constructor(...)
```

So the derived type is preserved automatically.

---

## Customizing Returned Type: `Symbol.species`

You can control what constructor is used internally by overriding `Symbol.species`.

### Force Built-in Methods to Return `Array`

```js
class PowerArray extends Array {
  isEmpty() {
    return this.length === 0;
  }

  static get [Symbol.species]() {
    return Array;
  }
}

const arr = new PowerArray(1, 2, 5, 10, 50);

const filteredArr = arr.filter(item => item >= 10);

console.log(filteredArr instanceof Array); // true
console.log(filteredArr instanceof PowerArray); // false
```

```js
filteredArr.isEmpty(); 
// ❌ Error: isEmpty is not a function
```

📌 Extended behavior does **not propagate** further.

---

## When to Use `Symbol.species`

Use it when:

* You want custom methods only on original instances
* You want built-in methods to return **standard arrays**
* You want to avoid leaking subclass behavior

---

## Other Built-in Collections

The same behavior applies to:

* `Map`
* `Set`
* `TypedArray`

They also respect `Symbol.species`.

---

## No Static Inheritance for Built-ins

Built-in classes behave **differently** from user-defined classes.

### Example

Although:

```js
Array extends Object
Date extends Object
```

They **do NOT inherit static methods** from `Object`.

```js
Object.keys({ a: 1 }); // ✅
Array.keys();          // ❌
Date.keys();           // ❌
```

---

## Why?

Prototype chains differ:

```
Date.prototype → Object.prototype
Array.prototype → Object.prototype

Date → ❌ Object
Array → ❌ Object
```

Only **instances** inherit from `Object.prototype`.

---

## Comparison with `extends`

| Feature                  | Custom Classes | Built-in Classes |
| ------------------------ | -------------- | ---------------- |
| Instance inheritance     | ✅              | ✅                |
| Static inheritance       | ✅              | ❌                |
| `Symbol.species` support | ✅              | ✅                |
| Prototype behavior       | Normal         | Special          |

---

## ⭐ Interview One-Liner

> JavaScript allows extending built-in classes like Array, and derived instances preserve their type in methods like map and filter unless customized using `Symbol.species`.

---
