### What is Function Currying ?

- Currying is a process in Functional programming in which we can transform a function with multiple argument into a sequence of nesting functions.
- Currying is an advanced technique of working with functions. It’s used not only in JavaScript but in other languages as well.

### Benefit 

- reusability
- Better separation of concerns
- Improves composability

### Example 

- https://www.youtube.com/watch?v=VK36OsyPeUw

```js
Developer 1 → responsible for TO

Developer 2 → responsible for SUBJECT

Developer 3 → responsible for BODY

Each developer contributes one piece, and the final email is assembled later.

That is exactly what currying enables.

function sendAutoEmail(to) {
   // return closure basically 
  return function (subject) {
     return function (body) {
          return `Hi ${to}, subject is ${subject} and body is ${body}`
      }
  }
}

or in arrow function

const sendAutoEmail = (to) => (subject) => (body) => {
  return `Hi ${to}, subject is ${subject} and body is ${body}`;
};

or

const sendAutoEmail = (to) => (subject) => (body) => 
  return `Hi ${to}, subject is ${subject} and body is ${body}`;
;


// use

let step1 = sendAutoEmail("test@gmail.com");
let step2 = step1("New testing email");
step2("My email body is");

This works because of closures, not magic.

```
