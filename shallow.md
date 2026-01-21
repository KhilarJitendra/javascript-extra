### What is Shallow Copy 
---
A shallow copy creates a new object/array, but nested objects are still shared by reference.
---

Example 

``` js
const original = {
  name: "Jitendra",
  address: { city: "Bangalore" }
};

const shallowCopy = { ...original };

shallowCopy.address.city = "Delhi";

console.log(original.address.city); // ❌ "Delhi" (changed!)

```

### Common ways to make a shallow copy

```js
// Objects
{ ...obj }
Object.assign({}, obj)

// Arrays
[...arr]
arr.slice()
Array.from(arr)
```

### when to use 

- When data is flat (no nested objects)

- For performance reasons

- Common in React state updates (with care)

### Example 

```JS

const obj = {
  name: "Jitendra",
  coding: {
    language: "JS",
    systemDesign: "YES",
    dsa: {
      searching: "YES",
    },
  },
};

// shallow copy
const newObj = Object.assign({}, obj);
newObj.coding.language = "C++";
console.log(obj);

// using spread operator (but here nested object also shared by reference)

const newObj = {
  ...obj,
  coding: {
    ...obj.coding,
    language: 'C++'
  }
}

```
