### DOM (Document Object Model)
- Represents HTML as a tree of nodes
- Used to read, create, update, delete UI

1. DOM Selection Method

```js
document.getElementById("id")
document.querySelector(".class")
document.querySelector("#id")

// select multiple elements

document.getElementsByClassName("box")
document.getElementsByTagName("div")
document.querySelectorAll(".item")

```
#### Interview note:

- querySelectorAll → NodeList
- getElementsByClassName → HTMLCollection

2. DOM Manipulation Methods

```js
// Change content
element.innerHTML = "<b>Hello</b>" // parses HTML (⚠️ XSS risk) (Never use innerHTML with untrusted data. Use textContent or sanitize first.)
element.textContent = "Hello" // fastest, ignores CSS (recommended)
element.innerText = "Hello" // respects CSS (avoid this one)

// Change attributes
element.getAttribute("href")
element.setAttribute("href", "/home")
element.removeAttribute("disabled")
element.hasAttribute("id")

// Change styles
element.style.color = "red"
element.style.backgroundColor = "black"

// class
element.classList.add("active")
element.classList.remove("active")
element.classList.toggle("active")
```

3. Create / Remove Elements

```js
const div = document.createElement("div");
div.textContent = "Hello";

parent.appendChild(div);
parent.removeChild(div);
parent.append(div);     // modern
parent.prepend(div);
```

4. DOM Traversal

```js
element.parentElement
element.children
element.firstElementChild
element.lastElementChild
element.nextElementSibling
element.previousElementSibling
```
5. DOM Events

```js
element.addEventListener("click", handler);
element.removeEventListener("click", handler);

// Event Object
event.target
event.currentTarget
  - target stays the original source
  - currentTarget is the element handling it
  - Click here 👇
    <button>  ← event.target (child)
    ↑
    <div>     ← event.currentTarget (parent)
event.preventDefault()
event.stopPropagation()
```


### BOM (Browser Object Model)
- Represents the browser environment
- Used to control browser behavior, not UI structure

1. window

```js
window.alert("Hello")
window.confirm("Are you sure?")
window.prompt("Enter name")

window.innerWidth
window.innerHeight
```

2. location

```js
location.href
location.reload()
location.assign("/login")
location.replace("/home")
```

3. history

```js
history.back()
history.forward()
history.go(-1)
```

4. navigator

```js
navigator.userAgent
navigator.language
navigator.onLine
navigator.geolocation
```

5. navigator

```js
navigator.userAgent
navigator.language
navigator.onLine
navigator.geolocation
```

6. screen

```js
screen.width
screen.height
screen.availWidth
```

7. Timer

```js
setTimeout(fn, 1000)
setInterval(fn, 2000)

clearTimeout(id)
clearInterval(id)
```

