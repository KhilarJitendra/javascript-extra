### What is Debounce ?

- Debounce delays execution of a function until the user stops doing something for a certain time.

### Think:

- User keeps typing → ❌ don’t run

- User stops typing for X ms → ✅ run once

### Why do we need debounce? 

- Function runs on every keystroke

- Too many API calls

- Performance issues

With debounce:

- Function runs only once after user pauses


### Implementaion (Basics)

```js

// Before Debounce

// html

 <input id="input" class="input-class" />

function fetchResults() {
  console.log("API Calling");
}

document.getElementById("input").addEventListener("input", (e) => {
  fetchResults(e);
});

// After debounce

function debounce(fn, delay) {
  let timer;

  return function () {
    clearTimeout(timer);
    timer = setTimeout(() => {
      fn();
    }, delay);
  };
}

document
  .getElementById("input")
  .addEventListener("input", debounce(fetchResults, 300));

```

### Implementaion (Advanced)

```js
Problem - you can't get e.target.value since it looses 'this' context

function debounce(fn, delay) {
  let timer;

  return function (...args) {
    clearTimeout(timer);
    timer = setTimeout(() => {
      fn.apply(this, args); // passed this and args it takes array of input
      // fn.call(this, ...args); // if we use call 
    }, delay);
  };
}

// I do not want to use arrow function here -

function debounce(fn, delay) {
  let timer;

  return function (...args) {
    clearTimeout(timer);
    let context = this; // added context
    timer = setTimeout(function () {
      fn.apply(context, args); // passing as argument
    }, delay);
  };
}

```

### Analogy 

- User typing → Debounce
- User scrolling → Throttle
