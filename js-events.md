
# ✅ JavaScript Events – Machine Coding (What it does & When to use)

---

## ✅ Core Events (Know These)

### `input`
**What it does:** Fires whenever the input value changes  
**When to use:** Capture user typing in real time (search, validation)
```js
input.addEventListener("input", (e) => console.log(e.target.value));
````

---

### `change`

**What it does:** Fires when value is committed (blur or enter)
**When to use:** Dropdowns, checkbox, final value submission

```js
input.addEventListener("change", (e) => console.log(e.target.value));
```

---

### `focus`

**What it does:** Fires when element gains focus
**When to use:** Show hints, highlight input

```js
input.addEventListener("focus", () => console.log("Focused"));
```

---

### `blur`

**What it does:** Fires when element loses focus
**When to use:** Field validation, hide tooltips

```js
input.addEventListener("blur", () => console.log("Blurred"));
```

---

### `keydown`

**What it does:** Fires when key is pressed
**When to use:** Detect Enter, keyboard shortcuts

```js
input.addEventListener("keydown", (e) => console.log(e.key));
```

---

### `keyup`

**What it does:** Fires when key is released
**When to use:** Read final value, avoid repeated firing

```js
input.addEventListener("keyup", (e) => console.log(e.key));
```

---

### `click`

**What it does:** Fires on mouse click
**When to use:** Buttons, checkboxes, toggles

```js
button.addEventListener("click", () => console.log("Clicked"));
```

---

### `submit`

**What it does:** Fires when form is submitted
**When to use:** Handle form submission

```js
form.addEventListener("submit", (e) => {
  e.preventDefault();
  console.log("Submitted");
});
```

---

## ✅ Mouse / Interaction (Common)

### `mousedown`

**What it does:** Fires when mouse button is pressed
**When to use:** Drag start, custom controls

```js
element.addEventListener("mousedown", () => console.log("Mouse down"));
```

---

### `mouseup`

**What it does:** Fires when mouse button is released
**When to use:** Drag end

```js
element.addEventListener("mouseup", () => console.log("Mouse up"));
```

---

### `mousemove`

**What it does:** Fires when mouse moves
**When to use:** Dragging, drawing, sliders

```js
element.addEventListener("mousemove", (e) => console.log(e.clientX));
```

---

## ✅ Form / UI Control

### `reset`

**What it does:** Fires when form is reset
**When to use:** Reset state/UI

```js
form.addEventListener("reset", () => console.log("Reset"));
```

---

### `select`

**What it does:** Fires when text is selected
**When to use:** Track text selection

```js
input.addEventListener("select", () => console.log("Selected"));
```

---

### `paste`

**What it does:** Fires when content is pasted
**When to use:** Validate pasted data

```js
input.addEventListener("paste", () => console.log("Paste"));
```

---

### `copy`

**What it does:** Fires when content is copied
**When to use:** Analytics, restrictions

```js
input.addEventListener("copy", () => console.log("Copy"));
```

---

### `cut`

**What it does:** Fires when content is cut
**When to use:** Data control

```js
input.addEventListener("cut", () => console.log("Cut"));
```

---

## ✅ Window / Document (Often needed)

### `DOMContentLoaded`

**What it does:** Fires when DOM is ready
**When to use:** Initialize JS safely

```js
document.addEventListener("DOMContentLoaded", () => console.log("DOM ready"));
```

---

### `load`

**What it does:** Fires when all resources loaded
**When to use:** After images, fonts load

```js
window.addEventListener("load", () => console.log("Loaded"));
```

---

### `resize`

**What it does:** Fires when window size changes
**When to use:** Responsive logic

```js
window.addEventListener("resize", () => console.log(window.innerWidth));
```

---

### `scroll`

**What it does:** Fires when page scrolls
**When to use:** Infinite scroll, lazy loading

```js
window.addEventListener("scroll", () => console.log(window.scrollY));
```

