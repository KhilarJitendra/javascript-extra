## What is Generator Function ?

- A generator function is a special type of JavaScript function that allows you to pause execution and resume it later, instead of running completely in one go.
- It is defined using function* and produces values one at a time using the yield keyword.

- Instead, it:

  - pauses its execution

  - returns values one by one

  - resumes from where it stopped
 
```js

function* myGenerator() {
  yield "Hello";
  yield "World";
}

const gen = myGenerator();
👉 The function does NOT run immediately
Instead, it returns a generator object (which is an iterator).

```

## Why do we need Generator Functions?

In many real-world scenarios, we do not want all data at once.

Examples:

- Paginated API responses

- Infinite scrolling lists

- Streaming data

- Large datasets

- On-demand computation

Generator functions allow us to produce values lazily, only when required.

This results in:

- Better performance

- Lower memory usage

- More control over execution


## What happens if generators did not exist?

Without generators:

- We would need complex manual iterators

- More boilerplate code

- Harder state management

- Higher memory consumption

```js

function createIterator(arr) {
  let index = 0;
  return {
    next() {
      if (index < arr.length) {
        return { value: arr[index++], done: false };
      }
      return { done: true };
    }
  };
}

```

## What is an Iterator? 

An object is an iterator if it has a next() method and that method returns an object of this shape:

- If a value has Symbol.iterator, it is iterable and works with for...of.
- Like array, string, generator function 

```js

{ value: any, done: boolean }

```

## What is the relationship between Generator Functions and Iterators? 

Step 1: What problem existed before generators?

To create an iterator without generators, you had to do this:

```js
function createIterator(arr) {
  let index = 0;

  return {
    next() {
      if (index < arr.length) {
        return { value: arr[index++], done: false };
      }
      return { done: true };
    }
  };
}

```
Step 2: Generator Functions solve this problem

Generator functions were introduced to simplify iterator creation.

Instead of manually writing next() and tracking state, you write:

```js

function* numbers() {
  yield 1;
  yield 2;
  yield 3;
}

```


## What is the yield keyword?

What is the yield keyword?

yield is a special keyword used only inside generator functions.

It:

- produces a value

- pauses the function execution

- remembers the function’s state

- resumes from the same place when called again


Also we have yield*

```js
function* gen() {
  yield [1, 2, 3];
}

// g.next(); // value = [1, 2, 3]

```




