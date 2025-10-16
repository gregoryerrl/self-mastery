# Advanced JavaScript Self-Mastery Workbook

---

## Table of Contents

- [💻 Prerequisites](#prerequisites)
- [How to Use This Workbook](#how-to-use-this-workbook)
- [🌱 Philosophy Behind This Workbook](#philosophy-behind-this-workbook)

### 🟢 PART 1: CLOSURES & FUNCTIONAL PATTERNS

- [Section 1: Closures Deep Dive](#section-1-closures-deep-dive)
- [Section 2: Higher-Order Functions & Composition](#section-2-higher-order-functions--composition)

### 🟡 PART 2: EXECUTION CONTEXT & BINDING

- [Section 3: Understanding `this` in All Contexts](#section-3-understanding-this-in-all-contexts)
- [Section 4: Execution Context & Scope Chains](#section-4-execution-context--scope-chains)

### 🔵 PART 3: PROTOTYPES & OBJECT SYSTEMS

- [Section 5: Prototype Chains & Inheritance](#section-5-prototype-chains--inheritance)
- [Section 6: Classes & Modern OOP](#section-6-classes--modern-oop)

### 🟣 PART 4: ASYNC MASTERY

- [Section 7: Promise Internals & Patterns](#section-7-promise-internals--patterns)
- [Section 8: Advanced Async Control Flow](#section-8-advanced-async-control-flow)

### 🟠 PART 5: EVENT LOOP & SCHEDULING

- [Section 9: Event Loop Deep Dive](#section-9-event-loop-deep-dive)
- [Section 10: Task Scheduling & Timing APIs](#section-10-task-scheduling--timing-apis)

### 🔴 PART 6: METAPROGRAMMING WITH PROXIES

- [Section 11: Proxies & Reflect API](#section-11-proxies--reflect-api)
- [Section 12: Advanced Metaprogramming](#section-12-advanced-metaprogramming)

### ⚫ PART 7: ITERATORS, GENERATORS & LAZY EVALUATION

- [Section 13: Iterators & Custom Iteration](#section-13-iterators--custom-iteration)
- [Section 14: Generators & Async Generators](#section-14-generators--async-generators)

### 🟤 PART 8: MEMORY, PERFORMANCE & DEBUGGING

- [Section 15: Memory Management & Leak Prevention](#section-15-memory-management--leak-prevention)
- [Section 16: Performance Profiling & Optimization](#section-16-performance-profiling--optimization)

### 🔷 PART 9: ARCHITECTURAL PATTERNS

- [Section 17: Design Patterns in JavaScript](#section-17-design-patterns-in-javascript)
- [Section 18: Module Systems & Code Organization](#section-18-module-systems--code-organization)

---

## 💻 Prerequisites

Before starting this workbook, you **must have completed**:

### ✅ Required Workbook

**"HTML-CSS-JavaScript Self-Mastery Workbook"** - You should be comfortable with:

- All JavaScript fundamentals (variables, functions, objects, arrays)
- DOM manipulation and event handling
- Basic async/await and Promises
- ES6+ syntax (arrow functions, destructuring, spread)
- Array methods (map, filter, reduce)
- Basic closures and scope

### ✅ What You Should Already Know

You should be able to:

- Build interactive web applications from scratch
- Debug using browser DevTools and console.log
- Use callbacks, promises, and async/await
- Work with objects and arrays fluently
- Understand basic scope and closures
- Read and understand others' JavaScript code

### ⚠️ This is NOT for Beginners

If you're not comfortable with:

- Writing functions without looking up syntax
- Using array methods like map/filter/reduce
- Basic Promise usage
- Object and array manipulation

**Stop here.** Complete the basic JavaScript workbook first.

---

## How to Use This Workbook

This workbook teaches you JavaScript **deeply** - not just "how to use it" but **how it works internally and why it behaves the way it does**.

### The Goal

After completing this workbook, you'll be able to:

✅ **Master any JavaScript framework** (prepared for "Framework Foundations" workbook)  
✅ **Build complex applications with vanilla JavaScript** (no framework needed)  
✅ **Read and understand framework source code**  
✅ **Debug complex JavaScript issues**  
✅ **Make informed architectural decisions**  
✅ **Contribute to open source JavaScript projects**

### The Structure

Each section follows this pattern:

#### 1. **The Problem / Real Scenario**

Why does this concept matter? You'll see a real situation where this knowledge is critical - whether you're using frameworks OR pure vanilla JavaScript.

#### 2. **Explorable Questions**

Questions designed to make you **think, research, and discover** - not memorize definitions.

**Good questions look like:**

- ✅ "You're building a module system. How would you create private variables that only the module can access but users can't modify directly?"
- ✅ "Your app has a memory leak. The Chrome profiler shows event listeners aren't being cleaned up. What's happening and how do you fix it?"
- ✅ "You pass an async function to `setTimeout`. What's the execution order, and why doesn't it work as expected?"

**Bad questions look like:**

- ❌ "What is a closure?" (too vague, just memorization)
- ❌ "What does IIFE stand for?" (trivia, not understanding)
- ❌ "List the 13 Proxy traps" (memorization, not useful)

#### 3. **Build It**

Every section has hands-on exercises where you **build something real**. You'll struggle, research, debug, and discover the answers naturally.

#### 4. **Reflect**

After building, you'll reflect:

- How does this connect to frameworks? (preparation for Framework Foundations)
- How does this help with vanilla JavaScript? (for projects without frameworks)
- What patterns did you discover?

### How to Approach Each Section

1. **Read "The Problem"** - Understand why this matters
2. **Try answering questions yourself first** - before Googling
3. **Research using all tools** - Google, ChatGPT, MDN, Stack Overflow
4. **Build the exercises** - Don't skip these, they're where real learning happens
5. **Compare your solution** - Look at how libraries/frameworks solve it
6. **Teach it back** - Explain to someone or write notes in your own words

---

## 🌱 Philosophy Behind This Workbook

This workbook prepares you for **TWO possible paths:**

### Path 1: Framework Foundations → Framework Mastery

After this workbook, you'll complete "JavaScript Framework Foundations" and then master React, Vue, Svelte, or any framework. This workbook ensures you understand the JavaScript concepts that frameworks rely on.

### Path 2: Pure Vanilla JavaScript Mastery

After this workbook, you can build complex applications with vanilla JavaScript alone - no framework needed. You'll understand JavaScript deeply enough to build your own abstractions.

### Core Beliefs

- **Deep understanding > Surface knowledge** - You'll learn WHY JavaScript behaves the way it does
- **Discovery > Memorization** - Questions guide you to discover, not just recall facts
- **Building > Reading** - You'll build everything from scratch before using libraries
- **Practical > Theoretical** - Every concept ties to real problems you'll face
- **Tool-agnostic** - Use ChatGPT, Google, Stack Overflow - whatever helps you learn

By the time you complete this workbook, you won't just "know JavaScript" - you'll **understand it so deeply that complex patterns become obvious, debugging becomes intuitive, and framework internals make perfect sense**.

---

# 🟢 PART 1: CLOSURES & FUNCTIONAL PATTERNS

---

## Section 1: Closures Deep Dive

### The Problem

You're building a counter module. Users should be able to increment, decrement, and check the count, but they should **never** be able to directly access or modify the count variable. How do you create this "private" variable?

```javascript
const counter = createCounter();
counter.increment(); // works
counter.getCount(); // works
counter.count; // should be undefined - not accessible!
```

This is the exact problem frameworks face: encapsulation and data privacy.

---

### Exploration Questions

**Try to answer these BEFORE researching. Then verify your understanding.**

#### Understanding Closures

**Scenario 1: The Button Bug**

```javascript
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 100);
}
// Logs: 3, 3, 3 (not 0, 1, 2) - Why?
```

**Explore:**

- What value does `i` have when the timeouts execute?
- Why do all three timeouts see the same value?
- How does closure capture variables?
- How would you fix this with closures?
- What if you used `let` instead of `var`? Why does that fix it?

**Scenario 2: The Memory Mystery**

```javascript
function createHugeArray() {
  const huge = new Array(1000000).fill("data");
  return function () {
    return huge[0];
  };
}

const getter = createHugeArray();
// Is the huge array still in memory? Why?
```

**Explore:**

- Does the closure keep the entire array in memory?
- When does the array get garbage collected?
- How can closures cause memory leaks?
- How would you fix potential memory issues here?

#### Closures in Practice

**Scenario 3: Event Handler Hell**

```javascript
class TodoList {
  constructor() {
    this.todos = [];
    this.setupEventListeners();
  }

  setupEventListeners() {
    document.querySelector("#add").addEventListener("click", function () {
      this.addTodo(); // ERROR - `this` is wrong!
    });
  }

  addTodo() {
    this.todos.push({text: "New todo"});
  }
}
```

**Explore:**

- Why is `this` wrong inside the event listener?
- How would you fix this with closures?
- How would you fix this with arrow functions?
- What's the difference between the two fixes?
- Which approach uses less memory?

**Scenario 4: The Module Pattern**

You see this pattern in old JavaScript libraries:

```javascript
const library = (function () {
  let privateVar = 0;

  return {
    publicMethod() {
      return privateVar;
    },
  };
})();
```

**Explore:**

- Why is the function immediately invoked?
- How does this create private variables?
- Can you access `privateVar` from outside? Why not?
- How is this different from using ES6 modules?
- When would you still use this pattern?

---

### Master Exercise: Build a Module System

**Goal:** Create a system where modules have private state that's truly inaccessible from outside.

#### Part 1: Private Counter Module

Build a counter with private state:

```javascript
function createCounter(initialValue = 0) {
  // Your implementation here
  // Users should NOT be able to access the count directly
}

const counter = createCounter(10);
console.log(counter.increment()); // 11
console.log(counter.increment()); // 12
console.log(counter.decrement()); // 11
console.log(counter.getCount()); // 11
console.log(counter.reset()); // 0

// This should NOT work:
console.log(counter.count); // undefined
```

**Requirements:**

- Private `count` variable
- Public methods: `increment()`, `decrement()`, `getCount()`, `reset()`
- Each instance has independent state
- Truly private - no way to access count directly

**Test your understanding:**

- Can you access `count` from outside? (should be no)
- Can you have multiple independent counters?
- What happens to `count` in memory when you're done with the counter?

#### Part 2: Todo Manager with Private State

Build a todo manager with complex private state:

```javascript
function createTodoManager() {
  // Your implementation here
}

const todos = createTodoManager();
todos.add("Buy milk");
todos.add("Walk dog");
console.log(todos.getAll()); // [{ id: 1, text: 'Buy milk', done: false }, ...]
todos.toggle(1); // Marks todo 1 as done
todos.delete(1); // Removes todo 1
console.log(todos.getStats()); // { total: 1, completed: 0, pending: 1 }
```

**Requirements:**

- Private array of todos
- Private `nextId` counter
- Private helper functions (like `findById`)
- Public methods: `add`, `toggle`, `delete`, `getAll`, `getStats`
- Return copies of data (prevent external mutation)
- Each instance is independent

**Challenge questions:**

- How do you prevent users from mutating the todos array?
- How do you ensure `nextId` always increments?
- Can you add private helper functions that public methods use?

#### Part 3: Bank Account with Validation

Build a bank account where balance is truly private and protected:

```javascript
function createBankAccount(initialBalance, accountHolder) {
  // Your implementation here
}

const account = createBankAccount(1000, "Alice");
console.log(account.deposit(500)); // 1500
console.log(account.withdraw(200)); // 1300
console.log(account.withdraw(2000)); // Error: Insufficient funds
console.log(account.getBalance()); // 1300
console.log(account.getHistory()); // Array of all transactions

// Should NOT work:
account.balance = 999999; // Has no effect - balance is private
```

**Requirements:**

- Private `balance` variable
- Private `transactions` array
- Prevent negative balances
- Track all deposits and withdrawals
- Validate all operations
- Return balance safely

**Advanced:**

- Add interest calculation (private method)
- Add transaction types (deposit, withdrawal, interest)
- Add date/time to each transaction
- Add account freeze/unfreeze functionality

---

### Reflection Questions

After completing the exercises:

1. **For Framework Foundations:**

   - How might React hooks use closures to store component state?
   - How might a state management library use closures for private state?
   - Why would a framework want to hide internal implementation details?

2. **For Vanilla JavaScript:**

   - When should you use closures for private state vs. classes with private fields (`#field`)?
   - How can closures help organize large vanilla JavaScript applications?
   - What are the memory implications of heavy closure usage?

3. **Deeper Understanding:**
   - When are closures created?
   - How long do closures persist in memory?
   - Can you visualize the scope chain in your exercises?

---

## Section 2: Higher-Order Functions & Composition

### The Problem

You're building a data processing pipeline. You need to:

1. Fetch user data
2. Filter out inactive users
3. Transform data shape
4. Sort by registration date
5. Take first 10 results

How do you build this **without writing a massive function** full of nested loops?

```javascript
// This is hard to read and maintain:
function processUsers(users) {
  const result = [];
  for (let i = 0; i < users.length; i++) {
    if (users[i].active) {
      const transformed = {id: users[i].id, name: users[i].fullName};
      result.push(transformed);
    }
  }
  result.sort((a, b) => a.registeredAt - b.registeredAt);
  return result.slice(0, 10);
}

// How can we make this declarative and composable?
```

---

### Exploration Questions

#### Higher-Order Functions

**Scenario 1: Build Your Own `map`**

You can't use `Array.prototype.map`. Build it from scratch:

```javascript
function myMap(array, callback) {
  // Your implementation here
}

const numbers = [1, 2, 3, 4];
const doubled = myMap(numbers, (n) => n * 2);
console.log(doubled); // [2, 4, 6, 8]
```

**Explore:**

- How does `map` work internally?
- What does the callback receive (value, index, array)?
- How do you handle edge cases (empty array, non-array)?
- Why is `map` better than a `for` loop?
- When might a `for` loop be better than `map`?

**Scenario 2: Build `filter` and `reduce`**

Build these from scratch:

```javascript
function myFilter(array, predicate) {
  // Your implementation
}

function myReduce(array, reducer, initialValue) {
  // Your implementation
}
```

**Explore:**

- How does `filter` decide what to keep?
- How does `reduce` accumulate values?
- What happens if `reduce` has no initial value?
- How are these three (map, filter, reduce) related?

#### Function Composition

**Scenario 3: The Pipeline Problem**

You need to process data through multiple steps:

```javascript
const data = "  hello world  ";

// Ugly nested calls:
const result = capitalize(trim(toLowerCase(data)));

// How can we make this readable?
// Desired: pipe(data, trim, toLowerCase, capitalize)
```

**Explore:**

- What is function composition?
- How do you implement `pipe` (left-to-right)?
- How do you implement `compose` (right-to-left)?
- Which is more readable?
- How does this relate to Unix pipes?

**Scenario 4: Currying Mystery**

```javascript
function add(a, b, c) {
  return a + b + c;
}

// You want to call it like this:
add(1)(2)(3); // 6
add(1, 2)(3); // 6
add(1)(2, 3); // 6

// How do you transform `add` to support this?
```

**Explore:**

- What is currying?
- How does currying differ from partial application?
- How do you implement `curry` for any function?
- Why would you want to curry functions?
- What are practical uses for currying?

#### Practical Applications

**Scenario 5: Debounce Deep Dive**

```javascript
// User types in search box - you don't want to search on every keystroke
searchInput.addEventListener("input", (e) => {
  searchAPI(e.target.value); // Too many API calls!
});

// You need debounce, but how does it work internally?
```

**Explore:**

- How does debounce delay function execution?
- What happens if the function is called repeatedly?
- How do you implement debounce from scratch?
- What's the difference between debounce and throttle?
- When should you use each?

**Scenario 6: Memoization**

```javascript
function fibonacci(n) {
  if (n <= 1) return n;
  return fibonacci(n - 1) + fibonacci(n - 2);
}

fibonacci(40); // Takes forever! Why?
// How can you make this fast with memoization?
```

**Explore:**

- Why is this recursive fibonacci so slow?
- What is memoization?
- How do you implement memoization?
- What are the memory trade-offs?
- When should you NOT use memoization?

---

### Master Exercise: Build a Functional Utility Library

#### Part 1: Core Higher-Order Functions

Implement these from scratch:

```javascript
// Implement all of these without using built-in array methods
function map(array, fn) {
  /* ... */
}
function filter(array, predicate) {
  /* ... */
}
function reduce(array, reducer, initial) {
  /* ... */
}
function find(array, predicate) {
  /* ... */
}
function some(array, predicate) {
  /* ... */
}
function every(array, predicate) {
  /* ... */
}
```

**Test them:**

```javascript
const numbers = [1, 2, 3, 4, 5];
console.log(map(numbers, (n) => n * 2)); // [2, 4, 6, 8, 10]
console.log(filter(numbers, (n) => n > 2)); // [3, 4, 5]
console.log(reduce(numbers, (a, b) => a + b, 0)); // 15
```

#### Part 2: Function Composition Tools

Build `pipe` and `compose`:

```javascript
function pipe(...fns) {
  // Takes functions left to right
  // pipe(f, g, h)(x) === h(g(f(x)))
}

function compose(...fns) {
  // Takes functions right to left
  // compose(f, g, h)(x) === f(g(h(x)))
}

// Test:
const add1 = (n) => n + 1;
const double = (n) => n * 2;
const square = (n) => n * n;

const pipeline = pipe(add1, double, square);
console.log(pipeline(2)); // (2 + 1) * 2 = 6, then 6^2 = 36
```

#### Part 3: Implement Curry

Build a curry function that works with any function:

```javascript
function curry(fn) {
  // Your implementation
}

// Test:
function add(a, b, c) {
  return a + b + c;
}

const curriedAdd = curry(add);
console.log(curriedAdd(1)(2)(3)); // 6
console.log(curriedAdd(1, 2)(3)); // 6
console.log(curriedAdd(1)(2, 3)); // 6
console.log(curriedAdd(1, 2, 3)); // 6
```

**Challenge:** Make curry work with any number of arguments.

#### Part 4: Build Debounce and Throttle

```javascript
function debounce(fn, delay) {
  // Wait `delay` ms after last call before executing
}

function throttle(fn, interval) {
  // Execute at most once per `interval` ms
}

// Test debounce:
const debouncedLog = debounce((text) => console.log(text), 500);
debouncedLog("a"); // Not logged yet
debouncedLog("b"); // Not logged yet
debouncedLog("c"); // After 500ms: logs 'c'

// Test throttle:
const throttledLog = throttle((text) => console.log(text), 1000);
throttledLog("1"); // Logs immediately
throttledLog("2"); // Ignored (within 1000ms)
setTimeout(() => throttledLog("3"), 1500); // Logs after 1500ms total
```

#### Part 5: Implement Memoization

```javascript
function memoize(fn) {
  // Cache results based on arguments
}

// Test:
const slowFib = (n) => (n <= 1 ? n : slowFib(n - 1) + slowFib(n - 2));
const fastFib = memoize(slowFib);

console.time("slow");
slowFib(35); // Very slow
console.timeEnd("slow");

console.time("fast");
fastFib(35); // Much faster
console.timeEnd("fast");
```

**Challenge:** Handle multiple arguments, not just one.

#### Part 6: Build a Data Processing Pipeline

Use everything you built:

```javascript
const users = [
  {id: 1, name: "Alice", age: 25, active: true, score: 85},
  {id: 2, name: "Bob", age: 30, active: false, score: 92},
  {id: 3, name: "Charlie", age: 35, active: true, score: 78},
  {id: 4, name: "David", age: 28, active: true, score: 95},
];

// Build a pipeline using your functions:
// 1. Filter active users
// 2. Map to { name, score }
// 3. Sort by score (descending)
// 4. Take first 2

const processUsers = pipe(
  (users) => filter(users, (u) => u.active),
  (users) => map(users, (u) => ({name: u.name, score: u.score})),
  (users) => users.sort((a, b) => b.score - a.score),
  (users) => users.slice(0, 2)
);

console.log(processUsers(users));
// [{ name: 'David', score: 95 }, { name: 'Alice', score: 85 }]
```

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks use higher-order functions for hooks (`useState`, `useEffect`)?
   - How might a framework implement `computed` values using function composition?
   - How do frameworks use memoization to prevent re-renders?

2. **For Vanilla JavaScript:**

   - When should you use functional patterns vs. imperative loops?
   - How can function composition make code more testable?
   - What are the performance trade-offs of functional style?

3. **Deeper Understanding:**
   - What is "point-free" style, and when is it useful?
   - How does currying enable better function reuse?
   - What are pure functions, and why do they matter?

---

# 🟡 PART 2: EXECUTION CONTEXT & BINDING

---

## Section 3: Understanding `this` in All Contexts

### The Problem

```javascript
const user = {
  name: "Alice",
  greet() {
    console.log(`Hello, ${this.name}`);
  },
};

user.greet(); // "Hello, Alice" - works!

const greetFn = user.greet;
greetFn(); // "Hello, undefined" - broken! Why?

setTimeout(user.greet, 1000); // "Hello, undefined" - also broken!
```

**The `this` keyword is confusing but critical.** You need to master it to:

- Build class-based components (frameworks)
- Handle event listeners correctly (vanilla JS)
- Understand how methods work
- Debug `this`-related bugs

---

### Exploration Questions

#### The 4 Binding Rules

**Scenario 1: Default Binding**

```javascript
function sayName() {
  console.log(this.name);
}

var name = "Global";
sayName(); // What is `this`? What gets logged?
```

**Explore:**

- What is `this` in a regular function call?
- What happens in strict mode vs non-strict mode?
- Why is this called "default" binding?

**Scenario 2: Implicit Binding**

```javascript
const obj = {
  name: "Object",
  sayName() {
    console.log(this.name);
  },
};

obj.sayName(); // What is `this`? Why?
```

**Explore:**

- What is `this` when a method is called on an object?
- What if you have nested objects? (`obj.nested.method()`)
- Can you predict `this` by looking at the call site?

**Scenario 3: Explicit Binding**

```javascript
function greet(greeting) {
  console.log(`${greeting}, ${this.name}`);
}

const person = {name: "Alice"};

greet.call(person, "Hello"); // What happens?
greet.apply(person, ["Hi"]); // What's different?
const boundGreet = greet.bind(person);
boundGreet("Hey"); // What is `this` now?
```

**Explore:**

- How does `call` differ from `apply`?
- How does `bind` differ from `call`/`apply`?
- Can you bind `this` multiple times? What happens?

**Scenario 4: `new` Binding**

```javascript
function User(name) {
  this.name = name;
  this.greet = function () {
    console.log(`Hello, ${this.name}`);
  };
}

const alice = new User("Alice");
alice.greet(); // What is `this`?
```

**Explore:**

- What does the `new` keyword do (step by step)?
- What is `this` inside a constructor function?
- What happens if you forget `new`?

#### Arrow Functions & Lexical `this`

**Scenario 5: Arrow Function Confusion**

```javascript
const obj = {
  name: "Object",
  regular: function () {
    console.log(this.name);
  },
  arrow: () => {
    console.log(this.name);
  },
};

obj.regular(); // ???
obj.arrow(); // ???
```

**Explore:**

- What is `this` in the arrow function?
- Why doesn't implicit binding work for arrow functions?
- When should you use arrow functions vs regular functions?

**Scenario 6: Event Listeners**

```javascript
class Button {
  constructor(label) {
    this.label = label;
    this.clicks = 0;
  }

  handleClick() {
    this.clicks++;
    console.log(`${this.label} clicked ${this.clicks} times`);
  }
}

const button = new Button("Submit");
document.querySelector("#btn").addEventListener("click", button.handleClick);
// Clicking the button: "undefined clicked NaN times" - Why broken?
```

**Explore:**

- Why is `this` wrong inside the event handler?
- How do you fix this with `bind`?
- How do you fix this with arrow functions?
- Which solution is better? Why?

#### Common Pitfalls

**Scenario 7: Method Assignment**

```javascript
const obj = {
  value: 42,
  getValue() {
    return this.value;
  },
};

const getValue = obj.getValue;
console.log(getValue()); // undefined - Why?

// How do you fix this?
```

**Scenario 8: Array Methods**

```javascript
const obj = {
  numbers: [1, 2, 3],
  multiplier: 2,

  multiplyAll() {
    return this.numbers.map(function (n) {
      return n * this.multiplier; // `this.multiplier` is undefined - Why?
    });
  },
};
```

**Explore:**

- Why is `this` wrong inside the `map` callback?
- How do you fix this with arrow functions?
- How do you fix this with the `thisArg` parameter?
- Which solution is clearer?

---

### Master Exercise: Mastering `this`

#### Part 1: Predict `this` Values

For each scenario, predict what `this` is BEFORE running:

```javascript
// Scenario 1
function foo() {
  console.log(this);
}
foo(); // ???

// Scenario 2
const obj = {
  method: foo,
};
obj.method(); // ???

// Scenario 3
foo.call({name: "Explicit"}); // ???

// Scenario 4
new foo(); // ???

// Scenario 5
const arrowFoo = () => console.log(this);
arrowFoo(); // ???
obj.method = arrowFoo;
obj.method(); // ???

// Scenario 6
setTimeout(obj.method, 1000); // ???

// Scenario 7
class MyClass {
  method() {
    console.log(this);
  }
}
const instance = new MyClass();
instance.method(); // ???
const extracted = instance.method;
extracted(); // ???
```

**For each:**

1. Predict `this` before running
2. Run and verify
3. Explain WHY `this` is that value
4. Draw the execution context

#### Part 2: Build `call`, `apply`, and `bind`

Implement these methods from scratch:

```javascript
Function.prototype.myCall = function (context, ...args) {
  // Your implementation
};

Function.prototype.myApply = function (context, argsArray) {
  // Your implementation
};

Function.prototype.myBind = function (context, ...fixedArgs) {
  // Your implementation
  // Should return a new function
};

// Test:
function greet(greeting, punctuation) {
  return `${greeting}, ${this.name}${punctuation}`;
}

const person = {name: "Alice"};

console.log(greet.myCall(person, "Hello", "!")); // "Hello, Alice!"
console.log(greet.myApply(person, ["Hi", "."])); // "Hi, Alice."

const boundGreet = greet.myBind(person, "Hey");
console.log(boundGreet("?")); // "Hey, Alice?"
```

#### Part 3: Fix Real-World `this` Problems

Fix all the `this` bugs in this code:

```javascript
class TodoList {
  constructor() {
    this.todos = [];
    this.init();
  }

  init() {
    // BUG 1: Event listener
    document.querySelector("#add-btn").addEventListener("click", this.addTodo);

    // BUG 2: forEach callback
    const initialTodos = ["Buy milk", "Walk dog"];
    initialTodos.forEach(function (text) {
      this.todos.push({text, done: false}); // `this` is undefined
    });

    // BUG 3: setTimeout
    setTimeout(function () {
      this.render(); // `this` is undefined
    }, 100);
  }

  addTodo() {
    const input = document.querySelector("#todo-input");
    this.todos.push({text: input.value, done: false}); // `this` is undefined
    this.render();
  }

  render() {
    console.log("Rendering:", this.todos);
  }
}

const app = new TodoList();
```

**Fix it 3 different ways:**

1. Using `bind`
2. Using arrow functions
3. Using a variable (`const self = this`)

**Which fix is best for each bug? Why?**

#### Part 4: Build a Method Chaining System

Create a calculator that chains methods:

```javascript
const calc = createCalculator(10);
calc.add(5).multiply(2).subtract(3).divide(3).getResult(); // ???

// Hint: Each method must return `this`
```

**Requirements:**

- `createCalculator(initial)` returns calculator object
- Methods: `add`, `subtract`, `multiply`, `divide`
- `getResult()` returns final value
- All methods except `getResult` return `this` for chaining
- Handle division by zero

**Challenge:** Add `undo()` method that reverts last operation.

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks handle `this` in event handlers?
   - Why do React class components need to bind methods?
   - How do arrow functions simplify component code?

2. **For Vanilla JavaScript:**

   - When should you use arrow functions vs regular functions?
   - How do you debug `this` issues in production?
   - What patterns help avoid `this` confusion?

3. **Deeper Understanding:**
   - What is the order of precedence for `this` binding rules?
   - Can you create a decision tree for determining `this`?
   - How does strict mode affect `this`?

---

## Section 4: Execution Context & Scope Chains

### The Problem

```javascript
var globalVar = "global";

function outer() {
  var outerVar = "outer";

  function inner() {
    var innerVar = "inner";
    console.log(innerVar); // 'inner' ✅
    console.log(outerVar); // 'outer' ✅ - How can inner() access this?
    console.log(globalVar); // 'global' ✅ - How can inner() access this?
  }

  inner();
}

outer();
```

**How does JavaScript "remember" variables from outer scopes?** Understanding execution contexts and scope chains is critical for:

- Understanding closures deeply
- Debugging scope issues
- Understanding how frameworks manage component state
- Writing efficient code

---

### Exploration Questions

#### Execution Context Fundamentals

**Scenario 1: What Happens When You Call a Function?**

```javascript
var x = 10;

function foo() {
  var y = 20;
  console.log(x + y);
}

foo();
```

**Explore:**

- What is the "Global Execution Context"?
- What is created when `foo()` is called?
- What are the phases of execution context creation?
- What is stored in the execution context?
- What is the "scope chain"?

**Scenario 2: Visualize the Call Stack**

```javascript
function first() {
  console.log("First");
  second();
  console.log("First again");
}

function second() {
  console.log("Second");
  third();
  console.log("Second again");
}

function third() {
  console.log("Third");
}

first();
```

**Explore:**

- Draw the call stack at each step
- When does `second` get added to the stack?
- When does it get removed?
- What happens if a function throws an error?
- What is a stack overflow?

#### Scope Chain Deep Dive

**Scenario 3: How Scope Chain Lookup Works**

```javascript
var a = 1;

function outer() {
  var b = 2;

  function middle() {
    var c = 3;

    function inner() {
      var d = 4;
      console.log(a + b + c + d); // 10
    }

    inner();
  }

  middle();
}

outer();
```

**Explore:**

- How does `inner()` find variable `a`?
- What is the scope chain for `inner()`?
- Draw the scope chain diagram
- What happens if `inner()` tries to access a variable that doesn't exist?
- What is the performance cost of deep scope chains?

**Scenario 4: Lexical vs Dynamic Scope**

```javascript
var value = "global";

function outer() {
  var value = "outer";
  inner();
}

function inner() {
  console.log(value); // What gets logged?
}

outer();
```

**Explore:**

- What is lexical scope?
- Where is `inner` defined?
- Does it matter where `inner` is called?
- What would happen with dynamic scope? (JavaScript doesn't have this)

#### Hoisting Deep Dive

**Scenario 5: Variable Hoisting**

```javascript
console.log(x); // ???
var x = 5;
console.log(x); // ???
```

**Explore:**

- What is hoisting?
- What gets logged first?
- What happens during the creation phase?
- How is this different from:

```javascript
console.log(y); // ???
let y = 5;
```

**Scenario 6: Function Hoisting**

```javascript
foo(); // Can you call foo before it's defined?

function foo() {
  console.log("Function declaration");
}

bar(); // What about bar?

var bar = function () {
  console.log("Function expression");
};
```

**Explore:**

- What's the difference between function declarations and expressions?
- Which are hoisted?
- What gets hoisted: the function or just the variable?

#### Temporal Dead Zone (TDZ)

**Scenario 7: The `let` and `const` TDZ**

```javascript
console.log(x); // ReferenceError
let x = 5;
```

**Explore:**

- What is the Temporal Dead Zone?
- Why does `let` throw an error but `var` doesn't?
- What's the purpose of TDZ?
- How is `const` different from `let`?

---

### Master Exercise: Execution Context Mastery

#### Part 1: Manual Execution Context Tracking

For this code, manually track every execution context:

```javascript
var global = "I am global";

function outer() {
  var outerVar = "I am outer";

  function inner() {
    var innerVar = "I am inner";
    console.log(global + outerVar + innerVar);
  }

  inner();
}

outer();
```

**Create a table:**

| Step | Call Stack               | Scope Chain    | Variables                               |
| ---- | ------------------------ | -------------- | --------------------------------------- |
| 1    | Global Execution Context | Global         | global: 'I am global', outer: function  |
| 2    | Global → outer()         | outer → Global | outerVar: 'I am outer', inner: function |
| 3    | ...                      | ...            | ...                                     |

Continue for every step until completion.

#### Part 2: Predict Execution Order

Predict the execution order of this code:

```javascript
var x = 1;

function a() {
  var x = 10;
  b();
}

function b() {
  var x = 100;
  console.log(x);
}

a();
console.log(x);
```

**Questions:**

1. What gets logged first?
2. What gets logged second?
3. Draw the scope chain for function `b`
4. Can `b()` access the `x` from `a()`? Why or why not?

#### Part 3: Fix Hoisting Bugs

Fix all the hoisting-related bugs:

```javascript
// Bug 1
console.log(greeting); // Should log "Hello"
greeting = "Hello";

// Bug 2
doSomething(); // Should work
var doSomething = function () {
  console.log("Doing something");
};

// Bug 3
if (true) {
  function test() {
    console.log("Test");
  }
}
test(); // Should work reliably

// Bug 4
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 100);
}
// Should log: 0, 1, 2 (not 3, 3, 3)
```

#### Part 4: Build a Scope Chain Visualizer

Build a function that shows the scope chain:

```javascript
function visualizeScope() {
  // Your implementation
  // Should show all variables accessible at this point
  // Should show where each variable comes from
}

var global = "Global Var";

function outer() {
  var outerVar = "Outer Var";

  function inner() {
    var innerVar = "Inner Var";
    visualizeScope();
    // Output:
    // Scope Chain:
    // 1. inner() scope: innerVar = 'Inner Var'
    // 2. outer() scope: outerVar = 'Outer Var'
    // 3. global scope: global = 'Global Var'
  }

  inner();
}

outer();
```

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks use scope chains for component state?
   - How might a framework implement nested components using scope?
   - How do hooks rely on execution context?

2. **For Vanilla JavaScript:**

   - How can understanding execution context help you debug?
   - When should you use `let`/`const` vs `var`?
   - How do you avoid scope-related bugs?

3. **Deeper Understanding:**
   - What is the performance cost of deep scope chains?
   - How does garbage collection interact with scope?
   - Can you draw the complete execution context for any function?

---

# 🔵 PART 3: PROTOTYPES & OBJECT SYSTEMS

---

## Section 5: Prototype Chains & Inheritance

### The Problem

```javascript
const animal = {
  eat() {
    console.log("Eating...");
  },
};

const dog = {
  bark() {
    console.log("Woof!");
  },
};

// How do you make dog inherit from animal?
// So dog can both bark() AND eat()?
```

**JavaScript doesn't have traditional classes** (despite the `class` keyword). Everything is objects and prototypes. Understanding prototypes is critical for:

- Understanding how `class` actually works
- Understanding how frameworks implement inheritance
- Understanding JavaScript's object model
- Reading framework source code

---

### Exploration Questions

#### Prototype Basics

**Scenario 1: The Prototype Chain**

```javascript
const obj = {a: 1};
console.log(obj.toString()); // Where does toString come from?
console.log(obj.hasOwnProperty("a")); // Where does hasOwnProperty come from?
```

**Explore:**

- What is `obj.__proto__`?
- What is the prototype chain?
- How does JavaScript find methods?
- What is at the end of every prototype chain?
- What is `Object.prototype`?

**Scenario 2: Constructor Functions**

```javascript
function Person(name) {
  this.name = name;
}

const alice = new Person("Alice");
console.log(alice.name); // 'Alice'
```

**Explore:**

- What is a constructor function?
- What does `new` do (step by step)?
- What is `Person.prototype`?
- What is `alice.__proto__`?
- How are they related?

**Scenario 3: Adding Methods to Prototypes**

```javascript
function Person(name) {
  this.name = name;
  this.greet = function () {
    // This is inefficient - why?
    console.log(`Hi, I'm ${this.name}`);
  };
}

// vs

function Person(name) {
  this.name = name;
}

Person.prototype.greet = function () {
  // This is better - why?
  console.log(`Hi, I'm ${this.name}`);
};
```

**Explore:**

- What's the difference between these two approaches?
- Where is the method stored in each case?
- What are the memory implications?
- Which is more performant? Why?

#### Inheritance Patterns

**Scenario 4: Prototypal Inheritance**

```javascript
function Animal(name) {
  this.name = name;
}

Animal.prototype.eat = function () {
  console.log(`${this.name} is eating`);
};

function Dog(name, breed) {
  Animal.call(this, name); // What does this line do?
  this.breed = breed;
}

Dog.prototype = Object.create(Animal.prototype); // What does this do?
Dog.prototype.constructor = Dog; // Why is this needed?

Dog.prototype.bark = function () {
  console.log(`${this.name} says Woof!`);
};

const dog = new Dog("Buddy", "Golden Retriever");
dog.eat(); // Works! How?
dog.bark(); // Works!
```

**Explore:**

- Why do we need `Animal.call(this, name)`?
- What does `Object.create(Animal.prototype)` do?
- Why not just `Dog.prototype = Animal.prototype`?
- Why do we need to reset `constructor`?
- Draw the complete prototype chain

**Scenario 5: Property Lookup**

```javascript
function Animal() {}
Animal.prototype.species = "Unknown";

function Dog() {}
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.species = "Canine";

const dog = new Dog();
dog.breed = "Golden Retriever";

console.log(dog.breed); // ???
console.log(dog.species); // ???
console.log(dog.kingdom); // ???
```

**Explore:**

- How does JavaScript find `dog.breed`?
- How does JavaScript find `dog.species`?
- What happens when JavaScript looks for `dog.kingdom`?
- Draw the prototype chain and show where each property lives

#### Object.create and Modern Patterns

**Scenario 6: Object.create Deep Dive**

```javascript
const animal = {
  eat() {
    console.log("Eating...");
  },
};

const dog = Object.create(animal);
dog.bark = function () {
  console.log("Woof!");
};

dog.eat(); // How does this work?
dog.bark(); // How does this work?
```

**Explore:**

- What does `Object.create()` do exactly?
- How is this different from `new` and constructor functions?
- What is the prototype of `dog`?
- When should you use `Object.create` vs constructors?

**Scenario 7: Checking Properties**

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function () {
  console.log(`Hello, I'm ${this.name}`);
};

const alice = new Person("Alice");

console.log("name" in alice); // ???
console.log("greet" in alice); // ???
console.log(alice.hasOwnProperty("name")); // ???
console.log(alice.hasOwnProperty("greet")); // ???
```

**Explore:**

- What's the difference between `in` operator and `hasOwnProperty`?
- How do you check if a property exists on the object itself vs prototype?
- What is `Object.getOwnPropertyNames()`?
- What is `Object.keys()` vs `Object.getOwnPropertyNames()`?

---

### Master Exercise: Build an Inheritance System

#### Part 1: Implement `Object.create`

Build your own version of `Object.create`:

```javascript
function myObjectCreate(proto) {
  // Your implementation
  // Should return a new object with proto as its prototype
}

// Test:
const animal = {
  eat() {
    console.log("Eating...");
  },
};

const dog = myObjectCreate(animal);
dog.bark = function () {
  console.log("Woof!");
};

dog.eat(); // Should work
dog.bark(); // Should work
console.log(Object.getPrototypeOf(dog) === animal); // Should be true
```

#### Part 2: Build a Complete Inheritance Chain

Create a vehicle hierarchy:

```javascript
// Base: Vehicle
function Vehicle(make, year) {
  this.make = make;
  this.year = year;
}

Vehicle.prototype.start = function () {
  console.log(`${this.make} is starting`);
};

Vehicle.prototype.getInfo = function () {
  return `${this.year} ${this.make}`;
};

// Child 1: Car extends Vehicle
function Car(make, year, doors) {
  // Call parent constructor
  // Add doors property
}

// Set up inheritance
// Add Car-specific methods

Car.prototype.honk = function () {
  console.log("Beep beep!");
};

// Child 2: Motorcycle extends Vehicle
function Motorcycle(make, year, type) {
  // Call parent constructor
  // Add type property
}

// Set up inheritance
// Add Motorcycle-specific methods

Motorcycle.prototype.wheelie = function () {
  console.log("Doing a wheelie!");
};

// Grandchild: ElectricCar extends Car
function ElectricCar(make, year, doors, batteryCapacity) {
  // Call parent constructor
  // Add batteryCapacity property
}

// Set up inheritance
// Override start method
// Add ElectricCar-specific methods

ElectricCar.prototype.start = function () {
  console.log(`${this.make} is starting silently...`);
};

ElectricCar.prototype.charge = function () {
  console.log("Charging battery...");
};

// Test:
const car = new Car("Toyota", 2020, 4);
car.start(); // "Toyota is starting"
car.honk(); // "Beep beep!"
console.log(car.getInfo()); // "2020 Toyota"

const bike = new Motorcycle("Harley", 2019, "Cruiser");
bike.start(); // "Harley is starting"
bike.wheelie(); // "Doing a wheelie!"

const tesla = new ElectricCar("Tesla", 2023, 4, 100);
tesla.start(); // "Tesla is starting silently..."
tesla.honk(); // "Beep beep!" (inherited from Car)
tesla.charge(); // "Charging battery..."

// Verify prototype chain:
console.log(tesla instanceof ElectricCar); // true
console.log(tesla instanceof Car); // true
console.log(tesla instanceof Vehicle); // true
console.log(tesla instanceof Motorcycle); // false
```

**Requirements:**

- Proper prototype chain setup
- Call parent constructors correctly
- Reset constructor properties
- Method overriding (ElectricCar.start)
- All inheritance working correctly

#### Part 3: Implement `instanceof`

Build your own `instanceof` operator:

```javascript
function myInstanceOf(obj, Constructor) {
  // Your implementation
  // Walk up the prototype chain
  // Check if Constructor.prototype is in the chain
}

// Test:
function Animal() {}
function Dog() {}
Dog.prototype = Object.create(Animal.prototype);

const dog = new Dog();

console.log(myInstanceOf(dog, Dog)); // true
console.log(myInstanceOf(dog, Animal)); // true
console.log(myInstanceOf(dog, Object)); // true
console.log(myInstanceOf(dog, Array)); // false
```

#### Part 4: Prototype Debugging Challenge

Fix all the prototype issues in this code:

```javascript
function Animal(name) {
  this.name = name;
}

Animal.prototype.eat = function () {
  console.log(`${this.name} is eating`);
};

function Dog(name, breed) {
  this.name = name; // BUG: Not calling parent constructor properly
  this.breed = breed;
}

Dog.prototype = Animal.prototype; // BUG: This is wrong - why?

Dog.prototype.bark = function () {
  console.log("Woof!");
};

const dog = new Dog("Buddy", "Golden");
const cat = new Animal("Whiskers");

dog.bark(); // Works
cat.bark(); // Shouldn't work but it does! Why?

console.log(dog.constructor === Dog); // false - Why?
console.log(dog.constructor === Animal); // true - Why?
```

**Fix all bugs and explain:**

1. Why shouldn't `Dog.prototype = Animal.prototype`?
2. Why did `cat.bark()` work when it shouldn't?
3. Why is `dog.constructor === Animal`?
4. How do you fix all of these issues?

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks use prototypes internally?
   - Why do some frameworks avoid class-based inheritance?
   - How does understanding prototypes help you read framework source code?

2. **For Vanilla JavaScript:**

   - When should you use prototypal inheritance vs composition?
   - What are the performance implications of deep prototype chains?
   - How do modern classes relate to prototypes?

3. **Deeper Understanding:**
   - Can you draw the complete prototype chain for any object?
   - What is the difference between `__proto__` and `prototype`?
   - Why does JavaScript have both?

---

## Section 6: Classes & Modern OOP

### The Problem

ES6 introduced `class` syntax, but it's just "syntactic sugar" over prototypes:

```javascript
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log(`Hi, I'm ${this.name}`);
  }
}

// This is just a nicer way to write:
function Person(name) {
  this.name = name;
}
Person.prototype.greet = function () {
  console.log(`Hi, I'm ${this.name}`);
};
```

**Understanding what classes really are** helps you:

- Use classes effectively in frameworks (React class components)
- Understand how class-based frameworks work
- Know when to use classes vs other patterns
- Understand modern JavaScript features (private fields, static methods)

---

### Exploration Questions

#### Class Fundamentals

**Scenario 1: What Are Classes Really?**

```javascript
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log(`Hi, I'm ${this.name}`);
  }
}

console.log(typeof Person); // ???
console.log(Person.prototype.greet); // ???
const alice = new Person("Alice");
console.log(alice.__proto__ === Person.prototype); // ???
```

**Explore:**

- What is a class in JavaScript? (What does it compile to?)
- Where do methods live?
- How does `new` work with classes?
- How is this different from function constructors?

**Scenario 2: Class Inheritance**

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  eat() {
    console.log(`${this.name} is eating`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name); // What does super do?
    this.breed = breed;
  }

  bark() {
    console.log("Woof!");
  }
}

const dog = new Dog("Buddy", "Golden");
dog.eat(); // Works! How?
dog.bark(); // Works!
```

**Explore:**

- What does `extends` do?
- What does `super()` do?
- Why must you call `super()` before using `this`?
- What happens if you forget `super()`?
- How does the prototype chain look?

#### Advanced Class Features

**Scenario 3: Static Methods and Properties**

```javascript
class MathHelper {
  static PI = 3.14159;

  static add(a, b) {
    return a + b;
  }

  static square(n) {
    return n * n;
  }
}

console.log(MathHelper.add(2, 3)); // 5
console.log(MathHelper.PI); // 3.14159

const helper = new MathHelper();
console.log(helper.add(2, 3)); // ???
```

**Explore:**

- What are static methods?
- How do you call static methods?
- Can instances call static methods?
- Where do static methods live in memory?
- When should you use static methods?

**Scenario 4: Private Fields**

```javascript
class BankAccount {
  #balance = 0; // Private field

  deposit(amount) {
    this.#balance += amount;
  }

  getBalance() {
    return this.#balance;
  }
}

const account = new BankAccount();
account.deposit(100);
console.log(account.getBalance()); // 100
console.log(account.#balance); // SyntaxError - Why?
```

**Explore:**

- What are private fields (`#`)?
- How are they different from naming conventions (`_balance`)?
- Can you access private fields from outside the class?
- Can you access them from subclasses?
- How are private fields implemented?

**Scenario 5: Getters and Setters**

```javascript
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }

  get area() {
    return this.width * this.height;
  }

  set area(value) {
    // Can you set the area? How?
  }
}

const rect = new Rectangle(5, 10);
console.log(rect.area); // 50 (looks like a property, not a method!)
rect.area = 100; // How can we make this set width/height?
```

**Explore:**

- What are getters and setters?
- When should you use them vs regular methods?
- How do they improve encapsulation?
- What's the syntax for calling them?

#### Method Types

**Scenario 6: Instance Methods vs Static Methods**

```javascript
class Counter {
  static totalInstances = 0;

  constructor() {
    this.count = 0;
    Counter.totalInstances++;
  }

  increment() {
    this.count++;
  }

  static getTotalInstances() {
    return Counter.totalInstances;
  }
}

const c1 = new Counter();
const c2 = new Counter();

c1.increment();
c2.increment();
c2.increment();

console.log(c1.count); // ???
console.log(c2.count); // ???
console.log(Counter.getTotalInstances()); // ???
```

**Explore:**

- What's the difference between instance and static methods?
- When should you use each?
- Can static methods access instance properties?
- Can instance methods access static properties?

---

### Master Exercise: Build Real-World Classes

#### Part 1: Geometry Class Hierarchy

Build a complete shape system with classes:

```javascript
// Base class
class Shape {
  constructor(color) {
    this.color = color;
  }

  // Abstract method (should be overridden)
  area() {
    throw new Error("area() must be implemented by subclass");
  }

  perimeter() {
    throw new Error("perimeter() must be implemented by subclass");
  }

  describe() {
    return `A ${this.color} ${this.constructor.name} with area ${this.area()}`;
  }
}

// Rectangle class
class Rectangle extends Shape {
  // Implement constructor, area, perimeter
}

// Circle class
class Circle extends Shape {
  // Implement constructor, area, perimeter
}

// Triangle class
class Triangle extends Shape {
  // Implement constructor, area, perimeter
}

// Static utility methods
class ShapeUtils {
  static compareAreas(shape1, shape2) {
    // Compare and return which is bigger
  }

  static totalArea(shapes) {
    // Sum area of array of shapes
  }
}

// Test:
const rect = new Rectangle("red", 5, 10);
const circle = new Circle("blue", 7);
const triangle = new Triangle("green", 3, 4, 5);

console.log(rect.area()); // 50
console.log(circle.area()); // ~153.94
console.log(triangle.area()); // 6

console.log(rect.describe()); // "A red Rectangle with area 50"

console.log(ShapeUtils.compareAreas(rect, circle));
// "Circle is larger (153.94 vs 50)"

console.log(ShapeUtils.totalArea([rect, circle, triangle]));
// ~209.94
```

#### Part 2: Bank Account System with Private Fields

Build a banking system with proper encapsulation:

```javascript
class BankAccount {
  // Private fields
  #balance = 0;
  #transactions = [];
  #accountNumber;

  constructor(accountNumber, initialBalance = 0) {
    this.#accountNumber = accountNumber;
    this.#balance = initialBalance;
    this.#addTransaction("Initial Deposit", initialBalance);
  }

  // Private methods
  #addTransaction(type, amount) {
    // Add transaction to history with timestamp
  }

  #validateAmount(amount) {
    // Ensure amount is positive number
  }

  // Public methods
  deposit(amount) {
    // Validate and add to balance
    // Record transaction
  }

  withdraw(amount) {
    // Validate, check sufficient funds
    // Deduct from balance
    // Record transaction
  }

  // Getters
  get balance() {
    return this.#balance;
  }

  get transactions() {
    // Return copy of transactions (prevent mutation)
  }

  get accountInfo() {
    return {
      accountNumber: this.#accountNumber,
      balance: this.#balance,
      transactionCount: this.#transactions.length,
    };
  }
}

class SavingsAccount extends BankAccount {
  #interestRate;

  constructor(accountNumber, initialBalance, interestRate) {
    super(accountNumber, initialBalance);
    this.#interestRate = interestRate;
  }

  applyInterest() {
    // Calculate and add interest to balance
  }
}

// Test:
const account = new BankAccount("ACC001", 1000);
account.deposit(500);
account.withdraw(200);
console.log(account.balance); // 1300
console.log(account.transactions); // Array of 3 transactions

// account.#balance = 999999; // SyntaxError - private!

const savings = new SavingsAccount("SAV001", 5000, 0.05);
savings.applyInterest();
console.log(savings.balance); // 5250
```

**Requirements:**

- True private fields (not accessible outside class)
- Private methods for internal use only
- Proper validation
- Transaction history
- Prevent negative balances
- Inheritance working correctly

#### Part 3: React-like Component System

Build a component system using classes (similar to React class components):

```javascript
class Component {
  constructor(props) {
    this.props = props;
    this.state = {};
  }

  setState(newState) {
    this.state = {...this.state, ...newState};
    this.render();
  }

  render() {
    throw new Error("render() must be implemented");
  }
}

class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = {count: props.initialCount || 0};
  }

  increment = () => {
    this.setState({count: this.state.count + 1});
  };

  decrement = () => {
    this.setState({count: this.state.count - 1});
  };

  render() {
    console.log(`Count: ${this.state.count}`);
  }
}

class TodoList extends Component {
  constructor(props) {
    super(props);
    this.state = {todos: []};
  }

  addTodo = (text) => {
    const newTodo = {id: Date.now(), text, done: false};
    this.setState({todos: [...this.state.todos, newTodo]});
  };

  toggleTodo = (id) => {
    const todos = this.state.todos.map((todo) =>
      todo.id === id ? {...todo, done: !todo.done} : todo
    );
    this.setState({todos});
  };

  render() {
    console.log("Todos:", this.state.todos);
  }
}

// Test:
const counter = new Counter({initialCount: 10});
counter.increment(); // Count: 11
counter.increment(); // Count: 12
counter.decrement(); // Count: 11

const todos = new TodoList({});
todos.addTodo("Buy milk");
todos.addTodo("Walk dog");
todos.toggleTodo(todos.state.todos[0].id);
todos.render(); // Shows updated todos
```

**Challenge:** Add lifecycle methods:

- `componentDidMount()` - Called after first render
- `componentDidUpdate()` - Called after setState
- `componentWillUnmount()` - Called before destroy

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do React class components use these patterns?
   - Why did React introduce hooks to replace class components?
   - When should you use classes in modern frameworks?

2. **For Vanilla JavaScript:**

   - When should you use classes vs factory functions?
   - What are the benefits and drawbacks of classes?
   - How do private fields improve code security?

3. **Deeper Understanding:**
   - What is the memory footprint of class instances?
   - How do classes relate to prototypes under the hood?
   - What are the performance implications of getters/setters?

---

# 🟣 PART 4: ASYNC MASTERY

---

## Section 7: Promise Internals & Patterns

### The Problem

```javascript
// This callback hell is hard to read and maintain:
getData(function (data) {
  processData(data, function (processed) {
    saveData(processed, function (result) {
      notifyUser(result, function () {
        console.log("Done!");
      });
    });
  });
});

// Promises make this cleaner:
getData()
  .then(processData)
  .then(saveData)
  .then(notifyUser)
  .then(() => console.log("Done!"));

// But how do Promises work internally?
```

**Understanding Promises deeply** is critical for:

- Handling async operations in frameworks (data fetching, effects)
- Understanding async/await (it's just Promise syntax)
- Debugging async issues
- Building reliable async code

---

### Exploration Questions

#### Promise Fundamentals

**Scenario 1: Promise States**

```javascript
const promise1 = new Promise((resolve) => {
  setTimeout(() => resolve("Success"), 1000);
});

const promise2 = new Promise((resolve, reject) => {
  setTimeout(() => reject("Error"), 1000);
});

const promise3 = new Promise(() => {
  // Never resolves or rejects
});
```

**Explore:**

- What are the three states of a Promise?
- Once a Promise is resolved, can it change state?
- What happens if you call `resolve()` multiple times?
- What happens to a Promise that never resolves?
- How do you check a Promise's state?

**Scenario 2: Promise Chaining**

```javascript
Promise.resolve(1)
  .then((x) => x + 1)
  .then((x) => x * 2)
  .then((x) => console.log(x)); // What gets logged?

// What if one returns a Promise?
Promise.resolve(1)
  .then((x) => {
    return new Promise((resolve) => {
      setTimeout(() => resolve(x + 1), 1000);
    });
  })
  .then((x) => console.log(x)); // What happens?
```

**Explore:**

- How does Promise chaining work?
- What does `.then()` return?
- What happens if you return a value from `.then()`?
- What happens if you return a Promise from `.then()`?
- How does the Promise "unwrap" nested Promises?

**Scenario 3: Error Handling**

```javascript
Promise.resolve(1)
  .then((x) => {
    throw new Error("Oops!");
  })
  .then((x) => {
    console.log("This runs?");
  })
  .catch((err) => {
    console.log("Caught:", err.message);
  })
  .then(() => {
    console.log("This runs?");
  });
```

**Explore:**

- Where do errors go in a Promise chain?
- Does `.catch()` stop the chain or continue it?
- What does `.catch()` return?
- Can you recover from errors in a Promise chain?
- What happens to unhandled Promise rejections?

**Scenario 4: Finally**

```javascript
Promise.resolve(1)
  .then((x) => x + 1)
  .catch((err) => console.error(err))
  .finally(() => {
    console.log("Cleanup!");
  });
```

**Explore:**

- When does `.finally()` run?
- Does it run if the Promise rejects?
- Can `.finally()` change the Promise value?
- What does `.finally()` return?
- When should you use `.finally()`?

#### Async/Await

**Scenario 5: What Is Async/Await?**

```javascript
async function fetchUser() {
  const response = await fetch("/api/user");
  const data = await response.json();
  return data;
}

// This is syntactic sugar for:
function fetchUser() {
  return fetch("/api/user")
    .then((response) => response.json())
    .then((data) => data);
}
```

**Explore:**

- What does `async` do to a function?
- What does `await` do?
- What does an `async` function return?
- Can you use `await` outside an `async` function?
- How does `async/await` relate to Promises?

**Scenario 6: Error Handling with Async/Await**

```javascript
async function riskyOperation() {
  try {
    const result = await dangerousAsync();
    return result;
  } catch (error) {
    console.error("Caught:", error);
  }
}

// vs

function riskyOperation() {
  return dangerousAsync()
    .then((result) => result)
    .catch((error) => console.error("Caught:", error));
}
```

**Explore:**

- How do you handle errors with `async/await`?
- What happens if you don't use try/catch?
- Which is better: try/catch or `.catch()`?
- Can you use both?

#### Promise Combinators

**Scenario 7: Promise.all**

```javascript
const promise1 = fetch("/api/users");
const promise2 = fetch("/api/posts");
const promise3 = fetch("/api/comments");

Promise.all([promise1, promise2, promise3]).then(([users, posts, comments]) => {
  console.log("All loaded!");
});
```

**Explore:**

- What does `Promise.all()` do?
- When does it resolve?
- What happens if one Promise rejects?
- Does it wait for all Promises if one fails?
- When should you use `Promise.all()`?

**Scenario 8: Other Combinators**

```javascript
// Promise.race
Promise.race([slowPromise, fastPromise]).then((result) =>
  console.log("First:", result)
);

// Promise.allSettled
Promise.allSettled([promise1, promise2, promise3]).then((results) => {
  results.forEach((result) => {
    if (result.status === "fulfilled") {
      console.log("Success:", result.value);
    } else {
      console.log("Failed:", result.reason);
    }
  });
});

// Promise.any
Promise.any([promise1, promise2, promise3])
  .then((result) => console.log("First success:", result))
  .catch(() => console.log("All failed"));
```

**Explore:**

- What does `Promise.race()` do?
- What does `Promise.allSettled()` do?
- What does `Promise.any()` do?
- When should you use each?
- What's the difference between `Promise.all()` and `Promise.allSettled()`?

---

### Master Exercise: Build Async Systems

#### Part 1: Implement Basic Promise

Build your own Promise implementation:

```javascript
class MyPromise {
  constructor(executor) {
    // Your implementation
    // executor receives (resolve, reject) functions
  }

  then(onFulfilled, onRejected) {
    // Your implementation
    // Should return a new Promise
  }

  catch(onRejected) {
    // Your implementation
  }

  finally(onFinally) {
    // Your implementation
  }
}

// Test:
new MyPromise((resolve, reject) => {
  setTimeout(() => resolve("Success!"), 1000);
})
  .then((result) => {
    console.log(result); // "Success!" after 1 second
    return result.toUpperCase();
  })
  .then((result) => {
    console.log(result); // "SUCCESS!"
  })
  .catch((error) => {
    console.error("Error:", error);
  })
  .finally(() => {
    console.log("Done!");
  });
```

**Requirements:**

- Three states: pending, fulfilled, rejected
- Can only transition once
- `.then()` returns new Promise
- `.catch()` catches errors
- `.finally()` always runs
- Handle synchronous and asynchronous resolution

#### Part 2: Implement Promise Combinators

Build `Promise.all`, `Promise.race`, `Promise.allSettled`, `Promise.any`:

```javascript
MyPromise.all = function (promises) {
  // Your implementation
  // Resolve when all resolve
  // Reject if any reject
};

MyPromise.race = function (promises) {
  // Your implementation
  // Resolve/reject with first settled Promise
};

MyPromise.allSettled = function (promises) {
  // Your implementation
  // Always resolves with array of results
};

MyPromise.any = function (promises) {
  // Your implementation
  // Resolve with first fulfilled
  // Reject if all reject
};

// Test:
const promises = [
  MyPromise.resolve(1),
  new MyPromise((resolve) => setTimeout(() => resolve(2), 100)),
  MyPromise.resolve(3),
];

MyPromise.all(promises).then((results) => {
  console.log(results); // [1, 2, 3]
});

MyPromise.race(promises).then((result) => {
  console.log(result); // 1 (first to resolve)
});
```

#### Part 3: Build Async Control Flow Utilities

Build practical async utilities:

```javascript
// 1. Retry with exponential backoff
async function retry(fn, attempts = 3, delay = 1000) {
  // Try fn()
  // If it fails, wait `delay` ms and try again
  // Double delay each time
  // After `attempts` failures, throw error
}

// Test:
let failCount = 0;
async function unreliableAPI() {
  if (failCount++ < 2) throw new Error("Failed");
  return "Success!";
}

retry(unreliableAPI, 3, 100)
  .then((result) => console.log(result)) // "Success!" after 2 retries
  .catch((error) => console.error("All attempts failed"));

// 2. Timeout wrapper
function timeout(promise, ms) {
  // Race promise against timeout
  // Reject if promise takes too long
}

// Test:
const slowPromise = new Promise((resolve) =>
  setTimeout(() => resolve("Done"), 2000)
);

timeout(slowPromise, 1000)
  .then((result) => console.log(result))
  .catch((error) => console.error("Timeout!")); // "Timeout!" after 1 second

// 3. Sequential execution
async function sequential(tasks) {
  // Execute array of async functions in sequence
  // Return array of results
}

// Test:
const delay = (ms) => new Promise((resolve) => setTimeout(resolve, ms));
const tasks = [
  () => delay(100).then(() => 1),
  () => delay(200).then(() => 2),
  () => delay(50).then(() => 3),
];

sequential(tasks).then((results) => {
  console.log(results); // [1, 2, 3] after 350ms total
});

// 4. Parallel with concurrency limit
async function parallel(tasks, limit = 2) {
  // Execute tasks with max `limit` running at once
  // Return results in order
}

// Test:
const tasks2 = [
  () => delay(100).then(() => 1),
  () => delay(50).then(() => 2),
  () => delay(200).then(() => 3),
  () => delay(75).then(() => 4),
];

parallel(tasks2, 2).then((results) => {
  console.log(results); // [1, 2, 3, 4] with max 2 running at once
});
```

#### Part 4: Build Request Deduplication

```javascript
class RequestDeduplicator {
  constructor() {
    this.pending = new Map();
  }

  async fetch(url) {
    // If same URL is already being fetched, return that Promise
    // Otherwise, start new fetch and cache the Promise
    // When fetch completes, remove from cache
  }
}

// Test:
const dedup = new RequestDeduplicator();

// These three requests will only trigger ONE actual fetch
Promise.all([
  dedup.fetch("/api/users"),
  dedup.fetch("/api/users"),
  dedup.fetch("/api/users"),
]).then(([result1, result2, result3]) => {
  console.log("All three get the same result");
  console.log(result1 === result2); // true
  console.log(result2 === result3); // true
});
```

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks use Promises for data fetching?
   - How does `useEffect` handle async operations?
   - What are common async patterns in frameworks?

2. **For Vanilla JavaScript:**

   - When should you use callbacks vs Promises vs async/await?
   - How do you debug async issues?
   - What are memory implications of Promise chains?

3. **Deeper Understanding:**
   - How does the microtask queue relate to Promises?
   - What is Promise chaining performance cost?
   - How do you cancel a Promise?

---

## Section 8: Advanced Async Control Flow

### The Problem

You're building a dashboard that needs to:

1. Fetch user data
2. Fetch user's posts (only after user data loads)
3. Fetch comments for each post (in parallel)
4. Show loading states
5. Handle errors gracefully
6. Support cancellation if user navigates away

**How do you orchestrate complex async operations** without creating a mess?

---

### Exploration Questions

#### Race Conditions

**Scenario 1: The Search Bug**

```javascript
let searchId = 0;

async function search(query) {
  const currentSearch = ++searchId;

  const results = await fetch(`/api/search?q=${query}`);

  if (currentSearch !== searchId) {
    // A newer search has started, ignore these results
    return;
  }

  displayResults(results);
}

// User types: "java"
search("j"); // Search 1
search("ja"); // Search 2
search("jav"); // Search 3
search("java"); // Search 4

// Search 1 completes last and shows old results!
```

**Explore:**

- What is a race condition?
- Why do old search results sometimes show?
- How does the search ID help?
- What are other ways to solve this?
- How do you test for race conditions?

**Scenario 2: Stale Closures**

```javascript
function Counter() {
  const [count, setCount] = useState(0);

  async function increment() {
    await delay(1000);
    setCount(count + 1); // BUG: Uses stale `count` value
  }

  // User clicks button 3 times quickly
  // Expected: count = 3
  // Actual: count = 1 (Why?)
}
```

**Explore:**

- What is a stale closure?
- Why does `count` not increment correctly?
- How do you fix this with functional updates?
- What are other ways to solve this?

#### Cancellation

**Scenario 3: AbortController**

```javascript
const controller = new AbortController();

fetch("/api/data", {signal: controller.signal})
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => {
    if (error.name === "AbortError") {
      console.log("Fetch aborted");
    }
  });

// Later: cancel the request
controller.abort();
```

**Explore:**

- What is AbortController?
- How do you cancel fetch requests?
- Can you cancel Promises?
- What happens to pending operations when aborted?
- How do you clean up after cancellation?

**Scenario 4: Cancellation Tokens**

```javascript
class CancellationToken {
  constructor() {
    this.cancelled = false;
  }

  cancel() {
    this.cancelled = true;
  }

  throwIfCancelled() {
    if (this.cancelled) throw new Error("Cancelled");
  }
}

async function longOperation(token) {
  await step1();
  token.throwIfCancelled();

  await step2();
  token.throwIfCancelled();

  await step3();
  return "Done";
}
```

**Explore:**

- How do cancellation tokens work?
- When should you check for cancellation?
- How is this different from AbortController?
- How do you propagate cancellation through nested calls?

#### Debouncing & Throttling Revisited

**Scenario 5: Debounced Search with Cancellation**

```javascript
function useDebounce(callback, delay) {
  // How do you implement debounce that:
  // 1. Delays execution
  // 2. Cancels previous pending calls
  // 3. Cleans up on unmount
}

function SearchBox() {
  const [query, setQuery] = useState("");

  const debouncedSearch = useDebounce(async (q) => {
    const results = await fetch(`/api/search?q=${q}`);
    setResults(results);
  }, 500);

  return (
    <input
      value={query}
      onChange={(e) => {
        setQuery(e.target.value);
        debouncedSearch(e.target.value);
      }}
    />
  );
}
```

**Explore:**

- How do you combine debouncing with async operations?
- How do you handle race conditions?
- How do you cancel pending searches?
- What happens when the component unmounts?

---

### Master Exercise: Build Advanced Async Utilities

#### Part 1: Build Request Queue with Concurrency

```javascript
class AsyncQueue {
  constructor(concurrency = 1) {
    // Your implementation
    // Run max `concurrency` tasks at once
  }

  async add(asyncFn) {
    // Add task to queue
    // Execute when slot available
    // Return result
  }

  async addAll(asyncFns) {
    // Add multiple tasks
    // Return results in order
  }

  clear() {
    // Clear all pending tasks
  }
}

// Test:
const queue = new AsyncQueue(2); // Max 2 concurrent

const tasks = [
  () => delay(100).then(() => console.log("Task 1")),
  () => delay(50).then(() => console.log("Task 2")),
  () => delay(200).then(() => console.log("Task 3")),
  () => delay(75).then(() => console.log("Task 4")),
  () => delay(125).then(() => console.log("Task 5")),
];

// Only 2 tasks run at a time
// Output order: Task 2, Task 1, Task 4, Task 3, Task 5
tasks.forEach((task) => queue.add(task));
```

**Requirements:**

- Respect concurrency limit
- Maintain task order
- Handle errors gracefully
- Support task prioritization (bonus)

#### Part 2: Build Retry System with Exponential Backoff

```javascript
class RetryStrategy {
  constructor(options = {}) {
    this.maxAttempts = options.maxAttempts || 3;
    this.initialDelay = options.initialDelay || 1000;
    this.maxDelay = options.maxDelay || 30000;
    this.factor = options.factor || 2;
    this.onRetry = options.onRetry || (() => {});
  }

  async execute(fn) {
    // Try fn()
    // If it fails, retry with exponential backoff
    // Call onRetry callback before each retry
    // After maxAttempts, throw error
  }
}

// Test:
const retry = new RetryStrategy({
  maxAttempts: 5,
  initialDelay: 100,
  factor: 2,
  onRetry: (attempt, delay, error) => {
    console.log(`Attempt ${attempt} failed: ${error.message}`);
    console.log(`Retrying in ${delay}ms...`);
  },
});

let attempts = 0;
const unreliableAPI = async () => {
  if (attempts++ < 3) throw new Error("Server error");
  return "Success!";
};

retry
  .execute(unreliableAPI)
  .then((result) => console.log(result))
  .catch((error) => console.error("All retries failed:", error));

// Output:
// Attempt 1 failed: Server error
// Retrying in 100ms...
// Attempt 2 failed: Server error
// Retrying in 200ms...
// Attempt 3 failed: Server error
// Retrying in 400ms...
// Success!
```

**Bonus:** Add jitter (random delay variation) to prevent thundering herd.

#### Part 3: Build Observable Data Fetcher

```javascript
class DataFetcher {
  constructor() {
    this.cache = new Map();
    this.pending = new Map();
    this.listeners = new Map();
  }

  subscribe(key, listener) {
    // Subscribe to data changes
    // Return unsubscribe function
  }

  async fetch(key, fetcher, options = {}) {
    // If data in cache and not stale, return cached
    // If fetch in progress, return pending Promise
    // Otherwise, fetch and cache
    // Notify all subscribers
  }

  invalidate(key) {
    // Remove from cache
    // Notify subscribers
  }

  prefetch(key, fetcher) {
    // Fetch data in background
    // Don't return Promise
  }
}

// Test:
const fetcher = new DataFetcher();

// Component 1 subscribes
fetcher.subscribe("user:1", (data) => {
  console.log("Component 1:", data);
});

// Component 2 subscribes
fetcher.subscribe("user:1", (data) => {
  console.log("Component 2:", data);
});

// Fetch data (only triggers ONE actual fetch)
await fetcher.fetch("user:1", () => fetch("/api/users/1"));

// Both components get notified
// Later: invalidate and refetch
fetcher.invalidate("user:1");
await fetcher.fetch("user:1", () => fetch("/api/users/1"));
// Both components notified again
```

**Requirements:**

- Request deduplication
- Cache management with TTL
- Subscription system
- Prefetching support
- Optimistic updates (bonus)

#### Part 4: Build Async State Machine

```javascript
class AsyncStateMachine {
  constructor(states, initialState) {
    this.states = states;
    this.currentState = initialState;
    this.data = null;
    this.error = null;
    this.listeners = [];
  }

  async transition(event, ...args) {
    // Find transition for current state + event
    // Execute transition
    // Update state
    // Notify listeners
  }

  subscribe(listener) {
    // Subscribe to state changes
  }

  getState() {
    return {
      state: this.currentState,
      data: this.data,
      error: this.error,
    };
  }
}

// Test: Data fetching state machine
const fetchMachine = new AsyncStateMachine(
  {
    idle: {
      FETCH: async function (url) {
        this.data = null;
        this.error = null;
        return "loading";
      },
    },
    loading: {
      SUCCESS: async function (data) {
        this.data = data;
        return "success";
      },
      ERROR: async function (error) {
        this.error = error;
        return "error";
      },
    },
    success: {
      REFETCH: async function (url) {
        return "loading";
      },
    },
    error: {
      RETRY: async function (url) {
        this.error = null;
        return "loading";
      },
    },
  },
  "idle"
);

// Subscribe to changes
fetchMachine.subscribe((state) => {
  console.log("State:", state);
});

// Execute state transitions
await fetchMachine.transition("FETCH", "/api/users");
// State: { state: 'loading', data: null, error: null }

// Simulate success
await fetchMachine.transition("SUCCESS", {users: []});
// State: { state: 'success', data: { users: [] }, error: null }

// Simulate error
await fetchMachine.transition("FETCH", "/api/error");
await fetchMachine.transition("ERROR", new Error("Network error"));
// State: { state: 'error', data: null, error: Error(...) }

// Retry
await fetchMachine.transition("RETRY", "/api/users");
// State: { state: 'loading', data: null, error: null }
```

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks handle race conditions?
   - How do frameworks implement request cancellation?
   - What are common async patterns in frameworks?

2. **For Vanilla JavaScript:**

   - When should you use async state machines?
   - How do you test async code reliably?
   - What are best practices for error handling?

3. **Deeper Understanding:**
   - How do you debug race conditions?
   - What tools help with async debugging?
   - How do you measure async performance?

---

# 🟠 PART 5: EVENT LOOP & SCHEDULING

---

## Section 9: Event Loop Deep Dive

### The Problem

```javascript
console.log("1");

setTimeout(() => console.log("2"), 0);

Promise.resolve().then(() => console.log("3"));

console.log("4");

// What order is logged? Why?
```

**Understanding the event loop** is critical for:

- Understanding why async code executes in a certain order
- Debugging timing issues
- Building responsive UIs that don't freeze
- Understanding how frameworks schedule updates

---

### Exploration Questions

#### Event Loop Fundamentals

**Scenario 1: Call Stack Basics**

```javascript
function first() {
  console.log("First start");
  second();
  console.log("First end");
}

function second() {
  console.log("Second start");
  third();
  console.log("Second end");
}

function third() {
  console.log("Third");
}

first();
```

**Explore:**

- What is the call stack?
- Draw the call stack at each step
- When does a function get removed from the stack?
- What happens when the stack is empty?
- What is a stack overflow?

**Scenario 2: Microtasks vs Macrotasks**

```javascript
console.log("Start");

setTimeout(() => console.log("Timeout 1"), 0);

Promise.resolve()
  .then(() => console.log("Promise 1"))
  .then(() => console.log("Promise 2"));

setTimeout(() => console.log("Timeout 2"), 0);

Promise.resolve().then(() => console.log("Promise 3"));

console.log("End");

// What order is logged? Why?
```

**Explore:**

- What is the microtask queue?
- What is the macrotask queue (task queue)?
- Which has higher priority?
- What goes into each queue?
- When does the event loop check each queue?

**Scenario 3: Complex Execution Order**

```javascript
console.log("1");

setTimeout(() => {
  console.log("2");
  Promise.resolve().then(() => console.log("3"));
}, 0);

Promise.resolve().then(() => {
  console.log("4");
  setTimeout(() => console.log("5"), 0);
});

console.log("6");

// Predict the order BEFORE running
```

**Explore:**

- Draw the call stack, microtask queue, and macrotask queue at each step
- Why does this execute in this specific order?
- What happens when a microtask adds a new microtask?
- What happens when a macrotask adds a new microtask?

#### Queue Types

**Scenario 4: What Goes Where?**

For each operation, determine which queue it uses:

```javascript
// Microtask or macrotask?
setTimeout(fn, 0);
setInterval(fn, 100);
Promise.resolve().then(fn);
queueMicrotask(fn);
requestAnimationFrame(fn);
requestIdleCallback(fn);
fetch(url).then(fn);
async function() { await something(); }
```

**Explore:**

- What is `queueMicrotask()`?
- What queue does `requestAnimationFrame` use?
- What queue does `requestIdleCallback` use?
- How do they differ from setTimeout?
- When should you use each?

**Scenario 5: Blocking the Event Loop**

```javascript
console.log("Start");

// This blocks the event loop
let sum = 0;
for (let i = 0; i < 1000000000; i++) {
  sum += i;
}

console.log("Done:", sum);

// Meanwhile, these are queued but can't execute:
setTimeout(() => console.log("Timeout"), 0);
Promise.resolve().then(() => console.log("Promise"));
```

**Explore:**

- What happens to queued tasks while the loop runs?
- Why does the UI freeze?
- How long can the call stack be blocked?
- How do you prevent blocking?
- What are worker threads for?

---

### Master Exercise: Event Loop Mastery

#### Part 1: Predict Execution Order

For each code snippet, predict the EXACT execution order BEFORE running:

```javascript
// Challenge 1
console.log("A");

setTimeout(() => console.log("B"), 0);

Promise.resolve().then(() => {
  console.log("C");
  setTimeout(() => console.log("D"), 0);
});

Promise.resolve().then(() => console.log("E"));

setTimeout(() => {
  console.log("F");
  Promise.resolve().then(() => console.log("G"));
}, 0);

console.log("H");

// Challenge 2
async function async1() {
  console.log("1");
  await async2();
  console.log("2");
}

async function async2() {
  console.log("3");
}

console.log("4");

setTimeout(() => console.log("5"), 0);

async1();

new Promise((resolve) => {
  console.log("6");
  resolve();
}).then(() => console.log("7"));

console.log("8");

// Challenge 3
Promise.resolve().then(() => {
  console.log("A");
  Promise.resolve().then(() => console.log("B"));
  console.log("C");
});

Promise.resolve().then(() => {
  console.log("D");
  Promise.resolve().then(() => console.log("E"));
});

console.log("F");
```

**For each:**

1. Write down your prediction
2. Draw the queues at each step
3. Run and verify
4. Explain WHY that order

#### Part 2: Build Event Loop Visualizer

Create a visual representation of the event loop:

```javascript
class EventLoopVisualizer {
  constructor() {
    this.callStack = [];
    this.microtaskQueue = [];
    this.macrotaskQueue = [];
    this.logs = [];
  }

  run(code) {
    // Execute code and track:
    // - Call stack changes
    // - Queue additions
    // - Console logs
    // - Execution order
  }

  visualize() {
    // Show state at each step:
    // Call Stack: [...]
    // Microtask Queue: [...]
    // Macrotask Queue: [...]
    // Logs: [...]
  }
}

// Test:
const visualizer = new EventLoopVisualizer();

visualizer.run(`
  console.log('1');
  setTimeout(() => console.log('2'), 0);
  Promise.resolve().then(() => console.log('3'));
  console.log('4');
`);

visualizer.visualize();
// Shows step-by-step execution with queue states
```

#### Part 3: Fix Blocking Code

You're given code that blocks the event loop. Fix it using async patterns:

```javascript
// Problem: Blocks UI for ~3 seconds
function processLargeDataset(data) {
  const result = [];
  for (let i = 0; i < data.length; i++) {
    // Expensive operation
    result.push(expensiveTransform(data[i]));
  }
  return result;
}

const data = new Array(100000).fill(0).map((_, i) => i);
const result = processLargeDataset(data);
console.log("Done");

// Fix it using async patterns so UI stays responsive
```

**Fix it multiple ways:**

1. Using `setTimeout` to batch processing
2. Using `requestIdleCallback`
3. Using `requestAnimationFrame`
4. Using Web Workers (if you know them)

**Compare:**

- Which is smoothest?
- Which completes fastest?
- Which is best for UI work?
- Which is best for background work?

#### Part 4: Build Task Scheduler

Create a scheduler that respects browser priorities:

```javascript
class TaskScheduler {
  constructor() {
    this.tasks = {
      high: [], // Run in microtasks
      normal: [], // Run in macrotasks
      low: [], // Run in idle time
      frame: [], // Run before next frame
    };
  }

  schedule(fn, priority = "normal") {
    // Add task to appropriate queue
    // Execute using correct API
  }

  scheduleHigh(fn) {
    // Microtask (highest priority)
  }

  scheduleNormal(fn) {
    // Macrotask (setTimeout)
  }

  scheduleLow(fn) {
    // Idle time (requestIdleCallback)
  }

  scheduleFrame(fn) {
    // Before next paint (requestAnimationFrame)
  }

  flush() {
    // Execute all pending tasks
  }
}

// Test:
const scheduler = new TaskScheduler();

scheduler.scheduleHigh(() => console.log("High priority"));
scheduler.scheduleNormal(() => console.log("Normal priority"));
scheduler.scheduleLow(() => console.log("Low priority"));
scheduler.scheduleFrame(() => console.log("Frame priority"));

// Observe execution order
```

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks use the event loop for rendering?
   - What is React's scheduler and how does it work?
   - How do frameworks batch updates?

2. **For Vanilla JavaScript:**

   - How do you keep UIs responsive with heavy computation?
   - When should you use each scheduling API?
   - How do you debug event loop issues?

3. **Deeper Understanding:**
   - What is the performance cost of many microtasks?
   - How do browsers prioritize different task types?
   - What are browser rendering phases?

---

## Section 10: Task Scheduling & Timing APIs

### The Problem

You're building a complex animation system. You need to:

1. Update positions every frame (60 FPS)
2. Fetch new data periodically
3. Process data in background without blocking UI
4. Measure performance

**Which timing API should you use for each task?**

- `setTimeout`?
- `setInterval`?
- `requestAnimationFrame`?
- `requestIdleCallback`?
- Performance API?

---

### Exploration Questions

#### Timing APIs

**Scenario 1: setTimeout vs setInterval**

```javascript
// Using setTimeout
let count = 0;
function loop() {
  console.log(count++);
  if (count < 5) {
    setTimeout(loop, 1000);
  }
}
loop();

// Using setInterval
let count2 = 0;
const interval = setInterval(() => {
  console.log(count2++);
  if (count2 >= 5) {
    clearInterval(interval);
  }
}, 1000);
```

**Explore:**

- What's the difference between setTimeout and setInterval?
- Which is more reliable?
- What happens if the callback takes longer than the interval?
- How do you cancel each?
- When should you use each?

**Scenario 2: requestAnimationFrame**

```javascript
let start = null;

function animate(timestamp) {
  if (!start) start = timestamp;
  const elapsed = timestamp - start;

  element.style.transform = `translateX(${elapsed / 10}px)`;

  if (elapsed < 2000) {
    requestAnimationFrame(animate);
  }
}

requestAnimationFrame(animate);
```

**Explore:**

- What is `requestAnimationFrame`?
- How is it different from setTimeout?
- What is the `timestamp` parameter?
- Why use this for animations?
- What happens when tab is hidden?

**Scenario 3: requestIdleCallback**

```javascript
requestIdleCallback((deadline) => {
  while (deadline.timeRemaining() > 0 && tasks.length > 0) {
    const task = tasks.pop();
    processTask(task);
  }

  if (tasks.length > 0) {
    requestIdleCallback(arguments.callee);
  }
});
```

**Explore:**

- What is `requestIdleCallback`?
- What is `deadline.timeRemaining()`?
- When does this run?
- What's it good for?
- What's the browser support?

#### Performance Timing

**Scenario 4: Performance API**

```javascript
// Measure operation timing
const start = performance.now();

await expensiveOperation();

const end = performance.now();
console.log(`Operation took ${end - start}ms`);

// vs

console.time("operation");
await expensiveOperation();
console.timeEnd("operation");

// vs

const start2 = Date.now();
await expensiveOperation();
const end2 = Date.now();
console.log(`Operation took ${end2 - start2}ms`);
```

**Explore:**

- What's the difference between `performance.now()` and `Date.now()`?
- Which is more accurate?
- What is `console.time`/`timeEnd`?
- How do you measure async operations?
- What is the Performance API?

**Scenario 5: Performance Marks and Measures**

```javascript
performance.mark("start-fetch");
await fetch("/api/data");
performance.mark("end-fetch");

performance.measure("fetch-duration", "start-fetch", "end-fetch");

const measures = performance.getEntriesByType("measure");
console.log(measures[0].duration);
```

**Explore:**

- What are performance marks?
- What are performance measures?
- How do you use them?
- How is this better than `performance.now()`?
- How do you visualize these in DevTools?

---

### Master Exercise: Build a Scheduling System

#### Part 1: Build Frame-Based Animator

```javascript
class Animator {
  constructor() {
    this.animations = [];
    this.rafId = null;
  }

  add(animation) {
    // Add animation to queue
    // animation = { update: (progress) => {...}, duration: ms }
    // Start RAF loop if not running
  }

  remove(animation) {
    // Remove animation
    // Stop RAF if no more animations
  }

  tick(timestamp) {
    // Update all animations
    // Remove completed animations
    // Request next frame if needed
  }

  stopAll() {
    // Cancel RAF
    // Clear all animations
  }
}

// Test:
const animator = new Animator();

const box = document.querySelector("#box");

animator.add({
  duration: 2000,
  update: (progress) => {
    box.style.transform = `translateX(${progress * 200}px)`;
  },
});

animator.add({
  duration: 1000,
  update: (progress) => {
    box.style.opacity = 1 - progress;
  },
});

// Box slides right while fading out
```

**Requirements:**

- Use `requestAnimationFrame`
- Support multiple concurrent animations
- Calculate progress (0 to 1)
- Clean up completed animations
- Provide easing functions (bonus)

#### Part 2: Build Background Task Processor

```javascript
class BackgroundProcessor {
  constructor() {
    this.tasks = [];
    this.processing = false;
  }

  addTask(task) {
    // Add task to queue
    // Start processing if not already
  }

  process(deadline) {
    // Process tasks while idle time available
    // Use deadline.timeRemaining()
    // Schedule next idle callback if more tasks
  }

  clear() {
    // Clear all tasks
  }

  onProgress(callback) {
    // Subscribe to progress updates
  }
}

// Test:
const processor = new BackgroundProcessor();

processor.onProgress((completed, total) => {
  console.log(`Progress: ${completed}/${total}`);
});

// Add 1000 tasks
for (let i = 0; i < 1000; i++) {
  processor.addTask(() => {
    // Do some work
    heavyComputation();
  });
}

// Tasks process in background without blocking UI
```

**Requirements:**

- Use `requestIdleCallback`
- Don't block main thread
- Report progress
- Handle task errors
- Fallback for browsers without `requestIdleCallback`

#### Part 3: Build Performance Monitor

```javascript
class PerformanceMonitor {
  constructor() {
    this.marks = new Map();
    this.measures = [];
  }

  start(label) {
    // Start timing with label
  }

  end(label) {
    // End timing with label
    // Return duration
  }

  measure(name, startLabel, endLabel) {
    // Create measure between two marks
  }

  getMetrics() {
    // Return all measures
  }

  async profile(fn, label) {
    // Profile async function
    // Return result and duration
  }

  visualize() {
    // Create visual timeline
    // Show all marks and measures
  }
}

// Test:
const monitor = new PerformanceMonitor();

monitor.start("data-fetch");
await fetch("/api/data");
monitor.end("data-fetch");

monitor.start("data-process");
processData(data);
monitor.end("data-process");

monitor.measure("total", "data-fetch", "data-process");

console.log(monitor.getMetrics());
// Shows timing for each operation

monitor.visualize();
// Shows visual timeline in console
```

#### Part 4: Build Smart Scheduler

Combine all timing APIs into one smart scheduler:

```javascript
class SmartScheduler {
  schedule(fn, options = {}) {
    const {priority, delay, frame, idle} = options;

    // Choose appropriate API based on options:
    // - priority === 'immediate': queueMicrotask
    // - priority === 'high': setTimeout 0
    // - frame === true: requestAnimationFrame
    // - idle === true: requestIdleCallback
    // - delay > 0: setTimeout with delay
  }

  scheduleRecurring(fn, interval, options = {}) {
    // Schedule recurring task
    // Use appropriate API
    // Return cancel function
  }

  batch(fns, options = {}) {
    // Execute multiple functions
    // Batch them appropriately
  }
}

// Test:
const scheduler = new SmartScheduler();

// Immediate (microtask)
scheduler.schedule(() => console.log("Immediate"), {priority: "immediate"});

// Next frame
scheduler.schedule(() => console.log("Frame"), {frame: true});

// Idle time
scheduler.schedule(() => console.log("Idle"), {idle: true});

// Delayed
scheduler.schedule(() => console.log("Delayed"), {delay: 1000});

// Recurring
const cancel = scheduler.scheduleRecurring(
  () => console.log("Every second"),
  1000,
  {frame: false}
);

// Later: cancel()
```

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks schedule updates?
   - What is React's Concurrent Mode and how does it use scheduling?
   - How do frameworks prevent UI jank?

2. **For Vanilla JavaScript:**

   - When should you use each timing API?
   - How do you build responsive UIs with heavy computation?
   - How do you profile and optimize performance?

3. **Deeper Understanding:**
   - What is the difference between FPS and idle time?
   - How do browsers decide when code runs?
   - What are browser rendering phases?

---

# 🔴 PART 6: METAPROGRAMMING WITH PROXIES

---

## Section 11: Proxies & Reflect API

### The Problem

```javascript
const user = {name: "Alice", age: 25};

// You want to:
// 1. Log every property access
// 2. Validate assignments
// 3. Trigger updates when data changes
// 4. Create computed properties

// How do you intercept object operations?
```

**Proxies let you intercept and customize object operations.** This is how Vue 3 implements reactivity!

Understanding Proxies is critical for:

- Building reactive systems (like Vue 3)
- Creating validation systems
- Implementing data binding
- Understanding how frameworks detect changes

---

### Exploration Questions

#### Proxy Basics

**Scenario 1: Property Access Interception**

```javascript
const target = {name: "Alice", age: 25};

const proxy = new Proxy(target, {
  get(target, property) {
    console.log(`Reading ${property}`);
    return target[property];
  },

  set(target, property, value) {
    console.log(`Writing ${property} = ${value}`);
    target[property] = value;
    return true;
  },
});

proxy.name; // Logs: "Reading name", returns "Alice"
proxy.age = 30; // Logs: "Writing age = 30"
```

**Explore:**

- What is a Proxy?
- What are traps?
- What is the `target` object?
- What operations can you intercept?
- Can you intercept property deletion?

**Scenario 2: Validation with Proxies**

```javascript
const user = new Proxy(
  {},
  {
    set(target, property, value) {
      if (property === "age" && typeof value !== "number") {
        throw new TypeError("Age must be a number");
      }
      if (property === "age" && value < 0) {
        throw new RangeError("Age cannot be negative");
      }
      target[property] = value;
      return true;
    },
  }
);

user.age = 25; // OK
user.age = -5; // Throws RangeError
user.age = "25"; // Throws TypeError
```

**Explore:**

- How do you validate on assignment?
- What should `set` trap return?
- Can you prevent assignment?
- How do you throw errors from traps?

#### Reflect API

**Scenario 3: Why Use Reflect?**

```javascript
const proxy = new Proxy(target, {
  get(target, property, receiver) {
    console.log(`Getting ${property}`);

    // These are equivalent, but Reflect is better:
    // return target[property];
    return Reflect.get(target, property, receiver);
  },
});
```

**Explore:**

- What is the Reflect API?
- Why use `Reflect.get` instead of `target[property]`?
- What is the `receiver` parameter?
- What Reflect methods exist?
- How do they relate to Proxy traps?

**Scenario 4: Proper Getter Interception**

```javascript
const target = {
  _value: 10,
  get value() {
    return this._value;
  },
};

// Without receiver
const proxy1 = new Proxy(target, {
  get(target, property) {
    return target[property]; // `this` in getter is target, not proxy
  },
});

// With receiver
const proxy2 = new Proxy(target, {
  get(target, property, receiver) {
    return Reflect.get(target, property, receiver); // `this` is proxy
  },
});
```

**Explore:**

- What is the `receiver` parameter?
- Why does it matter for getters?
- What happens to `this` in getters?
- When should you use receiver?

#### All Proxy Traps

**Scenario 5: Available Traps**

For each trap, understand when it's called:

```javascript
new Proxy(target, {
  // Property access
  get(target, property, receiver) {},
  set(target, property, value, receiver) {},
  has(target, property) {}, // 'property' in proxy
  deleteProperty(target, property) {}, // delete proxy.property
  ownKeys(target) {}, // Object.keys(proxy)
  getOwnPropertyDescriptor(target, property) {},

  // Function calls
  apply(target, thisArg, args) {}, // proxy()
  construct(target, args, newTarget) {}, // new proxy()

  // Prototype
  getPrototypeOf(target) {},
  setPrototypeOf(target, proto) {},

  // Extensibility
  isExtensible(target) {},
  preventExtensions(target) {},

  // Property definition
  defineProperty(target, property, descriptor) {},
});
```

**Explore:**

- What does each trap intercept?
- Which are most commonly used?
- Can you intercept all operations?
- What are invariants (unbreakable rules)?

---

### Master Exercise: Build Reactive Systems with Proxies

#### Part 1: Build Observable Objects

Create objects that notify listeners on changes:

```javascript
function createObservable(target, onChange) {
  // Use Proxy to intercept all changes
  // Call onChange whenever data changes
}

// Test:
const state = createObservable(
  {count: 0, name: "Alice"},
  (property, oldValue, newValue) => {
    console.log(`${property}: ${oldValue} → ${newValue}`);
  }
);

state.count = 1; // Logs: "count: 0 → 1"
state.name = "Bob"; // Logs: "name: Alice → Bob"
state.age = 25; // Logs: "age: undefined → 25"
delete state.age; // Logs: "age: 25 → undefined"
```

**Requirements:**

- Intercept property changes
- Track old and new values
- Handle property additions
- Handle property deletions
- Handle nested objects

#### Part 2: Build Vue-Style Reactivity

Implement Vue 3's reactivity system:

```javascript
const effectStack = [];

function reactive(target) {
  // Make object reactive with Proxy
  // Track property access
  // Trigger effects on changes
}

function effect(fn) {
  // Run fn and track which properties it reads
  // Re-run when those properties change
}

function computed(fn) {
  // Create computed value that auto-updates
}

// Test:
const state = reactive({
  count: 0,
  double: 0,
});

// Effect automatically re-runs when dependencies change
effect(() => {
  console.log(`Count is ${state.count}`);
});
// Immediately logs: "Count is 0"

state.count = 1;
// Logs: "Count is 1"

state.count = 2;
// Logs: "Count is 2"

// Computed values
const double = computed(() => state.count * 2);
console.log(double.value); // 4

state.count = 5;
console.log(double.value); // 10 (auto-updated)
```

**Requirements:**

- Track property reads in effects
- Re-run effects when dependencies change
- Handle nested objects
- Implement computed values
- Prevent infinite loops
- Handle array methods

**Hints:**

- Use a global stack to track active effects
- Store effects per property
- Trigger effects when properties change

#### Part 3: Build Validation Proxy

Create objects with built-in validation:

```javascript
function createValidated(schema) {
  // Return proxy that validates all assignments
}

// Test:
const userSchema = {
  name: {
    type: "string",
    minLength: 3,
    maxLength: 20,
  },
  age: {
    type: "number",
    min: 0,
    max: 150,
  },
  email: {
    type: "string",
    pattern: /^[^\s@]+@[^\s@]+\.[^\s@]+$/,
  },
};

const user = createValidated(userSchema);

user.name = "Alice"; // OK
user.name = "Al"; // Error: too short
user.age = 25; // OK
user.age = -5; // Error: below minimum
user.age = "25"; // Error: wrong type
user.email = "alice@example.com"; // OK
user.email = "invalid"; // Error: pattern mismatch
```

**Requirements:**

- Validate type
- Validate string length
- Validate number range
- Validate patterns (regex)
- Custom validators
- Helpful error messages

#### Part 4: Build Private Properties

Use Proxies to enforce truly private properties:

```javascript
function createPrivate(target) {
  // Properties starting with _ are private
  // Throw error if accessed from outside
}

// Test:
const obj = createPrivate({
  _private: "secret",
  public: "visible",
  getPrivate() {
    return this._private; // OK from inside
  },
});

console.log(obj.public); // 'visible' - OK
console.log(obj.getPrivate()); // 'secret' - OK (accessed from method)
console.log(obj._private); // Error: Cannot access private property
obj._private = "new"; // Error: Cannot access private property
```

**Challenge:** How do you know if access is from "inside" vs "outside"?

**Hint:** Use the call stack or a flag to track whether we're inside a method call.

#### Part 5: Build Query Builder with Proxy Magic

Create a fluent API using Proxies:

```javascript
function createQueryBuilder() {
  // Use Proxy to create fluent API
  // Any property access becomes part of the query
}

// Test:
const db = createQueryBuilder();

const query = db
  .from("users")
  .where("age")
  .gt(18)
  .and("status")
  .equals("active")
  .select("name", "email")
  .orderBy("name")
  .limit(10)
  .build();

console.log(query);
// {
//   table: 'users',
//   where: [
//     { field: 'age', op: 'gt', value: 18 },
//     { field: 'status', op: 'equals', value: 'active' }
//   ],
//   select: ['name', 'email'],
//   orderBy: 'name',
//   limit: 10
// }
```

**Requirement:** Use Proxy to make ANY method name work without defining methods explicitly.

**Hint:** The `get` trap can return functions dynamically based on the property name.

---

### Reflection Questions

1. **For Framework Foundations:**

   - How does Vue 3 use Proxies for reactivity?
   - What are the limitations of Proxy-based reactivity?
   - How is this different from React's approach?

2. **For Vanilla JavaScript:**

   - When should you use Proxies?
   - What are the performance implications?
   - What are alternatives to Proxies?

3. **Deeper Understanding:**
   - Can you proxy another proxy?
   - What are Proxy invariants?
   - How do you revoke a Proxy?

---

## Section 12: Advanced Metaprogramming

### The Problem

You want to build a library where:

- Objects track their own history (undo/redo)
- Methods are automatically logged
- Properties are lazy-loaded
- Access patterns are analyzed

**How do you add these behaviors without changing the original code?**

---

### Exploration Questions

#### Advanced Proxy Patterns

**Scenario 1: Negative Array Indices**

```javascript
const arr = ["a", "b", "c"];

// Python-style negative indexing
arr[-1]; // Should return 'c'
arr[-2]; // Should return 'b'

// How do you implement this with Proxies?
```

**Explore:**

- How do you intercept array access?
- How do you handle negative indices?
- Does this work with array methods?
- What are the edge cases?

**Scenario 2: Auto-Vivification**

```javascript
const obj = createAutoVivifying({});

obj.a.b.c.d = 10;
// Creates nested structure automatically
// No "Cannot read property 'b' of undefined" errors

console.log(obj);
// { a: { b: { c: { d: 10 } } } }
```

**Explore:**

- How do you create nested objects on access?
- How do you know when to create vs return?
- How deep can this go?
- What are the memory implications?

**Scenario 3: Method Chaining with Any Method**

```javascript
const obj = createChainable();

obj.method1().method2().method3().getValue();

// Even though these methods don't exist!
```

**Explore:**

- How do you make any method chainable?
- How do you track method calls?
- How do you end the chain?
- How is this useful?

#### Symbols & Metaprogramming

**Scenario 4: Well-Known Symbols**

```javascript
const obj = {
  [Symbol.iterator]() {
    // Make object iterable
  },

  [Symbol.toPrimitive](hint) {
    // Control type conversion
  },

  get [Symbol.toStringTag]() {
    // Control Object.prototype.toString() output
    return "CustomObject";
  },
};
```

**Explore:**

- What are well-known symbols?
- What does each symbol control?
- How many well-known symbols exist?
- How do you use them?

**Scenario 5: Custom Inspection**

```javascript
const obj = {
  _secret: "hidden",
  public: "visible",

  [Symbol.for("nodejs.util.inspect.custom")]() {
    return {public: this.public};
  },
};

console.log(obj);
// Only shows: { public: 'visible' }
```

**Explore:**

- How do you control console.log output?
- What is `Symbol.for()`?
- How is it different from `Symbol()`?
- What is the global symbol registry?

---

### Master Exercise: Build Advanced Metaprogramming Tools

#### Part 1: Build Time-Travel Object

Create objects that track their full history:

```javascript
function createTimeTravel(initial) {
  // Track all changes
  // Support undo/redo
  // Support going to any point in history
}

// Test:
const state = createTimeTravel({count: 0});

state.count = 1;
state.count = 2;
state.count = 3;

console.log(state.count); // 3

state.undo();
console.log(state.count); // 2

state.undo();
console.log(state.count); // 1

state.redo();
console.log(state.count); // 2

state.goto(0);
console.log(state.count); // 0

console.log(state.getHistory());
// [
//   { count: 0 },
//   { count: 1 },
//   { count: 2 },
//   { count: 3 }
// ]
```

**Requirements:**

- Track all changes
- Support undo/redo
- Support jumping to any point
- Show full history
- Handle nested objects

#### Part 2: Build Lazy-Loading Proxy

Create objects that load properties on demand:

```javascript
function createLazy(loaders) {
  // Properties are loaded only when accessed
  // Cache loaded values
}

// Test:
const user = createLazy({
  profile: async () => {
    console.log("Loading profile...");
    return await fetch("/api/profile").then((r) => r.json());
  },
  posts: async () => {
    console.log("Loading posts...");
    return await fetch("/api/posts").then((r) => r.json());
  },
});

// Nothing loads yet
await user.profile; // Logs "Loading profile...", then fetches
await user.profile; // Returns cached value, no fetch

await user.posts; // Logs "Loading posts...", then fetches
```

**Requirements:**

- Lazy load on first access
- Cache loaded values
- Support async loaders
- Handle errors
- Support invalidation

#### Part 3: Build Method Logger

Automatically log all method calls:

```javascript
function createLogged(target, options = {}) {
  // Log all method calls with arguments and return values
}

// Test:
class Calculator {
  add(a, b) {
    return a + b;
  }

  multiply(a, b) {
    return a * b;
  }
}

const calc = createLogged(new Calculator(), {
  logArgs: true,
  logResult: true,
  logTime: true,
});

calc.add(2, 3);
// [Calculator.add] Called with [2, 3]
// [Calculator.add] Returned 5 (took 0.1ms)

calc.multiply(4, 5);
// [Calculator.multiply] Called with [4, 5]
// [Calculator.multiply] Returned 20 (took 0.05ms)
```

**Requirements:**

- Log all method calls
- Log arguments
- Log return values
- Log execution time
- Configure what to log

#### Part 4: Build Access Pattern Analyzer

Track how objects are used:

```javascript
function createAnalyzed(target) {
  // Track all property access
  // Generate usage statistics
}

// Test:
const obj = createAnalyzed({
  name: "Alice",
  age: 25,
  email: "alice@example.com",
});

obj.name; // Read
obj.name; // Read again
obj.age; // Read
obj.age = 26; // Write
obj.name = "Bob"; // Write

console.log(obj.getAnalytics());
// {
//   name: { reads: 2, writes: 1 },
//   age: { reads: 1, writes: 1 },
//   email: { reads: 0, writes: 0 }
// }
```

**Requirements:**

- Track all reads and writes
- Count access per property
- Generate statistics
- Support resetting analytics

#### Part 5: Build Immutable Proxy

Create objects that can't be modified:

```javascript
function createImmutable(target) {
  // Prevent all modifications
  // Throw errors on mutation attempts
  // Deep immutability for nested objects
}

// Test:
const config = createImmutable({
  api: {
    url: "https://api.example.com",
    timeout: 5000,
  },
  features: ["auth", "logging"],
});

console.log(config.api.url); // 'https://api.example.com' - OK

config.api.url = "https://evil.com"; // Error: Cannot modify
config.features.push("new"); // Error: Cannot modify
delete config.api.timeout; // Error: Cannot delete
```

**Requirements:**

- Prevent property changes
- Prevent property additions
- Prevent property deletions
- Deep immutability (nested objects)
- Clear error messages

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks use Proxies for reactivity?
   - What are the performance trade-offs?
   - How do frameworks handle Proxy compatibility?

2. **For Vanilla JavaScript:**

   - When should you use advanced Proxy patterns?
   - How do you debug Proxy-wrapped objects?
   - What are the memory implications?

3. **Deeper Understanding:**
   - Can you combine multiple Proxy behaviors?
   - How do you test Proxy-based code?
   - What are the limitations of Proxies?

---

# ⚫ PART 7: ITERATORS, GENERATORS & LAZY EVALUATION

---

## Section 13: Iterators & Custom Iteration

### The Problem

```javascript
const range = {
  start: 1,
  end: 5,
};

// You want to do this:
for (let n of range) {
  console.log(n); // 1, 2, 3, 4, 5
}

// But range is not iterable!
// How do you make custom objects iterable?
```

**Understanding iterators is critical for:**

- Creating custom data structures
- Understanding how `for...of` works
- Building lazy evaluation systems
- Understanding generators

---

### Exploration Questions

#### Iterator Basics

**Scenario 1: What Is an Iterator?**

```javascript
const arr = [1, 2, 3];
const iterator = arr[Symbol.iterator]();

console.log(iterator.next()); // { value: 1, done: false }
console.log(iterator.next()); // { value: 2, done: false }
console.log(iterator.next()); // { value: 3, done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```

**Explore:**

- What is an iterator?
- What is the iterator protocol?
- What does `next()` return?
- What is `Symbol.iterator`?
- How does `for...of` use iterators?

**Scenario 2: Make Object Iterable**

```javascript
const range = {
  start: 1,
  end: 5,

  [Symbol.iterator]() {
    // How do you implement this?
  },
};

for (let n of range) {
  console.log(n); // Should log 1, 2, 3, 4, 5
}
```

**Explore:**

- How do you implement `Symbol.iterator`?
- What should it return?
- How do you maintain state across `next()` calls?
- Can you iterate the same object multiple times?

**Scenario 3: Iterable vs Iterator**

```javascript
const arr = [1, 2, 3];

// This is iterable (has Symbol.iterator)
console.log(typeof arr[Symbol.iterator]); // 'function'

// This is iterator (has next method)
const iterator = arr[Symbol.iterator]();
console.log(typeof iterator.next); // 'function'
```

**Explore:**

- What's the difference between iterable and iterator?
- Can an object be both?
- Why separate the two concepts?
- What are the benefits?

#### Custom Iterators

**Scenario 4: Infinite Sequences**

```javascript
const fibonacci = {
  [Symbol.iterator]() {
    let prev = 0,
      curr = 1;

    return {
      next() {
        const value = prev;
        [prev, curr] = [curr, prev + curr];
        return {value, done: false}; // Never done!
      },
    };
  },
};

// How do you safely consume this?
for (let n of fibonacci) {
  if (n > 100) break; // Must manually break
  console.log(n);
}
```

**Explore:**

- How do you create infinite sequences?
- When are they useful?
- How do you safely consume them?
- What are the memory implications?

**Scenario 5: Tree Traversal**

```javascript
const tree = {
  value: 1,
  left: {
    value: 2,
    left: {value: 4},
    right: {value: 5},
  },
  right: {
    value: 3,
    left: {value: 6},
    right: {value: 7},
  },
};

// Iterate depth-first
for (let value of tree) {
  console.log(value); // 1, 2, 4, 5, 3, 6, 7
}
```

**Explore:**

- How do you iterate a tree?
- How do you implement depth-first traversal?
- How would breadth-first differ?
- How do you maintain traversal state?

---

### Master Exercise: Build Custom Iterables

#### Part 1: Build Range Iterator

Create a range that works like Python's range:

```javascript
class Range {
  constructor(start, end, step = 1) {
    // Your implementation
  }

  [Symbol.iterator]() {
    // Return iterator
  }
}

// Test:
for (let n of new Range(1, 10)) {
  console.log(n); // 1, 2, 3, 4, 5, 6, 7, 8, 9
}

for (let n of new Range(0, 10, 2)) {
  console.log(n); // 0, 2, 4, 6, 8
}

for (let n of new Range(10, 0, -1)) {
  console.log(n); // 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
}

// Should work with spread
const nums = [...new Range(1, 5)]; // [1, 2, 3, 4]
```

**Requirements:**

- Support start, end, step
- Support negative step (counting down)
- Work with `for...of`
- Work with spread operator
- Work with `Array.from()`

#### Part 2: Build Fibonacci Iterator

Create infinite Fibonacci sequence:

```javascript
class Fibonacci {
  [Symbol.iterator]() {
    // Your implementation
  }

  static take(n) {
    // Return first n Fibonacci numbers
  }
}

// Test:
let count = 0;
for (let n of new Fibonacci()) {
  console.log(n);
  if (count++ >= 10) break; // 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55
}

// Helper method
const first10 = Fibonacci.take(10);
console.log(first10); // [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
```

**Requirements:**

- Infinite sequence
- Efficient (don't recalculate)
- Support taking first n numbers
- Memory efficient

#### Part 3: Build Tree Iterator

Make trees iterable with different traversal strategies:

```javascript
class TreeNode {
  constructor(value, left = null, right = null) {
    this.value = value;
    this.left = left;
    this.right = right;
  }

  *[Symbol.iterator]() {
    // Default: depth-first (pre-order)
  }

  *depthFirst() {
    // Depth-first traversal
  }

  *breadthFirst() {
    // Breadth-first traversal
  }
}

// Test:
const tree = new TreeNode(
  1,
  new TreeNode(2, new TreeNode(4), new TreeNode(5)),
  new TreeNode(3, new TreeNode(6), new TreeNode(7))
);

console.log([...tree]);
// [1, 2, 4, 5, 3, 6, 7] (depth-first)

console.log([...tree.breadthFirst()]);
// [1, 2, 3, 4, 5, 6, 7] (breadth-first)
```

**Requirements:**

- Support both depth-first and breadth-first
- Use generators (the `*` syntax)
- Work with any tree structure
- Memory efficient

#### Part 4: Build Linked List Iterator

Create an iterable linked list:

```javascript
class LinkedList {
  constructor() {
    this.head = null;
    this.tail = null;
    this.length = 0;
  }

  append(value) {
    // Add to end
  }

  prepend(value) {
    // Add to start
  }

  [Symbol.iterator]() {
    // Make iterable
  }
}

// Test:
const list = new LinkedList();
list.append(1);
list.append(2);
list.append(3);

for (let value of list) {
  console.log(value); // 1, 2, 3
}

const arr = [...list]; // [1, 2, 3]
```

**Requirements:**

- Standard linked list operations
- Iterable
- Work with `for...of`
- Work with spread operator

#### Part 5: Build Custom Collection

Create a collection with custom iteration:

```javascript
class Collection {
  constructor(items = []) {
    this.items = items;
  }

  [Symbol.iterator]() {
    // Default iterator
  }

  *reverse() {
    // Iterate in reverse
  }

  *filter(predicate) {
    // Iterate only matching items
  }

  *map(fn) {
    // Transform items while iterating
  }
}

// Test:
const collection = new Collection([1, 2, 3, 4, 5]);

console.log([...collection]);
// [1, 2, 3, 4, 5]

console.log([...collection.reverse()]);
// [5, 4, 3, 2, 1]

console.log([...collection.filter((n) => n % 2 === 0)]);
// [2, 4]

console.log([...collection.map((n) => n * 2)]);
// [2, 4, 6, 8, 10]
```

**Requirements:**

- Support chaining operations
- Lazy evaluation (only compute when needed)
- Memory efficient
- Use generators

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks use iterators?
   - How does React iterate over children?
   - What are keys in iteration?

2. **For Vanilla JavaScript:**

   - When should you make objects iterable?
   - What are the performance implications?
   - When should you use iterators vs arrays?

3. **Deeper Understanding:**
   - Can you combine iterators?
   - How do you transform iterator pipelines?
   - What is the difference between eager and lazy evaluation?

---

## Section 14: Generators & Async Generators

### The Problem

```javascript
// You want to create a sequence without storing all values:
function* fibonacci() {
  let [prev, curr] = [0, 1];
  while (true) {
    yield prev;
    [prev, curr] = [curr, prev + curr];
  }
}

// Take first 10
const fib = fibonacci();
for (let i = 0; i < 10; i++) {
  console.log(fib.next().value);
}
// 0, 1, 1, 2, 3, 5, 8, 13, 21, 34

// But what IS a generator?
```

**Understanding generators is critical for:**

- Lazy evaluation
- Infinite sequences
- Async iteration
- Understanding how frameworks handle suspense

---

### Exploration Questions

#### Generator Basics

**Scenario 1: What Are Generators?**

```javascript
function* simpleGenerator() {
  yield 1;
  yield 2;
  yield 3;
}

const gen = simpleGenerator();

console.log(gen.next()); // { value: 1, done: false }
console.log(gen.next()); // { value: 2, done: false }
console.log(gen.next()); // { value: 3, done: false }
console.log(gen.next()); // { value: undefined, done: true }
```

**Explore:**

- What is a generator function?
- What is the `*` syntax?
- What is `yield`?
- What does calling a generator return?
- How is this different from regular functions?

**Scenario 2: Generator State**

```javascript
function* counter() {
  let count = 0;
  while (true) {
    yield count++;
  }
}

const c1 = counter();
const c2 = counter();

console.log(c1.next().value); // 0
console.log(c1.next().value); // 1
console.log(c2.next().value); // 0
console.log(c1.next().value); // 2
```

**Explore:**

- Where is state stored?
- Are generators independent?
- What happens to state between yields?
- When is state destroyed?

**Scenario 3: Passing Values to Generators**

```javascript
function* echo() {
  const a = yield "First";
  console.log("Received:", a);

  const b = yield "Second";
  console.log("Received:", b);

  return "Done";
}

const gen = echo();

console.log(gen.next()); // { value: 'First', done: false }
console.log(gen.next("A")); // Logs "Received: A", returns { value: 'Second', done: false }
console.log(gen.next("B")); // Logs "Received: B", returns { value: 'Done', done: true }
```

**Explore:**

- How do you pass values into generators?
- What does `yield` return?
- How does `next(value)` work?
- Why is this useful?

**Scenario 4: Generator Delegation**

```javascript
function* inner() {
  yield 2;
  yield 3;
}

function* outer() {
  yield 1;
  yield* inner(); // Delegate to inner generator
  yield 4;
}

console.log([...outer()]); // [1, 2, 3, 4]
```

**Explore:**

- What is `yield*`?
- How does generator delegation work?
- Can you delegate to any iterable?
- When is this useful?

#### Async Generators

**Scenario 5: Async Generators**

```javascript
async function* fetchPages(url) {
  let page = 1;
  let hasMore = true;

  while (hasMore) {
    const response = await fetch(`${url}?page=${page}`);
    const data = await response.json();

    yield data.results;

    hasMore = data.hasNext;
    page++;
  }
}

// Consume
for await (let results of fetchPages("/api/users")) {
  console.log(results);
}
```

**Explore:**

- What are async generators?
- How do they differ from regular generators?
- What is `for await...of`?
- When should you use async generators?

**Scenario 6: Error Handling in Generators**

```javascript
function* errorGenerator() {
  try {
    yield 1;
    yield 2;
    yield 3;
  } catch (e) {
    console.log("Caught:", e);
  }
}

const gen = errorGenerator();

console.log(gen.next()); // { value: 1, done: false }
console.log(gen.throw("Error")); // Logs "Caught: Error", returns { value: undefined, done: true }
```

**Explore:**

- How do you throw errors into generators?
- How do generators handle errors?
- What is `generator.throw()`?
- How do you clean up after errors?

---

### Master Exercise: Build with Generators

#### Part 1: Build Lazy Sequence Operations

Create lazy map, filter, take using generators:

```javascript
function* map(iterable, fn) {
  // Transform each value lazily
}

function* filter(iterable, predicate) {
  // Filter values lazily
}

function* take(iterable, n) {
  // Take first n values
}

// Test:
const numbers = (function* () {
  let i = 0;
  while (true) yield i++;
})();

const pipeline = take(
  filter(
    map(numbers, (n) => n * 2),
    (n) => n % 3 === 0
  ),
  5
);

console.log([...pipeline]); // [0, 6, 12, 18, 24]
// Only computes 5 values, not infinite!
```

**Requirements:**

- Use generators
- Lazy evaluation (only compute when needed)
- Chainable
- Memory efficient

#### Part 2: Build Async Data Stream

Process streaming data with async generators:

```javascript
async function* streamData(url) {
  // Fetch paginated data
  // Yield each page
}

async function* processStream(stream) {
  // Process each chunk
  // Yield transformed data
}

// Test:
const stream = streamData("/api/data");
const processed = processStream(stream);

for await (let chunk of processed) {
  console.log(chunk);
}
```

**Requirements:**

- Async generators
- Handle pagination
- Process data in chunks
- Handle errors gracefully

#### Part 3: Build Generator-Based Control Flow

Implement `co`-like library for generator-based async:

```javascript
function run(generatorFn) {
  // Run generator that yields promises
  // Automatically handle promises
  // Return promise that resolves with final value
}

// Test:
run(function* () {
  const user = yield fetch("/api/user").then((r) => r.json());
  console.log("User:", user);

  const posts = yield fetch(`/api/posts?user=${user.id}`).then((r) => r.json());
  console.log("Posts:", posts);

  return {user, posts};
}).then((result) => {
  console.log("Done:", result);
});
```

**Requirements:**

- Handle yielded promises
- Support error handling
- Return final value
- Handle nested generators

#### Part 4: Build Infinite Sequences

Create useful infinite sequences:

```javascript
function* naturals() {
  // 0, 1, 2, 3, 4, ...
}

function* primes() {
  // 2, 3, 5, 7, 11, 13, ...
}

function* fibonacci() {
  // 0, 1, 1, 2, 3, 5, 8, 13, ...
}

// Test:
const first10Primes = [...take(primes(), 10)];
console.log(first10Primes); // [2, 3, 5, 7, 11, 13, 17, 19, 23, 29]

const fib = fibonacci();
const fibArray = [];
for (let i = 0; i < 15; i++) {
  fibArray.push(fib.next().value);
}
console.log(fibArray); // [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377]
```

**Requirements:**

- Truly infinite (never done)
- Memory efficient
- Can be consumed safely with `take`
- Efficient algorithms

#### Part 5: Build Coroutine System

Use generators for cooperative multitasking:

```javascript
class Scheduler {
  constructor() {
    this.tasks = [];
  }

  spawn(generatorFn) {
    // Add task to scheduler
  }

  run() {
    // Run all tasks cooperatively
    // Each task yields control
  }
}

// Test:
const scheduler = new Scheduler();

scheduler.spawn(function* () {
  console.log("Task 1: Start");
  yield;
  console.log("Task 1: Middle");
  yield;
  console.log("Task 1: End");
});

scheduler.spawn(function* () {
  console.log("Task 2: Start");
  yield;
  console.log("Task 2: End");
});

scheduler.run();
// Task 1: Start
// Task 2: Start
// Task 1: Middle
// Task 2: End
// Task 1: End
```

**Requirements:**

- Run multiple generators cooperatively
- Fair scheduling (round-robin)
- Tasks yield control voluntarily
- Handle task completion

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks use generators?
   - How does React Suspense relate to generators?
   - What is the Fiber architecture?

2. **For Vanilla JavaScript:**

   - When should you use generators?
   - What are the performance implications?
   - When are generators better than regular functions?

3. **Deeper Understanding:**
   - Can generators be garbage collected mid-execution?
   - How do generators relate to continuations?
   - What is the memory cost of suspended generators?

---

# 🟤 PART 8: MEMORY, PERFORMANCE & DEBUGGING

---

## Section 15: Memory Management & Leak Prevention

### The Problem

```javascript
// This code has a memory leak!
class EventEmitter {
  constructor() {
    this.listeners = [];
  }

  on(event, callback) {
    this.listeners.push({event, callback});
  }
}

const emitter = new EventEmitter();

// Components add listeners but never remove them
for (let i = 0; i < 1000; i++) {
  emitter.on("click", () => {
    console.log(`Component ${i} clicked`);
  });
}

// All 1000 closures stay in memory forever!
```

**Understanding memory is critical for:**

- Building apps that don't leak memory
- Understanding when objects are garbage collected
- Optimizing performance
- Debugging production issues

---

### Exploration Questions

#### Memory Fundamentals

**Scenario 1: Garbage Collection Basics**

```javascript
function createData() {
  const largeArray = new Array(1000000);
  return largeArray;
}

const data = createData();
// largeArray is in memory (referenced by data)

data = null;
// Now largeArray can be garbage collected
```

**Explore:**

- How does garbage collection work?
- When are objects collected?
- What is reachability?
- Can you force garbage collection?

**Scenario 2: Common Memory Leaks**

```javascript
// Leak 1: Forgotten timer
setInterval(() => {
  console.log("Running...");
}, 1000);
// Never cleared, runs forever!

// Leak 2: Detached DOM elements
const element = document.getElementById("myDiv");
document.body.removeChild(element);
// element is removed from DOM but still in memory!

// Leak 3: Closures
function createClosure() {
  const large = new Array(1000000);
  return function () {
    console.log(large[0]);
  };
}
const fn = createClosure();
// large stays in memory as long as fn exists

// Leak 4: Event listeners
element.addEventListener("click", function handler() {
  // If element is removed but listener not removed,
  // both element and handler stay in memory
});
```

**Explore:**

- Why does each cause a leak?
- How do you fix each one?
- How do you detect these leaks?
- What tools help find leaks?

#### WeakMap and WeakSet

**Scenario 3: WeakMap for Metadata**

```javascript
// Strong reference (prevents GC)
const metadata = new Map();

function attachMetadata(obj, data) {
  metadata.set(obj, data);
  // obj can't be garbage collected!
}

// Weak reference (allows GC)
const weakMetadata = new WeakMap();

function attachWeakMetadata(obj, data) {
  weakMetadata.set(obj, data);
  // obj can be garbage collected when no other references exist
}
```

**Explore:**

- What is WeakMap?
- How is it different from Map?
- When should you use WeakMap?
- What are the limitations?

**Scenario 4: WeakSet for Tracking**

```javascript
const visited = new WeakSet();

function process(obj) {
  if (visited.has(obj)) {
    return; // Already processed
  }

  visited.add(obj);
  // Process obj...
}
```

**Explore:**

- What is WeakSet?
- How is it different from Set?
- When should you use WeakSet?
- Why can't you iterate WeakSet?

#### Memory Profiling

**Scenario 5: Finding Memory Leaks**

```javascript
// How do you find and fix this leak?
class DataCache {
  constructor() {
    this.cache = new Map();
  }

  set(key, value) {
    this.cache.set(key, value);
    // Cache grows forever!
  }

  get(key) {
    return this.cache.get(key);
  }
}
```

**Explore:**

- How do you use Chrome DevTools Memory profiler?
- What is a heap snapshot?
- How do you compare snapshots?
- How do you identify leaking objects?

---

### Master Exercise: Memory Management

#### Part 1: Fix Memory Leaks

Fix all the memory leaks in this code:

```javascript
// Leak 1: Event emitter
class EventEmitter {
  constructor() {
    this.listeners = {};
  }

  on(event, callback) {
    if (!this.listeners[event]) {
      this.listeners[event] = [];
    }
    this.listeners[event].push(callback);
    // No way to remove listeners!
  }

  emit(event, ...args) {
    (this.listeners[event] || []).forEach((cb) => cb(...args));
  }
}

// Leak 2: Timer
class PollingComponent {
  constructor(url) {
    this.url = url;
    this.interval = setInterval(() => {
      fetch(this.url).then((data) => this.handleData(data));
    }, 1000);
    // Never cleared!
  }

  handleData(data) {
    console.log(data);
  }
}

// Leak 3: Circular reference
function createCircular() {
  const obj1 = {};
  const obj2 = {};
  obj1.ref = obj2;
  obj2.ref = obj1;
  return obj1;
  // Can obj1 and obj2 be GC'd?
}

// Leak 4: Cache without limit
class Cache {
  constructor() {
    this.data = new Map();
  }

  set(key, value) {
    this.data.set(key, value);
    // Grows forever!
  }
}
```

**Fix each leak and explain:**

- Why it leaks
- How your fix prevents the leak
- How you would test the fix

#### Part 2: Build LRU Cache

Create a cache with automatic eviction:

```javascript
class LRUCache {
  constructor(maxSize) {
    // Your implementation
    // Use WeakMap or Map as appropriate
  }

  get(key) {
    // Return value if exists
    // Mark as recently used
  }

  set(key, value) {
    // Add to cache
    // Evict least recently used if over maxSize
  }

  has(key) {
    // Check if key exists
  }

  clear() {
    // Clear all entries
  }
}

// Test:
const cache = new LRUCache(3);

cache.set("a", 1);
cache.set("b", 2);
cache.set("c", 3);
console.log(cache.has("a")); // true

cache.set("d", 4); // Evicts 'a' (least recently used)
console.log(cache.has("a")); // false
console.log(cache.has("d")); // true

cache.get("b"); // Marks 'b' as recently used
cache.set("e", 5); // Evicts 'c', not 'b'
console.log(cache.has("c")); // false
console.log(cache.has("b")); // true
```

**Requirements:**

- Fixed size
- Evict least recently used
- O(1) get and set
- Track access order

#### Part 3: Build Resource Pool

Create a reusable object pool to reduce GC pressure:

```javascript
class ObjectPool {
  constructor(factory, maxSize = 100) {
    // Your implementation
  }

  acquire() {
    // Get object from pool or create new
  }

  release(obj) {
    // Return object to pool
    // Reset state
  }

  clear() {
    // Clear pool
  }
}

// Test:
const pool = new ObjectPool(
  () => ({x: 0, y: 0}), // Factory
  10 // Max size
);

const obj1 = pool.acquire();
obj1.x = 10;
obj1.y = 20;

pool.release(obj1); // Returns to pool, resets state

const obj2 = pool.acquire(); // Reuses obj1
console.log(obj2.x); // 0 (reset)
```

**Requirements:**

- Reuse objects
- Reset state on release
- Max size limit
- Track pool statistics

#### Part 4: Build Memory Leak Detector

Create a tool to detect potential memory leaks:

```javascript
class LeakDetector {
  constructor() {
    this.tracked = new WeakMap();
    this.counters = new Map();
  }

  track(obj, label) {
    // Track object with label
    // Count how many objects of this type exist
  }

  check(label) {
    // Return count of tracked objects with label
  }

  report() {
    // Generate report of all tracked objects
  }
}

// Test:
const detector = new LeakDetector();

function createComponent() {
  const component = {name: "MyComponent"};
  detector.track(component, "MyComponent");
  return component;
}

const components = [];
for (let i = 0; i < 100; i++) {
  components.push(createComponent());
}

console.log(detector.check("MyComponent")); // 100

// Clear half
components.splice(0, 50);

// Force GC (in real environment)
// console.log(detector.check('MyComponent')); // Should be ~50
```

**Requirements:**

- Track object creation
- Count live objects
- Use WeakMap to allow GC
- Generate reports

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks prevent memory leaks?
   - How does React cleanup effects?
   - How do frameworks handle component unmounting?

2. **For Vanilla JavaScript:**

   - How do you profile memory in production?
   - What tools help detect leaks?
   - How do you optimize for low-memory devices?

3. **Deeper Understanding:**
   - How does GC affect performance?
   - What is generational garbage collection?
   - How do you write GC-friendly code?

---

## Section 16: Performance Profiling & Optimization

### The Problem

```javascript
// This code is slow, but why?
function processData(data) {
  const results = [];
  for (let i = 0; i < data.length; i++) {
    const item = data[i];
    const processed = expensiveOperation(item);
    const validated = validate(processed);
    const formatted = format(validated);
    results.push(formatted);
  }
  return results;
}

// How do you:
// 1. Measure where time is spent?
// 2. Identify bottlenecks?
// 3. Optimize without breaking functionality?
```

**Understanding performance is critical for:**

- Building fast applications
- Identifying bottlenecks
- Making informed optimization decisions
- Debugging performance issues

---

### Exploration Questions

#### Performance Measurement

**Scenario 1: Measuring Time**

```javascript
// Method 1: performance.now()
const start = performance.now();
expensiveOperation();
const end = performance.now();
console.log(`Took ${end - start}ms`);

// Method 2: console.time()
console.time("operation");
expensiveOperation();
console.timeEnd("operation");

// Method 3: Performance marks
performance.mark("start");
expensiveOperation();
performance.mark("end");
performance.measure("operation", "start", "end");
```

**Explore:**

- Which method is most accurate?
- When should you use each?
- How do you measure async operations?
- What is the overhead of measurement?

**Scenario 2: Profiling CPU**

```javascript
// How do you find what's slow?
function complexOperation() {
  step1(); // 50ms?
  step2(); // 200ms?
  step3(); // 10ms?
}
```

**Explore:**

- How do you use Chrome DevTools profiler?
- What is the flame graph?
- How do you identify hot paths?
- What is self time vs total time?

#### Common Performance Issues

**Scenario 3: Loop Optimization**

```javascript
// Slow version
for (let i = 0; i < array.length; i++) {
  doSomething(array[i]);
}

// Why is this faster?
const len = array.length;
for (let i = 0; i < len; i++) {
  doSomething(array[i]);
}
```

**Explore:**

- Does caching length matter?
- When does it matter?
- What about `for...of`?
- What about `forEach`?

**Scenario 4: String Concatenation**

```javascript
// Slow for large strings
let result = "";
for (let i = 0; i < 10000; i++) {
  result += "text";
}

// Faster
const parts = [];
for (let i = 0; i < 10000; i++) {
  parts.push("text");
}
const result = parts.join("");
```

**Explore:**

- Why is concatenation slow?
- Why is array join faster?
- When does it matter?
- What about template literals?

**Scenario 5: Function Call Overhead**

```javascript
// Many small function calls
function add(a, b) {
  return a + b;
}

for (let i = 0; i < 1000000; i++) {
  add(i, i + 1);
}

// Inlined
for (let i = 0; i < 1000000; i++) {
  const result = i + (i + 1);
}
```

**Explore:**

- Do function calls have overhead?
- When does it matter?
- Do engines inline functions?
- Should you manually inline?

---

### Master Exercise: Performance Optimization

#### Part 1: Build Performance Monitor

Create a comprehensive performance monitoring system:

```javascript
class PerformanceMonitor {
  constructor() {
    this.metrics = new Map();
  }

  start(label) {
    // Start timing operation
  }

  end(label) {
    // End timing, record result
  }

  mark(label) {
    // Create performance mark
  }

  measure(name, startMark, endMark) {
    // Create performance measure
  }

  getMetric(label) {
    // Get timing for label
  }

  getAllMetrics() {
    // Get all recorded timings
  }

  getStats(label) {
    // Get min, max, avg, median for label
  }

  report() {
    // Generate performance report
  }
}

// Test:
const monitor = new PerformanceMonitor();

for (let i = 0; i < 100; i++) {
  monitor.start("operation");
  // Do work
  expensiveOperation();
  monitor.end("operation");
}

console.log(monitor.getStats("operation"));
// { min: 10, max: 50, avg: 25, median: 23, count: 100 }

monitor.report();
// Displays formatted report of all metrics
```

**Requirements:**

- Track multiple metrics
- Calculate statistics
- Support performance marks/measures
- Generate reports
- Low overhead

#### Part 2: Optimize Slow Code

Given this slow code, optimize it:

```javascript
// Slow version (takes ~5 seconds)
function processUsers(users) {
  const results = [];

  for (let i = 0; i < users.length; i++) {
    const user = users[i];

    // Expensive validation (called for each user)
    if (isValid(user.email)) {
      // Expensive transformation
      const processed = {
        id: user.id,
        name: user.firstName + " " + user.lastName,
        email: user.email.toLowerCase(),
        age: calculateAge(user.birthDate),
      };

      // Expensive formatting
      processed.formatted = formatUser(processed);

      results.push(processed);
    }
  }

  // Expensive sort
  results.sort((a, b) => {
    return a.name.localeCompare(b.name);
  });

  return results;
}

// Test data
const users = generateUsers(10000);

console.time("slow");
const result = processUsers(users);
console.timeEnd("slow");
```

**Your task:**

1. Profile the code
2. Identify bottlenecks
3. Optimize each bottleneck
4. Measure improvements
5. Document what you optimized and why

**Optimization strategies to try:**

- Memoization
- Caching
- Batching
- Lazy evaluation
- Better algorithms
- Reduce allocations

#### Part 3: Build Benchmark Suite

Create a benchmarking system:

```javascript
class Benchmark {
  constructor(name, fn, options = {}) {
    this.name = name;
    this.fn = fn;
    this.iterations = options.iterations || 1000;
  }

  run() {
    // Run benchmark multiple times
    // Return statistics
  }
}

class BenchmarkSuite {
  constructor(name) {
    this.name = name;
    this.benchmarks = [];
  }

  add(name, fn, options) {
    // Add benchmark
  }

  run() {
    // Run all benchmarks
    // Compare results
  }

  report() {
    // Generate comparison report
  }
}

// Test:
const suite = new BenchmarkSuite("Array vs Object");

suite.add("Array lookup", () => {
  const arr = [1, 2, 3, 4, 5];
  return arr[2];
});

suite.add("Object lookup", () => {
  const obj = {0: 1, 1: 2, 2: 3, 3: 4, 4: 5};
  return obj[2];
});

suite.run();
suite.report();
// Displays which is faster and by how much
```

**Requirements:**

- Multiple iterations for accuracy
- Warm-up phase
- Statistical analysis
- Comparison between benchmarks
- Report generation

#### Part 4: Build Lazy Evaluation System

Optimize data processing with lazy evaluation:

```javascript
class Lazy {
  constructor(iterable) {
    this.iterable = iterable;
  }

  map(fn) {
    // Lazy map (doesn't execute immediately)
  }

  filter(predicate) {
    // Lazy filter
  }

  take(n) {
    // Take first n items
  }

  toArray() {
    // Materialize results
  }
}

// Test:
const numbers = Lazy.range(0, 1000000); // 1 million numbers

const result = numbers
  .map((n) => n * 2)
  .filter((n) => n % 3 === 0)
  .take(10)
  .toArray();

// Should only process enough to get 10 results
// Not all 1 million numbers!

console.log(result);
```

**Requirements:**

- Lazy evaluation (no work until needed)
- Chainable operations
- Only compute what's needed
- Compare performance to eager evaluation

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks optimize rendering?
   - What is reconciliation optimization?
   - How do frameworks minimize reflows?

2. **For Vanilla JavaScript:**

   - When should you optimize?
   - How do you measure real-world performance?
   - What are premature optimization pitfalls?

3. **Deeper Understanding:**
   - How do engines optimize code?
   - What is JIT compilation?
   - How do you write optimization-friendly code?

---

# 🔷 PART 9: ARCHITECTURAL PATTERNS

---

## Section 17: Design Patterns in JavaScript

### The Problem

You're building a large application. How do you structure your code so it's:

- Maintainable
- Testable
- Reusable
- Scalable

**Design patterns provide proven solutions to common problems.**

---

### Exploration Questions

#### Creational Patterns

**Scenario 1: Singleton Pattern**

```javascript
// Only one instance should exist
class Database {
  constructor() {
    if (Database.instance) {
      return Database.instance;
    }
    this.connection = this.connect();
    Database.instance = this;
  }

  connect() {
    return "Connected to DB";
  }
}

const db1 = new Database();
const db2 = new Database();
console.log(db1 === db2); // true
```

**Explore:**

- What is the Singleton pattern?
- When should you use it?
- What are the drawbacks?
- How do you test singletons?

**Scenario 2: Factory Pattern**

```javascript
class ButtonFactory {
  createButton(type) {
    switch (type) {
      case "primary":
        return new PrimaryButton();
      case "secondary":
        return new SecondaryButton();
      case "danger":
        return new DangerButton();
      default:
        throw new Error("Unknown button type");
    }
  }
}

const factory = new ButtonFactory();
const btn = factory.createButton("primary");
```

**Explore:**

- What is the Factory pattern?
- When should you use it?
- How does it help with testability?
- What's the difference between Factory and Abstract Factory?

#### Structural Patterns

**Scenario 3: Observer Pattern**

```javascript
class Subject {
  constructor() {
    this.observers = [];
  }

  subscribe(observer) {
    this.observers.push(observer);
  }

  unsubscribe(observer) {
    this.observers = this.observers.filter((obs) => obs !== observer);
  }

  notify(data) {
    this.observers.forEach((observer) => observer.update(data));
  }
}

const subject = new Subject();

subject.subscribe({
  update(data) {
    console.log("Observer 1:", data);
  },
});

subject.notify("Hello!"); // All observers notified
```

**Explore:**

- What is the Observer pattern?
- How does it relate to pub/sub?
- When should you use it?
- How does it help decouple code?

**Scenario 4: Decorator Pattern**

```javascript
class Coffee {
  cost() {
    return 5;
  }
}

class MilkDecorator {
  constructor(coffee) {
    this.coffee = coffee;
  }

  cost() {
    return this.coffee.cost() + 2;
  }
}

class SugarDecorator {
  constructor(coffee) {
    this.coffee = coffee;
  }

  cost() {
    return this.coffee.cost() + 1;
  }
}

let coffee = new Coffee();
coffee = new MilkDecorator(coffee);
coffee = new SugarDecorator(coffee);

console.log(coffee.cost()); // 8
```

**Explore:**

- What is the Decorator pattern?
- When should you use it?
- How is it different from inheritance?
- How does it enable composition?

#### Behavioral Patterns

**Scenario 5: Strategy Pattern**

```javascript
class PaymentContext {
  constructor(strategy) {
    this.strategy = strategy;
  }

  setStrategy(strategy) {
    this.strategy = strategy;
  }

  pay(amount) {
    return this.strategy.pay(amount);
  }
}

class CreditCardStrategy {
  pay(amount) {
    return `Paid ${amount} with credit card`;
  }
}

class PayPalStrategy {
  pay(amount) {
    return `Paid ${amount} with PayPal`;
  }
}

const payment = new PaymentContext(new CreditCardStrategy());
console.log(payment.pay(100));

payment.setStrategy(new PayPalStrategy());
console.log(payment.pay(100));
```

**Explore:**

- What is the Strategy pattern?
- When should you use it?
- How does it enable flexibility?
- How does it relate to dependency injection?

---

### Master Exercise: Implement Design Patterns

#### Part 1: Build Event System (Observer Pattern)

Create a robust event system:

```javascript
class EventEmitter {
  constructor() {
    // Your implementation
  }

  on(event, callback) {
    // Subscribe to event
    // Return unsubscribe function
  }

  once(event, callback) {
    // Subscribe but only fire once
  }

  off(event, callback) {
    // Unsubscribe
  }

  emit(event, ...args) {
    // Trigger all listeners
  }

  listenerCount(event) {
    // Count listeners for event
  }
}

// Test:
const emitter = new EventEmitter();

const unsubscribe = emitter.on("data", (data) => {
  console.log("Received:", data);
});

emitter.emit("data", {value: 123});
// Logs: "Received: { value: 123 }"

unsubscribe(); // Stop listening

emitter.once("done", () => {
  console.log("Done!");
});

emitter.emit("done"); // Logs: "Done!"
emitter.emit("done"); // Nothing (only once)
```

**Requirements:**

- Multiple listeners per event
- Unsubscribe support
- Once-only listeners
- Wildcard events (bonus)
- Error handling

#### Part 2: Build Middleware System (Chain of Responsibility)

Create Express-style middleware:

```javascript
class MiddlewareChain {
  constructor() {
    this.middlewares = [];
  }

  use(middleware) {
    // Add middleware to chain
  }

  execute(context) {
    // Run middleware chain
    // Each middleware can:
    // 1. Modify context
    // 2. Call next()
    // 3. Stop chain
  }
}

// Test:
const chain = new MiddlewareChain();

chain.use((context, next) => {
  console.log("Middleware 1: Before");
  next();
  console.log("Middleware 1: After");
});

chain.use((context, next) => {
  console.log("Middleware 2: Before");
  context.data = "Modified";
  next();
  console.log("Middleware 2: After");
});

chain.use((context, next) => {
  console.log("Middleware 3:", context.data);
  // Don't call next() - stops chain
});

chain.execute({data: "Original"});
// Output:
// Middleware 1: Before
// Middleware 2: Before
// Middleware 3: Modified
// Middleware 2: After
// Middleware 1: After
```

**Requirements:**

- Sequential execution
- `next()` function
- Error handling
- Async middleware support
- Ability to stop chain

#### Part 3: Build Plugin System

Create an extensible plugin architecture:

```javascript
class Application {
  constructor() {
    this.plugins = [];
  }

  use(plugin) {
    // Register plugin
    // Plugin can add:
    // - Methods
    // - Event listeners
    // - Middleware
    // - Configuration
  }

  // Core functionality here
}

// Test:
const app = new Application();

// Plugin 1: Logger
app.use({
  name: "logger",
  install(app) {
    app.log = (message) => {
      console.log(`[LOG] ${message}`);
    };
  },
});

// Plugin 2: Router
app.use({
  name: "router",
  install(app) {
    app.routes = {};
    app.route = (path, handler) => {
      app.routes[path] = handler;
    };
  },
});

// Use plugins
app.log("Application started");
app.route("/home", () => console.log("Home page"));
```

**Requirements:**

- Plugin registration
- Plugin lifecycle (install, uninstall)
- Plugin dependencies
- Prevent duplicate plugins
- Plugin configuration

#### Part 4: Build Component Factory

Create a factory for UI components:

```javascript
class ComponentFactory {
  constructor() {
    this.components = new Map();
  }

  register(name, ComponentClass) {
    // Register component type
  }

  create(name, props) {
    // Create component instance
  }

  has(name) {
    // Check if component registered
  }
}

// Test:
const factory = new ComponentFactory();

class Button {
  constructor(props) {
    this.props = props;
  }

  render() {
    return `<button>${this.props.label}</button>`;
  }
}

factory.register("button", Button);

const btn = factory.create("button", {label: "Click me"});
console.log(btn.render()); // <button>Click me</button>
```

**Requirements:**

- Register component types
- Create instances
- Support configuration
- Validate components
- Support extending/overriding

#### Part 5: Build Command Pattern System

Implement undo/redo with commands:

```javascript
class Command {
  execute() {
    throw new Error("Must implement execute()");
  }

  undo() {
    throw new Error("Must implement undo()");
  }
}

class CommandManager {
  constructor() {
    this.history = [];
    this.currentIndex = -1;
  }

  execute(command) {
    // Execute command
    // Add to history
  }

  undo() {
    // Undo last command
  }

  redo() {
    // Redo last undone command
  }

  canUndo() {
    // Check if undo possible
  }

  canRedo() {
    // Check if redo possible
  }
}

// Test:
class AddCommand extends Command {
  constructor(receiver, value) {
    super();
    this.receiver = receiver;
    this.value = value;
  }

  execute() {
    this.receiver.value += this.value;
  }

  undo() {
    this.receiver.value -= this.value;
  }
}

const state = {value: 0};
const manager = new CommandManager();

manager.execute(new AddCommand(state, 5));
console.log(state.value); // 5

manager.execute(new AddCommand(state, 3));
console.log(state.value); // 8

manager.undo();
console.log(state.value); // 5

manager.redo();
console.log(state.value); // 8
```

**Requirements:**

- Execute commands
- Undo/redo support
- Command history
- Macro commands (multiple commands as one)

---

### Reflection Questions

1. **For Framework Foundations:**

   - Which patterns do frameworks use internally?
   - How does React use patterns?
   - How does Vue use patterns?

2. **For Vanilla JavaScript:**

   - When should you use design patterns?
   - How do patterns improve code quality?
   - What are the costs of patterns?

3. **Deeper Understanding:**
   - Can you combine patterns?
   - How do you choose the right pattern?
   - What are anti-patterns?

---

## Section 18: Module Systems & Code Organization

### The Problem

You're building a large application with hundreds of files. How do you:

- Organize code into logical units
- Manage dependencies
- Avoid naming conflicts
- Enable reuse across projects
- Build for production

**Module systems solve these problems.**

---

### Exploration Questions

#### Module Fundamentals

**Scenario 1: ES Modules vs CommonJS**

```javascript
// ES Modules (ESM)
import {something} from "./module.js";
export const value = 42;

// CommonJS (CJS)
const something = require("./module");
module.exports = {value: 42};
```

**Explore:**

- What's the difference between ESM and CJS?
- Why does ESM exist if we have CJS?
- Can you use both in the same project?
- What are the trade-offs?

**Scenario 2: Named vs Default Exports**

```javascript
// Named exports
export const a = 1;
export const b = 2;
import { a, b } from './module.js';

// Default export
export default function() {}
import whatever from './module.js';

// Can you mix both?
export const a = 1;
export default function() {}
import fn, { a } from './module.js';
```

**Explore:**

- When should you use named exports?
- When should you use default exports?
- Can you have multiple default exports?
- What are the trade-offs?

**Scenario 3: Dynamic Imports**

```javascript
// Static import (loaded at parse time)
import {something} from "./module.js";

// Dynamic import (loaded at runtime)
const module = await import("./module.js");
```

**Explore:**

- What are dynamic imports?
- When should you use them?
- How do they enable code splitting?
- What do they return?

#### Code Organization

**Scenario 4: Project Structure**

```
/src
  /features
    /auth
      - login.js
      - register.js
      - auth-api.js
    /dashboard
      - dashboard.js
      - widgets.js
  /shared
    /utils
    /components
  /api
  - index.js
```

**Explore:**

- How should you organize code?
- Feature-based vs type-based structure?
- Where do shared utilities go?
- How do you prevent circular dependencies?

**Scenario 5: Barrel Files**

```javascript
// features/auth/index.js
export {login} from "./login.js";
export {register} from "./register.js";
export {authApi} from "./auth-api.js";

// Now you can:
import {login, register} from "./features/auth";
// Instead of:
import {login} from "./features/auth/login";
import {register} from "./features/auth/register";
```

**Explore:**

- What are barrel files?
- When are they useful?
- What are the drawbacks?
- How do they affect tree-shaking?

---

### Master Exercise: Module Systems

#### Part 1: Build Module Loader

Create a simple module loader:

```javascript
class ModuleLoader {
  constructor() {
    this.cache = new Map();
  }

  load(path) {
    // Load module from path
    // Cache result
    // Handle dependencies
    // Return exports
  }

  resolve(path) {
    // Resolve module path
    // Handle relative paths
    // Handle node_modules lookup
  }

  invalidate(path) {
    // Remove from cache
  }
}

// Test:
const loader = new ModuleLoader();

const module = loader.load("./myModule.js");
console.log(module.exports);

// Second load uses cache
const module2 = loader.load("./myModule.js");
console.log(module === module2); // true
```

**Requirements:**

- Load modules from path
- Cache loaded modules
- Resolve dependencies
- Handle circular dependencies
- Support both ESM and CJS syntax

#### Part 2: Organize Large Application

Given this messy structure, reorganize it:

```
/src
  - everything-in-one-file.js (5000 lines!)
```

**Reorganize into:**

```
/src
  /features
  /shared
  /api
  /utils
```

**Requirements:**

- Logical feature separation
- Shared code in appropriate places
- Clear dependency graph
- No circular dependencies
- Scalable structure

#### Part 3: Build Dependency Graph

Create a tool to visualize module dependencies:

```javascript
class DependencyGraph {
  constructor() {
    this.graph = new Map();
  }

  addModule(path, dependencies) {
    // Add module and its dependencies
  }

  getDependencies(path) {
    // Get direct dependencies
  }

  getAllDependencies(path) {
    // Get all dependencies (recursive)
  }

  getDependents(path) {
    // Get modules that depend on this
  }

  findCircular() {
    // Find circular dependencies
  }

  visualize() {
    // Generate visual graph
  }
}

// Test:
const graph = new DependencyGraph();

graph.addModule("/app.js", ["/utils.js", "/api.js"]);
graph.addModule("/utils.js", []);
graph.addModule("/api.js", ["/utils.js"]);

console.log(graph.findCircular()); // []

graph.addModule("/api.js", ["/utils.js", "/app.js"]); // Circular!
console.log(graph.findCircular()); // ['/app.js', '/api.js']
```

**Requirements:**

- Build dependency graph
- Find circular dependencies
- Find unused modules
- Visualize dependencies
- Export graph data

---

### Reflection Questions

1. **For Framework Foundations:**

   - How do frameworks organize code?
   - What module system do frameworks use?
   - How do frameworks handle dependencies?

2. **For Vanilla JavaScript:**

   - How should you structure large projects?
   - How do you prevent spaghetti code?
   - How do you make code reusable?

3. **Deeper Understanding:**
   - What are module bundlers?
   - How does tree-shaking work?
   - What is code splitting?

---

## 🎓 Congratulations!

You've completed **ALL 9 PARTS** of the Deep JavaScript Self-Mastery Workbook!

### What You've Mastered

✅ **Part 1: Closures & Functional Patterns** - Private state, composition, memoization  
✅ **Part 2: Execution Context & `this` Binding** - How JavaScript executes code  
✅ **Part 3: Prototypes & Object Systems** - Inheritance and OOP  
✅ **Part 4: Async Mastery** - Promises, async/await, control flow  
✅ **Part 5: Event Loop & Scheduling** - Concurrency and timing  
✅ **Part 6: Metaprogramming with Proxies** - Intercepting and customizing behavior  
✅ **Part 7: Iterators & Generators** - Lazy evaluation and custom iteration  
✅ **Part 8: Memory & Performance** - Writing fast, leak-free code  
✅ **Part 9: Architectural Patterns** - Design patterns and code organization

### You Now Have Deep JavaScript Mastery

You understand JavaScript at a level where:

- ✅ Framework source code makes sense
- ✅ Complex patterns are obvious
- ✅ Debugging is intuitive
- ✅ Performance issues are identifiable
- ✅ Architecture decisions are informed

### What's Next?

#### Option 1: JavaScript Framework Foundations

Continue to the **"JavaScript Framework Foundations"** workbook to:

- Build your own reactivity system
- Build your own virtual DOM
- Build your own state manager
- Build your own router
- Build your own complete framework

Then master any framework (React, Vue, Svelte) in days.

#### Option 2: Build With Vanilla JavaScript

You now have everything needed to build complex applications without frameworks:

- Build your own abstractions
- Create reusable libraries
- Publish npm packages
- Contribute to open source

### Keep Growing

- **Build projects** - Apply what you learned
- **Read source code** - React, Vue, Lodash, etc.
- **Teach others** - Best way to solidify knowledge
- **Contribute to open source** - Give back to the community
- **Stay curious** - Keep exploring and asking "why?"

---

**You're now a JavaScript master. The possibilities are endless. Go build amazing things! 🚀**
