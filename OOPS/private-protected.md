---

## (14) Private and Protected Properties & Methods (Encapsulation)

---

## Encapsulation (Core OOP Principle)

**Encapsulation** means **delimiting the internal interface from the external one**.

* Internal details are hidden
* External usage stays simple and safe
* This is **mandatory** for any non-trivial application

> In OOP terms, this separation is called **encapsulation**.

---

## Real-Life Analogy: Coffee Machine ☕

* Outside: button, display → easy to use
* Inside: boiler, heater, wiring → hidden complexity

If internal parts were exposed:

* Harder to use
* Dangerous
* Easy to break

👉 **Objects in programming work the same way**

---

## Internal vs External Interface

### 🔹 Internal Interface

* Properties/methods used **inside the class**
* Implementation details
* Should NOT be accessed externally

### 🔹 External Interface

* Properties/methods accessible from outside
* Public API of the object

---

## Types of Fields in JavaScript

JavaScript supports:

| Type                       | Access                |
| -------------------------- | --------------------- |
| **Public**                 | Anywhere              |
| **Protected (convention)** | Class + subclasses    |
| **Private (#)**            | Only inside the class |

⚠️ **Protected is NOT enforced by JS**, only a convention
✅ **Private is enforced by the language**

---

## Public Properties (Default)

```js
class CoffeeMachine {
  waterAmount = 0;

  constructor(power) {
    this.power = power;
  }
}

const machine = new CoffeeMachine(100);
machine.waterAmount = 200; // allowed
```

❌ No control over invalid values.

---

## Protected Properties (Convention: `_`)

* Prefix with `_`
* Signals: *“Do not touch from outside”*
* Not enforced, but respected by developers

---

### Protecting `waterAmount`

```js
class CoffeeMachine {
  _waterAmount = 0;

  set waterAmount(value) {
    if (value < 0) value = 0;
    this._waterAmount = value;
  }

  get waterAmount() {
    return this._waterAmount;
  }

  constructor(power) {
    this._power = power;
  }
}

const machine = new CoffeeMachine(100);
machine.waterAmount = -10; // becomes 0
```

✅ Controlled access
❌ Still technically accessible (`machine._waterAmount`)

---

## Read-Only Property (Getter Only)

```js
class CoffeeMachine {
  constructor(power) {
    this._power = power;
  }

  get power() {
    return this._power;
  }
}

const machine = new CoffeeMachine(100);
console.log(machine.power); // 100
machine.power = 50; // ❌ Error (no setter)
```

---

## Getter / Setter vs Methods

### Using Getter / Setter

```js
get waterAmount() {}
set waterAmount(value) {}
```

### Using Methods (Preferred Often)

```js
class CoffeeMachine {
  _waterAmount = 0;

  setWaterAmount(value) {
    if (value < 0) value = 0;
    this._waterAmount = value;
  }

  getWaterAmount() {
    return this._waterAmount;
  }
}
```

📌 Methods are:

* More flexible
* Can accept multiple parameters
* Easier to evolve

---

## Protected Fields Are Inherited

```js
class MegaMachine extends CoffeeMachine {
  increaseWater() {
    this._waterAmount += 10; // allowed
  }
}
```

✅ Accessible in subclasses
❌ Still not truly private

---

## Private Fields (`#`) — Language Level

⚠️ **Recent addition to JavaScript**

* Enforced by the language
* Accessible only inside the class
* Not accessible in subclasses

---

### Private Field Example

```js
class CoffeeMachine {
  #waterLimit = 200;

  #fixWaterAmount(value) {
    if (value < 0) return 0;
    if (value > this.#waterLimit) return this.#waterLimit;
    return value;
  }

  setWaterAmount(value) {
    this.#waterLimit = this.#fixWaterAmount(value);
  }
}

const machine = new CoffeeMachine();
machine.#waterLimit = 1000; // ❌ Error
machine.#fixWaterAmount(10); // ❌ Error
```

---

## Private + Public Together

```js
class CoffeeMachine {
  #waterAmount = 0;

  get waterAmount() {
    return this.#waterAmount;
  }

  set waterAmount(value) {
    if (value < 0) value = 0;
    this.#waterAmount = value;
  }
}

const machine = new CoffeeMachine();
machine.waterAmount = 100;
```

❌ `machine.#waterAmount` → Error

---

## Private Fields Are NOT Inherited

```js
class MegaCoffeeMachine extends CoffeeMachine {
  method() {
    console.log(this.#waterAmount); // ❌ Error
  }
}
```

📌 Must use public getters/setters

---

## Private Fields Are Not Dynamic

```js
this['#name']; // ❌ Not allowed
```

Private fields:

* Cannot be accessed via bracket notation
* Ensures strict privacy

---

## Protected vs Private (Quick Comparison)

| Feature                | Protected `_` | Private `#` |
| ---------------------- | ------------- | ----------- |
| Language enforced      | ❌             | ✅           |
| Accessible in subclass | ✅             | ❌           |
| External access        | Possible      | Impossible  |
| Flexibility            | High          | Strict      |

---

## Why Encapsulation Matters

### ✅ Protection

Prevents accidental misuse of internals

### ✅ Maintainability

Internal changes don’t break users

### ✅ Flexibility

Private methods can be renamed or removed safely

### ✅ Simplicity

Users see a clean, simple API

---

## Best Practice Summary

* Use **public** for API
* Use **protected (`_`)** for extensible internals
* Use **private (`#`)** for strict encapsulation
* Prefer **protected** in frameworks
* Prefer **private** in closed implementations

---

## ⭐ Interview One-Liner

> Encapsulation in JavaScript is achieved using public fields, protected fields by convention (`_`), and private fields (`#`) to hide internal implementation and expose a clean external interface.

---
