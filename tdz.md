### The Temporal Dead Zone is the time between:

- when a variable is created (hoisted), and

- when it is initialized

### description

- During this time, accessing the variable throws a ReferenceError.

- The Temporal Dead Zone (TDZ) applies to let and const only, not to var.

### var → NO TDZ

- hoisted ✅

- initialized to undefined immediately ✅
- So no TDZ.
