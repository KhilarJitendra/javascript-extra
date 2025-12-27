### What is Deep Copy 
---
A deep copy creates a completely independent copy — all nested objects are duplicated.

- Top-level copied
- Nested level also copied
- No shared references
---

Example 

``` js
const original = {
  name: "Jitendra",
  address: { city: "Bangalore" }
};

const deepCopy = structuredClone(original);

deepCopy.address.city = "Delhi";

console.log(original.address.city); // ✅ "Bangalore"

```

### Common ways to make a deep copy

```js
structuredClone(obj)
JSON.parse(JSON.stringify(obj)) - OLD Not used
```

### when to use 

- Nested objects

- Prevent accidental mutations

- Complex state (Redux, APIs, configs)

----
Shallow copy copies references for nested objects, while deep copy duplicates the entire object structure so changes don’t affect the original.
----

### Implementaion (Polyfill)

```js
const original = {
  name: "Jitendra",
  address: { city: "Bangalore" },
  skills: ["JS", "React"],
};

function deepCopy(value) {
  // base condition here.... at the end we have primitive value only like string

  if (value !== null || typeof value !== "object") {
    return value;
  }

  let result = Array.isArray(value) ? [] : {};

  // now Loop

  for (const key in value) {
    if (value.hasOwnProperty(key)) {
      result[key] = deepCopy(value[key]);
    }
  }

  return result;
}

const modified = deepCopy(original);

console.log(modified);

```







