## Levels of Caching

Caching in frontend happens at multiple levels: 
browser storage, H
TTP caching, and application-level caching. 
As a senior frontend developer, I focus on choosing the right layer based on data sensitivity, freshness, and performance.

---

### 1. Client-Side Storage Caching (Browser Storage)

#### a) LocalStorage

**Used for**

* Theme (dark/light)
* Language
* Feature flags

---

#### b) SessionStorage

**Used for**

* Multi-step forms
* Temporary UI state

---

#### c) Cookies

**What it is**

* Small data sent to the server on every request

**Used for**

* Authentication
* Session tracking

**Key points**

* Set by the **server**
* Sent automatically with HTTP requests

---

### 2. HTTP Caching (Browser + Network Level)

**Handled via HTTP response headers such as**

* `Cache-Control`
* `ETag`
* `Expires`

**Used for**

* Static assets (JS, CSS, images)
* API responses (with validation)

---

### 3. Application-Level Caching

#### a) Service Worker Caching

**Used for**

* Offline support
* Faster repeat visits
* Custom caching strategies

---

#### b) App Shell Caching

**Used for**

* Caching core UI (HTML, CSS, JS)
* Loading data separately via APIs

---

### 4. Resource Loading Optimization

#### a) Preload (Urgent)

* Used for critical resources needed immediately (JS, fonts)

#### b) Prefetch (Future)

* Used for resources likely needed soon (next page, route-based chunks)


User
 ↓
Browser Cache
 ↓
Service Worker
 ↓
Akamai CDN
 ↓
Next.js Server
 ↓
Backend APIs


---
