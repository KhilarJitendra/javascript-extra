## 🔥 Tier 1 — MUST KNOW (Asked in almost every React interview)

| Priority | Topic (Cleaned & Merged)                          | Why it matters                     |
| -------- | ------------------------------------------------- | ---------------------------------- |
| ⭐⭐⭐⭐⭐    | **How React Works Under the Hood**                | Shows real framework understanding |
| ⭐⭐⭐⭐⭐    | **React Rendering Process (Pre & Post React 18)** | Interviewers *love* this           |
| ⭐⭐⭐⭐⭐    | **Virtual DOM + Reconciliation + Diffing**        | Core React mental model            |
| ⭐⭐⭐⭐⭐    | **React Fiber (Architecture & Purpose)**          | Senior-level signal                |
| ⭐⭐⭐⭐⭐    | **State Management in React**                     | Local, lifted, global, Context     |
| ⭐⭐⭐⭐⭐    | **React Lifecycle (Class → Hooks mapping)**       | Still asked conceptually           |
| ⭐⭐⭐⭐⭐    | **Performance Optimization in React**             | Very common follow-up              |
| ⭐⭐⭐⭐⭐    | **CSR vs SSR (and hydration basics)**             | Product & architecture thinking    |

---

## ⭐⭐⭐⭐ Tier 2 — VERY IMPORTANT (Strong senior signal)

These separate **mid → senior** candidates.

| Priority | Topic                                          | Notes                              |
| -------- | ---------------------------------------------- | ---------------------------------- |
| ⭐⭐⭐⭐     | **Batching & Concurrent Rendering (React 18)** | Tie to Fiber                       |
| ⭐⭐⭐⭐     | **React Events (Synthetic Events)**            | Event delegation knowledge         |
| ⭐⭐⭐⭐     | **Lazy Loading & Code Splitting**              | Performance + UX                   |
| ⭐⭐⭐⭐     | **Routing in React**                           | SPA navigation understanding       |
| ⭐⭐⭐⭐     | **Async Tasks in React**                       | Fetching, effects, race conditions |
| ⭐⭐⭐⭐     | **React Design Patterns**                      | Real-world architecture            |

---

## ⭐⭐⭐ Tier 3 — GOOD TO KNOW (Asked selectively)

Useful, but not deal-breakers.

| Priority | Topic                             | Notes                  |
| -------- | --------------------------------- | ---------------------- |
| ⭐⭐⭐      | **Higher Order Components (HOC)** | Legacy but conceptual  |
| ⭐⭐⭐      | **Styling Approaches in React**   | CSS Modules, CSS-in-JS |
| ⭐⭐⭐      | **Good Practices in React**       | Clean code discussion  |
| ⭐⭐⭐      | **Unit Testing in React**         | Often high-level       |

---

ANSWERSSSSSSSSSSSSSS -------------->

---

## 1. **How React Works Under the Hood**

“Under the hood, React works by creating a lightweight in-memory representation of the UI called the Virtual DOM. When state or props change, 
React creates a new Virtual DOM tree, compares it with the previous one using a diffing algorithm, and calculates the minimum set of changes needed.
These changes are then efficiently applied to the real DOM.
React uses Fiber architecture to break rendering work into units, prioritize updates, and support features like concurrent rendering, making updates smooth and performant.”

“React has a reconciliation algorithm to calculate changes and a commit phase to apply those changes to the real DOM.”

---

## 2. **React Rendering Process (Pre & Post React 18)**

“Before React 18, rendering was synchronous and blocking. 
React 18 introduced concurrent rendering, allowing React to pause, 
prioritize, and resume rendering while keeping DOM commits synchronous.”

“The render phase is when React calculates what the UI should look like by 
calling components and comparing the new output with the previous one, without touching the real DOM.”

During the render phase, React:

- Calls your function components

- Executes:

  - JSX

  - Hooks (useState, useMemo, etc.)

  - Builds a new Virtual DOM / Fiber tree

  - Compares it with the previous tree (reconciliation)

- Figures out what changed

📌 No DOM updates happen here

<img width="872" height="487" alt="Screenshot 2026-01-02 at 7 52 52 PM" src="https://github.com/user-attachments/assets/111ee3d7-f9d3-40d2-9e2b-f6fe11fcf961" />

---

## 3. **Virtual DOM + Reconciliation + Diffing**

