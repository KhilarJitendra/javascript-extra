

---

### Q1

```js
function outer() {
  let a = 10;
  return function inner() {
    a++;
    console.log(a);
  };
}
const fn = outer();
fn();
fn();
```

---

### Q2

```js
console.log(a);
var a = 20;
var a = 10;
```

---

### Q3

```js
var a = 10;
function foo() {
  var a = 20;
  console.log(a);
}
foo();
console.log(a);
```

---

### Q4

```js
function outer() {
  let x = 10;
  function inner() {
    console.log(x);
  }
  inner();
  x = 20;
  // inner();
}
outer();
```


---

### Q5

```js
(function () {
  var a = 10;
})();
console.log(a); // a is not defined
```

---



