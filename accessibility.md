Here is a **simple Accessibility (a11y) cheat sheet** you can revise quickly before interviews. I also added a **rating/importance level** so you know what interviewers usually focus on.

---

# Accessibility (a11y) Cheat Sheet

## 1️⃣ Use Semantic HTML ⭐⭐⭐⭐⭐ (Very Important)

Use meaningful tags instead of `div`.

Example:

```html
<header>
<nav></nav>
<main></main>
<section></section>
<article></article>
<footer></footer>
```

Why?

* Screen readers understand page structure
* Improves SEO
* Better navigation

---

## 2️⃣ Image Alt Text ⭐⭐⭐⭐⭐

Every image should have `alt`.

```html
<img src="product.jpg" alt="Red running shoes">
```

Decorative images:

```html
<img src="design.png" alt="">
```

---

## 3️⃣ Label for Form Inputs ⭐⭐⭐⭐⭐

Bad:

```html
<input type="text">
```

Good:

```html
<label for="name">Name</label>
<input id="name" type="text">
```

Screen readers read the label.

---

## 4️⃣ Keyboard Accessibility ⭐⭐⭐⭐⭐

Users must navigate with **keyboard (Tab key)**.

Bad:

```html
<div onclick="submit()">Submit</div>
```

Good:

```html
<button>Submit</button>
```

Use **interactive elements** like:

* `button`
* `a`
* `input`

---

## 5️⃣ ARIA Attributes ⭐⭐⭐⭐

Used when semantic HTML is not enough.

Example:

```html
<button aria-label="Close menu">X</button>
```

Common ARIA:

| Attribute       | Purpose                 |
| --------------- | ----------------------- |
| `aria-label`    | Screen reader label     |
| `aria-hidden`   | Hide from screen reader |
| `aria-expanded` | Dropdown state          |
| `role`          | Defines element role    |

---

## 6️⃣ Color Contrast ⭐⭐⭐⭐

Text should be readable.

Example:

Good:

```text
Black text on white background
```

Bad:

```text
Light gray on white
```

WCAG minimum ratio:

```text
4.5:1
```

---

## 7️⃣ Focus State ⭐⭐⭐⭐

Users should see where keyboard focus is.

Example:

```css
button:focus {
  outline: 2px solid blue;
}
```

Never remove outline completely.

Bad:

```css
outline: none;
```

---

## 8️⃣ Heading Structure ⭐⭐⭐⭐

Use proper order:

```html
<h1>Main Title</h1>
<h2>Section</h2>
<h3>Subsection</h3>
```

Do not skip levels.

Bad:

```html
<h1>
<h4>
```

---

## 9️⃣ Accessible Links ⭐⭐⭐⭐

Bad:

```html
<a href="#">Click here</a>
```

Good:

```html
<a href="/products">View products</a>
```

---

## 🔟 Accessible Buttons ⭐⭐⭐⭐

Buttons should describe action.

Bad:

```html
<button>+</button>
```

Good:

```html
<button aria-label="Add item">+</button>
```

---

# Accessibility Tools ⭐⭐⭐

Developers test accessibility using:

* Lighthouse
* axe DevTools
* WAVE

---

# Quick Accessibility Checklist

Before production check:

✅ Semantic HTML
✅ Alt text for images
✅ Labels for forms
✅ Keyboard navigation
✅ Focus state visible
✅ Good color contrast
✅ ARIA only when needed

