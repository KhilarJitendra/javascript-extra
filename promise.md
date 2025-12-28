### 1. What is callback ?

A callback in JavaScript is a function that is passed as an argument to another function and executed later, usually after some task finishes.

```js

const cart = ["paints", "shirts", "watches"];

api.createOrder(cart, function () {
  api.proceedtoPayment(function () {
    api.showOrderSummary(function () {
      api.updateWallet();
    });
  });
});

```

#### Issues 

- callback inside callback (called callback hell or Pyramid of Doom)
- inversion of control

### Solution

- We use Promises (and async/await) to avoid callback hell and make async code readable, predictable, and maintainable.


### 2. What is Promise ?

- A Promise allows you to handle asynchronous operations in a structured way by attaching success and failure handlers instead of using nested callbacks.
- A Promise in JavaScript is an object that represents the eventual completion or failure of an asynchronous operation and its resulting value.

```js
let promise = new Promise(resolve, reject) {
  // executor function
}

resolve(value) - when promise fullfilled
reject(error) - if an error occured

```
- promise state
  - initially - pending
  - fulfilled
  - rejected

- We can have either resolve or reject
- only first value will be picked up
```js

  let promise = new Promise(function(resolve, reject) {
  resolve("done");

  reject(new Error("…")); // ignored
  setTimeout(() => resolve("…")); // ignored
});

```
- example

```js
let promisewithResolve = new Promise(function(resolve, reject) {
  // calling empty executor 
  resolve('DONE');
}); 

let promisewithRejext = new Promise(function(resolve, reject) {
  // calling empty executor  
  reject('FAILED');
})
```

### 3. Consumer (then/catch)

```js
promisewithResolve.then(function (result) {
  // success
}, function (error) {
  // failure
});

// only success

promisewithResolve.then(function (result) {
  // success
});


// only failure 

promisewithResolve.catch(function (result) {
  // success
});

or // passing null as first argument

promisewithResolve.then(null, function (error) {
  // error
});

```

### 4. Finally

- it is used for cleanup
- it does not return anything. if we return it silenlty ignores the value
- The error in finally() OVERRIDES everything before it

```js

Promise.resolve("DONE")
  .then((res) => console.log(res))
  .finally(() => console.log('CLEAN UP DONE'))

// 

Promise.resolve("DONE")
  .then((res) => console.log(res))
  .finally(() => Promise.resolve("DONE2"))
  .then((res) => console.log(res)); // undefined because finally does not return anything

N.B - If we want to add {} then you should add return statement

```


### 5. Promise Chaining

```js

Promise.resolve("DONE")
  .then(() => {
    return Promise.reject("ERROR");
  })
  .catch((err) => console.log(err));

// 

Promise.resolve("DONE")
.then(() => {
  throw new Error('REJECT')
})
.catch((err) => console.log(err));

```


























