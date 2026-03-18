## ✅ A. UI Consistency (Biggest Win)

### Before:
- 5 different button styles across apps

### After:
- Single `<Button />` component used everywhere

👉 **If design changes:**
- Update once → reflected everywhere

💬 **Interview Line:**
> “We enforced a design system through shared components, which ensured UI consistency across all applications.”

---

## ✅ B. Reusable Custom Hooks (Logic Standardization)

### You created hooks like:
- `useCart()`
- `useAuth()`
- `useApi()`

### Before:
- Each team handled API & state differently

### After:
- Same logic everywhere → predictable behavior

👉 **Example:**
```js
const { addToCart } = useCart();
````

💬 **Interview Line:**

> “Custom hooks helped us standardize business logic like cart and authentication across multiple apps.”

---

## ✅ C. Developer Velocity 🚀

### Before:

* Build from scratch every time

### After:

* Just import and use

👉 **Example:**

```js
import { ProductCard } from '@repo/ui-components';
```

### Result:

* Faster feature delivery
* Less debugging
* Better onboarding

💬 **Interview Line:**

> “Developers could ship features faster by leveraging pre-built components and hooks instead of rebuilding from scratch.”

---

## ✅ D. Centralized Dependency Management

### Before:

* Different React versions in different repos 😅

### After:

* Single source of truth

👉 **Result:**

* No version conflicts
* Easier upgrades
