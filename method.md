## =========================
## ARRAY METHODS (MUST KNOW)
## =========================

### 1. map() — Transform Data
### 2. filter() — Select Data
### 3. reduce() — Aggregate / Group / Build Anything 🔥
### 4. find() — Get First Match
### 5. findIndex()
### 6. some() — Any Match?
### 7. every() — All Match?
### 8. includes()
### 9. slice() — Non-mutating copy
### 10. splice() — Mutates array ⚠️
### 11. sort() — Mutates ⚠️
### 12. flat()
### 13. flatMap()
### 14. Array.from()
### 15. Array.isArray()



## =========================

## OBJECT METHODS (MUST KNOW)

## =========================

### 1. Object.keys()
### 2. Object.values()
### 3. Object.entries() 🔥🔥
### 4. Object.assign()
const returnedTarget = Object.assign(target, source);
return new object
### 5. structuredClone() — Deep Copy (Modern)
### 6. hasOwnProperty()
### 7. Object.hasOwn() (Modern)
const object = {
  prop: "exists",
};
console.log(Object.hasOwn(object, "prop"));
### 8. Object.freeze()
Object.freeze() → Nothing can change
### 9. Object.seal()
Object.seal() → Shape fixed, values can change
### 10. Object.preventExtensions()
Object.preventExtensions() → “No new keys, but I can still edit or delete old ones.”

| Feature           | preventExtensions  | seal           | freeze            |
| ----------------- | ------------------ | -------------- | ----------------- |
| Add properties    | ❌                  | ❌              | ❌                 |
| Delete properties | ✅                  | ❌              | ❌                 |
| Modify values     | ✅                  | ✅              | ❌                 |
| Use case          | Lock shape loosely | Lock structure | Full immutability |