“Reconciliation is the process React uses to compare the previous and the new Virtual DOM trees to determine what has changed.”

“Diffing is the algorithm React uses during reconciliation to efficiently compare two Virtual DOM trees and calculate the minimal set of changes.”

---

## 4. **React Fiber (Architecture & Purpose)**

**React Fiber** is React’s internal reconciliation architecture that breaks the component tree into **units of work**, enabling **pause, resume, and priority-based rendering** for better responsiveness.

---

### Fiber Node (per component)
```js
{
  type,
  child,
  sibling,
  return,
  stateNode,
  pendingProps,
  memoizedState,
  flags
}
````

**Fiber nodes**

* Live in **heap memory**
* Form a **linked-list–based tree**
* Replace **recursive call stack traversal**

---

### How Fiber Works (Execution Model)

**Two Trees**

* **Current tree** → what’s on screen
* **Work-in-Progress tree** → what React is building

**Process**

1. Work on **one Fiber at a time**
2. Can **pause** between units
3. **Resume** later
4. **Commit** once ready

| Phase  | Behavior                       |
| ------ | ------------------------------ |
| Render | Incremental, interruptible     |
| Commit | Synchronous, non-interruptible |

➡️ Fiber enables **concurrent rendering**, but **DOM updates stay synchronous**.

---

### Purpose of React Fiber (Interview Gold)

Fiber exists to:

* Enable **concurrent rendering**
* **Prioritize** user interactions
* Avoid **UI blocking**
* Support **Suspense**
* Enable **Transitions** (`startTransition`)
* Improve **perceived performance**

---

### Memory & Execution

* Fiber nodes → **heap**
* Virtual DOM trees → **heap**
* Diffing & reconciliation → **call stack execution**

---

### Are There Multiple Algorithms in React?

| Responsibility     | Algorithm                |
| ------------------ | ------------------------ |
| What changed?      | Reconciliation (Diffing) |
| When to work?      | Fiber Scheduler          |
| How to update DOM? | Commit Phase             |

---

### Before React 18 (Stack Reconciler) that is React 16

* Rendering was **synchronous**
* Large updates → **UI freeze**
* **No interruption**

Flow:

```
State change
→ Re-render subtree
→ Block main thread
→ Commit DOM
```

---

### One-Line Definition

**React Fiber enables interruptible, priority-based rendering by breaking rendering into small units, improving responsiveness and performance.**

** Also check - https://medium.com/@jitendrakhilar609/understanding-react-fiber-explained-simply-85e67a1f882b **

---

---

## 5. **State Management in React** 
  - All type states
    - Local state (Component level)
    - Derived State (const firstName = fname + lname)
    - Global (Shared) state (use context APi or Redux)
      - theme
      - auth user
      - language
    - Server State (reeact query or tenstack query)
      - comes from API
  - How state update in react
    - “When setState is called, React does not update the state immediately.
       It schedules an update using the Fiber scheduler, batches multiple updates, and triggers a re-render.”
    - State updates are asynchronous
    - React batches updates
  - When to use Redux (Please read - https://medium.com/@jitendrakhilar609/redux-essentials-interview-topics-for-developers-b19188b4848a)
    - complex, frequently changing global state
    - Eg - Authentication and user session , product cart information (quantity, price etc)
  - When to use Contetxt API
    - global, low-frequency data across the component tree
    - Eg - Theme (light / dark), Auth user info, Language / locale, Feature flags, App-level configuration

---

## 6. **React Lifecycle (Class → Hooks mapping)**

| Phase   | Method                   |
| ------- | ------------------------ |
| Mount   | constructor              |
|         | render                   |
|         | componentDidMount        |
| Update  | shouldComponentUpdate    |
|         | render                   |
|         | componentDidUpdate       |
| Unmount | componentWillUnmount     |
| Error   | componentDidCatch        |
|         | getDerivedStateFromError |


| Class                 | Hook                           |
| --------------------- | ------------------------------ |
| componentDidMount     | `useEffect(() => {}, [])`      |
| componentDidUpdate    | `useEffect(() => {}, [deps])`  |
| componentWillUnmount  | `useEffect(() => cleanup, [])` |
| shouldComponentUpdate | `React.memo`                   |

---


---

## 6. **Performance Optimization in React**

  - Part 1 - https://www.youtube.com/watch?v=G8Mk6lsSOcw 
  - Part 2 - https://www.youtube.com/watch?v=HJFDXKkz67M






