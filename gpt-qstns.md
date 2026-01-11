## 🟦 Frequency Count (Core)

### Q1. Frequency count using Object  
**Example**
```js
const arr = ["a", "b", "a", "c", "b", "a"];
// Expected Output: { a: 3, b: 2, c: 1 }
````

---

### Q2. Frequency count using Map

**Example**

```js
const arr = ["a", "b", "a", "c", "b", "a"];
// Expected Output: Map { "a" => 3, "b" => 2, "c" => 1 }
```

---

### Q3. Frequency count using reduce

**Example**

```js
const arr = ["a", "b", "a", "c", "b", "a"];
// Expected Output: { a: 3, b: 2, c: 1 }
```

---

### Q4. Frequency count in a string

**Example**

```js
const str = "hello";
// Expected Output: { h:1, e:1, l:2, o:1 }
```

---

### Q5. Find most frequent element

**Example**

```js
const arr = [1, 2, 2, 3, 3, 3, 4];
// Expected Output: 3
```

---

### Q6. Frequency-based problems

**Examples**

```js
// Find duplicates
[1,2,2,3,4,4]

// Majority element
[2,2,1,2,3,2,2]

// Anagram check
("listen", "silent")

// Word count
"hello world hello"

// Voting system
["A","B","A","C","A"]
```

---

## 🟦 Map Questions

### Q7. Extract IDs from users

**Example**

```js
const users = [
  { id: 1, name: "jitendra" },
  { id: 2, name: "rahul" },
  { id: 3, name: "ankit" },
];
// Expected Output: [1, 2, 3]
```

---

### Q8. Convert paise to rupees

**Example**

```js
const prices = [1999, 2500, 3499];
// Expected Output: ["₹19.99", "₹25", "₹34.99"]
```

---

### Q9. Fix bug in map logic

**Example**

```js
const arr = [1, 2, 3];
// Buggy map usage to multiply elements by 2
```

---

### Q10. Add derived property using map

**Example**

```js
const products = [
  { id: 1, name: "Phone", price: 20000 },
  { id: 2, name: "Laptop", price: 50000 },
];
// Expected: add priceWithTax (18%)
```

---

### Q11. Prefix items with 1-based index

**Example**

```js
const arr = ["apple", "banana", "mango"];
// Expected Output: ["1. apple", "2. banana", "3. mango"]
```

---

## 🟦 Filter Questions

### Q12. Extract valid user names

**Example**

```js
const users = [{ name: "jitendra" }, null, { name: "rahul" }, undefined];
// Expected Output: ["jitendra", "rahul"]
```

---

### Q13. Filter active users

**Example**

```js
const users = [
  { id: 1, name: "Jitendra", active: true },
  { id: 2, name: "Rahul", active: false },
  { id: 3, name: "Ankit", active: true },
];
// Expected Output: active users only
```

---

### Q14. Remove falsy values

**Example**

```js
const arr = [0, 1, false, 2, "", 3, null, undefined];
// Expected Output: [1, 2, 3]
```

---

### Q15. Filter events after a date

**Example**

```js
const events = [
  { id: 1, date: "2023-12-30" },
  { id: 2, date: "2024-01-05" },
  { id: 3, date: "2024-03-10" },
];
// Filter events after 1 Jan 2024
```

---

### Q16. Search users by substring

**Example**

```js
const users = [
  { name: "Rahul" },
  { name: "Ankit" },
  { name: "Ramesh" },
  { name: "Suresh" },
];
// Filter names containing "ra"
```

---

### Q17. Filter transactions between dates

**Example**

```js
const transactions = [
  { id: 1, date: "2024-01-20" },
  { id: 2, date: "2024-02-10" },
  { id: 3, date: "2024-03-15" },
  { id: 4, date: "2024-04-01" },
];
// Between 1 Feb 2024 and 31 Mar 2024
```

---

### Q18. Filter today’s records

**Example**

```js
const records = [
  { id: 1, createdAt: "2025-01-01" },
  { id: 2, createdAt: "2025-01-21" },
];
// Filter records created today
```

---

### Q19. Filter valid coupons

**Example**

```js
const coupons = [
  { code: "A", expiresOn: "2024-01-01" },
  { code: "B", expiresOn: "2026-01-01" },
];
// Filter non-expired coupons
```

---

## 🟦 Reduce Questions

### Q20. Calculate days between two dates

**Example**

```js
const startDay = new Date("2024-03-01");
const endDay = new Date("2024-03-10");
// Expected Output: 9
```

---

### Q21. Sum of array

**Example**

```js
const arr = [1, 2, 3, 4, 5];
// Expected Output: 15
```

---

### Q22. Find maximum value

**Example**

```js
const arr = [10, 5, 20, 8];
// Expected Output: 20
```

---

### Q23. Group and sum by category

**Example**

```js
const items = [
  { category: "food", amount: 100 },
  { category: "travel", amount: 300 },
  { category: "food", amount: 50 },
];
// Expected Output: { food: 150, travel: 300 }
```

---

### Q24. Count active vs inactive

**Example**

```js
const users = [{ active: true }, { active: false }, { active: true }];
// Expected Output: { active: 2, inactive: 1 }
```

---

### Q25. Remove duplicates

**Example**

```js
const arr = [1, 2, 2, 3, 4, 4, 5];
// Expected Output: [1, 2, 3, 4, 5]
```

---

### Q26. Flatten 1-level nested array

**Example**

```js
const arr = [[1, 2], [3, 4], [5]];
// Expected Output: [1, 2, 3, 4, 5]
```

---

### Q27. Group objects by role

**Example**

```js
const users = [{ role: "admin" }, { role: "user" }];
// Expected Output: { admin: [...], user: [...] }
```

---

### Q28. Group primitive values

**Example**

```js
const arr = ["a", "b", "a"];
// Expected Output: { a: ["a","a"], b: ["b"] }
```

---

### Q29. Cart summary (Advanced)

**Example**

```js
const cart = [
  { id: 1, name: "Phone", price: 20000, qty: 2 },
  { id: 2, name: "Charger", price: 1000, qty: 3 },
  { id: 3, name: "Phone", price: 20000, qty: 1 },
];
// Build items summary + grandTotal
```

---

### Q30. Group payments by status

**Example**

```js
const payments = [
  { status: "success", amount: 1000 },
  { status: "failed", amount: 500 },
  { status: "success", amount: 2000 },
  { status: "pending", amount: 700 },
];
// Group by status + totals
```

---
