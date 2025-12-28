### What is Critical Reneding Path ?
---
- Critical Rendering Path is the sequence of steps a browser follows to convert HTML, CSS, and JavaScript into pixels on the screen.
- In simple words: 👉 How your code becomes a visible webpage


### Why it matters ?

- Affects First Paint (FP)
- Affects First Contentful Paint (FCP)
- Affects page load speed
- Core Web Vitals depend on it

👉 Faster CRP = Faster page

### There are 6 Steps to crtical rendering path -  

1️⃣ HTML → DOM
- Browser downloads HTML
- Parses it into DOM tree

```js
<h1>Hello</h1>
<p>World</p>

becomes
Document
 └─ html
    └─ body
       ├─ h1
       └─ p
```

2️⃣ CSS → CSSOM
- Browser downloads CSS
- Parses it into CSSOM tree
```js
CSS is render-blocking
Browser waits until CSS is ready
```

3️⃣ DOM + CSSOM → Render Tree
- Combines DOM + CSSOM
- Removes:
  - display: none
  - Invisible nodes
- 👉 Render Tree = what will actually be painted

4️⃣ Layout (Reflow)
- Calculates:
  - width
  - height
  - position
- “Where does each element go?”

5️⃣ Paint
- Draws pixels:
  - colors
  - text
  - borders
  - images

🎨 “How does it look?”

6️⃣ Composite
- Layers combined
- GPU optimizations
- Final screen output

🖥️ “Show it on screen”



### How to Optimize Critical Rendering Path ?

1️⃣ Reduce render-blocking resources

- Use defer / async
- Split JS bundles

2️⃣ Minimize CSS

- Remove unused CSS
- Inline critical CSS

3️⃣ Reduce DOM size

- Fewer nodes = faster DOM
- Avoid deeply nested HTML

4️⃣ Avoid layout thrashing

```js
// BAD
el.style.width = "100px";
console.log(el.offsetHeight);
el.style.height = "200px";
```

5️⃣ Use modern CSS properties

- Prefer transform, opacity
- Avoid frequent top, left
