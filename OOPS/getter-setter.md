## What is getter and setter in JS ?

- We use getters and setters to protect internal data and enforce business rules while keeping the external API simple and intuitive.
- It implement encapsulation
- Getter = asking for information
- Setter = enforcing rules while changing information

## Real World Example 

  - “The balance is stored internally, and the getter allows safe reading of it, while the setter enforces rules like preventing negative balances. This keeps the data protected while exposing a clean API.”
  - Getter = checking balance
  - Setter = bank approval before updating balance

## Code 

```js

class BankAccount {
  constructor(balance) {
    this._balance = balance;
  }

  get balance() {
    return this._balance; // check balance
  }

  set balance(amount) {
    if (amount < 0) {
      throw new Error("Balance cannot be negative");
    }
    this._balance = amount;
  }
}

const acc = new BankAccount(1000);

acc.balance;        // getter → 1000
acc.balance = 500;  // setter → allowed
acc.balance = -200; // ❌ blocked

```
