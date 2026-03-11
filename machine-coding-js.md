# JavaScript Machine Coding Practice (Vanilla JS Focus)

This list focuses on **HTML + CSS + Vanilla JavaScript** implementations.
Goal: strengthen **DOM manipulation, events, async JS, performance, and data structures** without relying on frameworks.

---

# 1. Core UI Components

## 1. Star Rating Component

**Requirements**

* Display 5 stars
* Hover should preview rating
* Click should select rating
* Selected rating should remain highlighted

**Concepts Tested**

* DOM events
* Dynamic UI updates
* Event delegation

---

## 2. Modal / Dialog Component

**Requirements**

* Open modal on button click
* Close modal on overlay click
* Close modal using ESC key

**Concepts Tested**

* Event listeners
* Keyboard events
* DOM manipulation

---

## 3. Accordion Component

**Requirements**

* Expand/collapse sections
* Only one section open at a time

**Concepts Tested**

* Event delegation
* State management
* DOM updates

---

## 4. Tooltip / Popover

**Requirements**

* Show tooltip on hover
* Hide when mouse leaves
* Position relative to element

**Concepts Tested**

* CSS positioning
* Mouse events
* DOM updates

---

## 5. Carousel / Image Slider

**Requirements**

* Next / Previous buttons
* Auto-play option
* Infinite loop

**Concepts Tested**

* Timers
* DOM updates
* State tracking

---

## 6. Dropdown Component

**Requirements**

* Open dropdown on click
* Select option
* Close when clicking outside

**Concepts Tested**

* Event bubbling
* Event delegation
* DOM traversal

---

## 7. Progress Bar

**Requirements**

* Start
* Pause
* Reset

**Concepts Tested**

* setInterval
* UI state management

---

## 8. Analog Clock

**Requirements**

* Display hour, minute, second hands
* Update every second

**Concepts Tested**

* Date object
* Timers

---

## 9. Pagination Component

**Requirements**

* Display page numbers
* Next / previous navigation
* Active page highlight

**Concepts Tested**

* State updates
* DOM rendering

---

# 2. Search & Performance Problems

## 10. Debounced Search Bar

**Requirements**

* API request after user stops typing
* Delay using debounce

**Concepts Tested**

* Debounce
* Async API calls
* Event handling

---

## 11. Autocomplete / Typeahead Search

**Requirements**

* Suggestions while typing
* Highlight matching text
* Keyboard navigation

**Concepts Tested**

* Filtering
* Keyboard events
* Dynamic rendering

---

## 12. Infinite Scroll

**Requirements**

* Load more items when reaching bottom
* Avoid duplicate requests

**Concepts Tested**

* Scroll events
* Throttle
* Lazy loading

---

## 13. Image Gallery with API

**Requirements**

* Fetch images from API
* Pagination or infinite scroll
* Search functionality

**Concepts Tested**

* Fetch API
* Async/await
* UI updates

---

## 14. Weather Application

**Requirements**

* Search city
* Fetch weather data
* Show error state

**Concepts Tested**

* API handling
* Error handling
* Async JS

---

# 3. CRUD Applications

## 15. Todo List

**Requirements**

* Add task
* Edit task
* Delete task
* Mark complete

**Concepts Tested**

* CRUD operations
* State management

---

## 16. Todo List with Drag and Drop

**Requirements**

* Reorder tasks

**Concepts Tested**

* Drag and Drop API

---

## 17. Kanban Board

**Requirements**

* Columns: Todo / In Progress / Done
* Move tasks between columns

**Concepts Tested**

* Drag & Drop
* State management

---

## 18. Nested Comment System

**Requirements**

* Reply to comment
* Infinite nested replies
* Collapse thread

**Concepts Tested**

* Recursion
* Tree structures

---

## 19. Poll Widget

**Requirements**

* Vote for option
* Show percentage results

**Concepts Tested**

* Array manipulation
* UI rendering

---

## 20. Quiz Application

**Requirements**

* Multiple questions
* Score calculation
* Timer

**Concepts Tested**

* State tracking
* Conditional rendering

---

## 21. Login Form Validation

**Requirements**

* Email validation
* Password rules
* Error messages

**Concepts Tested**

* Regex
* Form validation
* Event handling

---

# 4. Logic Heavy Applications

## 22. Tic Tac Toe

**Requirements**

* Two players
* Winner detection
* Reset game

**Concepts Tested**

* Game logic
* State management

---

## 23. Calculator

**Requirements**

* Basic operations
* Decimal numbers
* Clear functionality

**Concepts Tested**

* Expression parsing
* Event handling

---

## 24. Countdown Timer

**Requirements**

* Start
* Pause
* Reset

**Concepts Tested**

* setInterval
* Time calculations

---

## 25. File Explorer UI

**Requirements**

* Folder expand/collapse
* Nested folders

**Concepts Tested**

* Tree data structures
* Recursion

---

# 5. JavaScript System Design

## 26. Event Emitter

Implement a custom event system.

**Functions**

* on(event, callback)
* emit(event)
* off(event)

**Concepts Tested**

* Closures
* Event systems

---

# JavaScript Concepts Covered

### Core JavaScript

* closures
* promises
* async/await
* event loop

### Performance

* debounce
* throttle

### DOM Manipulation

* querySelector
* createElement
* appendChild
* removeChild
* classList

### Events

* click
* input
* keyup
* scroll
* submit

### Data Structures

* arrays
* objects
* trees
* recursion

---

# Suggested Practice Order

Start with these first:

1. Star Rating
2. Modal
3. Accordion
4. Todo List
5. Debounced Search
6. Autocomplete
7. Infinite Scroll
8. Nested Comments
9. Event Emitter
10. Tic Tac Toe

These cover **most JavaScript interview patterns for frontend machine coding rounds**.
