## What is Memoization ?

- Memoization is a performance optimization technique where you cache the result of a function so
  that future calls with the same input return instantly instead of recomputing.
- Memoization stores function results based on inputs to avoid repeated expensive calculations.

- Implementation

```js
function Computer(a, b) {
  console.log("Computting....");
  const result = a + b + a * b + (a + b);
  return result;
}
const cache = {};
function memoization(a, b) {
  const key = a + ":" + b;
  if (!cache[key]) {
    const result = Computer(a, b);
    cache[key] = result;
    return cache[key];
  } else {
    cache[key];
  }
}

console.log(memoization(12, 12));
console.log(memoization(12, 12));
```

| Memoization     | Caching                |
| --------------- | ---------------------- |
| Function-level  | System-level           |
| Based on inputs | Based on keys/requests |
| In-memory       | Can be Redis, DB       |
