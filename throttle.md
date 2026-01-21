
---

### What is **Throttle**?

* **Throttle limits execution of a function to once every fixed time interval**, no matter how many times the event fires.

---

### Think:

* User keeps scrolling → ✅ run at fixed intervals
* User keeps resizing → ✅ run at fixed intervals
* User keeps clicking → ✅ run at fixed intervals

---

### Why do we need throttle?

Without throttle:

* Function runs **continuously**
* Heavy calculations
* UI jank / performance issues

With throttle:

* Function runs **at most once every X ms**
* Controlled execution
* Smooth performance

---

### Implementation (Basics)

```js
// Before Throttle

function handleScroll() {
  console.log("Scroll event");
}

window.addEventListener("scroll", handleScroll);
```

```js
// After Throttle

function throttle(fn, delay) {
  let isThrottled = false;

  return function () {
    if (isThrottled) return;

    fn();
    isThrottled = true;

    setTimeout(() => {
      isThrottled = false;
    }, delay);
  };
}

window.addEventListener("scroll", throttle(handleScroll, 300));
```

---

### Implementation (Advanced)

### Problem – you can’t access `e` or `this` properly

```js
function throttle(fn, delay) {
  let isThrottled = false;

  return function (...args) {
    if (isThrottled) return;

    fn.apply(this, args);
    isThrottled = true;

    setTimeout(() => {
      isThrottled = false;
    }, delay);
  };
}
```

---

### I do NOT want to use arrow function here

```js
function throttle(fn, delay) {
  let isThrottled = false;

  return function (...args) {
    if (isThrottled) return;

    let context = this;
    fn.apply(context, args);
    isThrottled = true;

    setTimeout(function () {
      isThrottled = false;
    }, delay);
  };
}
```

---

### Real-World Examples

```js
window.addEventListener(
  "scroll",
  throttle(() => {
    console.log("Fetching next batch...");
  }, 500)
);
```

```js
window.addEventListener(
  "resize",
  throttle(() => {
    console.log("Window resized");
  }, 300)
);
```


```jsx
With React
import { useEffect, useState } from "react";

function useDebounce(value, delay = 500) {
   const [debouncedValue, setDeboucnedValue] = useState('');

   useEffect( () => {
       const timer = setTimeout( () => {
            setDeboucnedValue(value)
       },  delay)

       return () => {
           clearTimeout(timer);
       }
   }, [value, delay] )


   return debouncedValue;
}

export default useDebounce;


import { useEffect, useState } from "react";

import useDebounce from "./useDebounce";

function Search() {
    const [searchInput, setSearchInput] = useState('');

    const debouncedValue = useDebounce(searchInput,300);

    const handleChange = (e) => {
        setSearchInput(e.target.value);
    }

    useEffect( () => {
        if(!debouncedValue.trim()) return;
        console.log('calling ..API....', debouncedValue)
    }, [debouncedValue])

    return (
        <>
        <h1>this is my search box..</h1>

        <input placeholder="enter your name" value={searchInput} onChange={handleChange} />
        </>
    )
}

export default Search;


```

---

### Key Difference (Debounce vs Throttle)

| Debounce              | Throttle                |
| --------------------- | ----------------------- |
| Runs after user stops | Runs at fixed intervals |
| Waits                 | Limits                  |
| Search input          | Scroll / resize         |
| API calls             | UI events               |

---

### Analogy

* User typing → **Debounce**
* User scrolling → **Throttle**

---

## 🏆 Interview-Ready One-Liner

> **Throttle ensures a function runs at most once in a given time interval, preventing performance issues during continuous events like scrolling or resizing.**

---

