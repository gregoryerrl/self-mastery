# Advanced JavaScript Self-Mastery Workbook

---

## Table of Contents

- [💻 Prerequisites](#-prerequisites)
- [How to Use This Workbook](#how-to-use-this-workbook)
- [🌱 Philosophy Behind This Workbook](#-philosophy-behind-this-workbook)

### 🟢 FOUNDATIONS (Advanced Fundamentals)

- [Section 1: Advanced Functions & Closures](#section-1-advanced-functions--closures)
- [Section 2: The `this` Keyword & Execution Context](#section-2-the-this-keyword--execution-context)
- [Section 3: Prototypes & Inheritance](#section-3-prototypes--inheritance)
- [Section 4: Classes & Object-Oriented Patterns](#section-4-classes--object-oriented-patterns)

### 🟡 FUNCTIONAL & ASYNC (Programming Paradigms)

- [Section 5: Functional Programming in JavaScript](#section-5-functional-programming-in-javascript)
- [Section 6: Advanced Async Patterns](#section-6-advanced-async-patterns)
- [Section 7: Event Loop & Concurrency Model](#section-7-event-loop--concurrency-model)
- [Section 8: Modules & Code Organization](#section-8-modules--code-organization)

### 🔵 METAPROGRAMMING (Advanced Language Features)

- [Section 9: Proxies, Reflect & Metaprogramming](#section-9-proxies-reflect--metaprogramming)
- [Section 10: Symbols, Iterators & Generators](#section-10-symbols-iterators--generators)
- [Section 11: Error Handling & Debugging Mastery](#section-11-error-handling--debugging-mastery)
- [Section 12: Memory Management & Performance](#section-12-memory-management--performance)

### 🔴 PATTERNS & ARCHITECTURE (Building Large Applications)

- [Section 13: Design Patterns in JavaScript](#section-13-design-patterns-in-javascript)
- [Section 14: Advanced DOM & Browser APIs](#section-14-advanced-dom--browser-apis)
- [Section 15: Testing Patterns & Test-Driven Development](#section-15-testing-patterns--test-driven-development)
- [Section 16: Building Scalable Applications](#section-16-building-scalable-applications)

### ⚫ MASTERY (Real-World Application)

- [Section 17: Final Mastery Project - Build a Complete Application](#section-17-final-mastery-project)
- [Next Steps: Framework Foundations & Beyond](#next-steps-framework-foundations--beyond)

---

## 💻 Prerequisites

Before starting this workbook, you **must have completed**:

### ✅ Required Workbooks

1. **"HTML-CSS-JavaScript Self-Mastery Workbook"** - Comfortable with:

   - All JavaScript fundamentals
   - DOM manipulation and events
   - Basic async/await and Promises
   - ES6+ syntax
   - Array methods (map, filter, reduce)
   - Basic scope and closures

2. **"Development Environment & Servers Mastery Workbook"** - Know:
   - Terminal usage and Git
   - Node.js and npm
   - Module systems basics
   - Running local development servers
   - Basic debugging with browser DevTools

### ✅ Technical Skills Required

- Can build interactive web applications
- Comfortable breaking down complex problems
- Can read and understand others' code
- Can use console.log and browser DevTools for debugging
- Can run commands in terminal

### ⚠️ This is NOT a Beginner Workbook

If you're not comfortable with basic JavaScript, **stop here**. Complete the foundational workbook first.

---

## How to Use This Workbook

This document is **not a textbook**. It will not hand you the answers.

Instead, it gives you the **right questions to ask yourself** — questions every advanced JavaScript developer must be able to answer to build professional applications.

### Here's how to use it effectively:

#### 1. **Ask Yourself First**

- Before looking things up, try to explain the answer in your own words
- If you can't, that's fine — it means you found a gap in your knowledge
- If a new question pops up that's not in here, write it down and explore it

#### 2. **Leverage All Resources**

- Use Google, Stack Overflow, and ChatGPT to research
- Read documentation, articles, and examples
- Look at library source code (Lodash, React, Vue)
- Find a way to practice and produce results

#### 3. **Learn by Doing**

- Each section has project exercises
- Completing these exercises forces you to practice and discover answers naturally
- **Don't skip them** — doing is how you'll turn theory into mastery

#### 4. **Reflect and Explain**

- After finding an answer, try teaching it back:
  - Explain to a friend or fellow developer
  - Write notes in your own words
  - Create blog posts or GitHub READMEs
- If you can explain clearly, you've truly learned it

#### 5. **Iterate and Improve**

- Revisit questions regularly
- As you grow, your answers will become deeper and more precise

---

## 🌱 Philosophy Behind This Workbook

### This is a **"find the answer within yourself"** document — the advanced JavaScript version.

- The **questions** represent the knowledge every advanced JavaScript developer must internalize

- **Be curious** → always ask "why does this work this way?"

- The **resources** (Google, Stack Overflow, ChatGPT) are your tools — but the true goal is that **the understanding lives inside you**, not just in your search history

- The **exercises** are opportunities to struggle, explore, and discover

- **Expect mistakes** → debugging is how you learn

- **Reflect** → explain new concepts in your own words

By the time you've asked and answered everything here — and built the exercises — you won't just "know advanced JavaScript." **You'll understand it so deeply that you can build large-scale applications, create your own frameworks, and master any JavaScript codebase with confidence.**

---

# 🟢 FOUNDATIONS (Advanced Fundamentals)

---

## Section 1: Advanced Functions & Closures

### Function Fundamentals Deep Dive

- What is a function in JavaScript (not just "a block of code")?
- What are the different ways to create functions, and how do they differ?
- What is function hoisting, and why does it exist?
- What is the difference between function declarations and function expressions?
- What are anonymous functions, and when should you use them?
- What are arrow functions, and how do they differ from regular functions?
- What is the `arguments` object, and why is it array-like but not an array?
- What are rest parameters, and how do they differ from `arguments`?

### Closures Deep Dive

- What is a closure (in your own words, not a memorized definition)?
- How do closures work in memory?
- What is lexical scope, and how does it enable closures?
- What is the relationship between scope chains and closures?
- When does a closure get created?
- How long does a closure persist in memory?
- What are practical uses of closures?
- What is the module pattern, and how does it use closures?
- How do closures enable data privacy?
- What are the memory implications of closures?

### Higher-Order Functions

- What is a higher-order function?
- What is the difference between a callback and a higher-order function?
- How do you write a function that returns a function?
- How do you write a function that accepts a function as an argument?
- What is function composition?
- What is currying, and how is it different from partial application?
- What is partial application?
- How do you implement curry from scratch?
- What are practical uses of currying and partial application?

### Function Context & Binding

- What is the call stack?
- What is an execution context?
- What is a lexical environment?
- What is variable environment vs lexical environment?
- What is the scope chain lookup process?
- How do closures affect the scope chain?

### Advanced Function Patterns

- What is the IIFE (Immediately Invoked Function Expression) pattern?
- Why would you use an IIFE?
- What is the revealing module pattern?
- How do you implement memoization?
- What is debouncing vs throttling?
- How do you implement function pipelining?
- What are generator functions (basic understanding)?

### Exercise 1: Build a Module System

Create a counter module with private state using closures.

**Requirements:**

- Private `count` variable that can't be accessed directly
- Public methods: `increment()`, `decrement()`, `getCount()`, `reset()`
- Each instance should have its own independent state
- Test that you can't access `count` from outside

### Exercise 2: Build a TODO Manager Module

Create a TODO manager with private state and helper functions.

**Requirements:**

- Private array of todos
- Private `nextId` counter
- Private helper function `findById(id)`
- Public methods: `addTodo(text)`, `toggleTodo(id)`, `deleteTodo(id)`, `getTodos()`, `getStats()`
- Return copies of data to prevent external mutation
- Initialize with optional starting todos

**Bonus challenges:**

- Add `updateTodo(id, text)` method
- Add `clearCompleted()` method
- Add `filterTodos(filter)` for 'all', 'active', 'completed'
- Add undo/redo functionality

### Exercise 3: Implement Curry and Partial Application

Build your own `curry` and `partial` functions from scratch.

**Requirements:**

- `curry(fn)` - should allow calling function arguments one at a time
- Should work with any number of arguments
- Should work with different calling patterns: `fn(1)(2)(3)`, `fn(1, 2)(3)`, `fn(1)(2, 3)`
- `partial(fn, ...fixedArgs)` - should fix some arguments and return new function
- Test both with real use cases

**Bonus:**

- Implement `compose` (right-to-left function composition)
- Implement `pipe` (left-to-right function composition)
- Build a data transformation pipeline using these functions

### Exercise 4: Build Memoization

Implement memoization for expensive computations.

**Requirements:**

- Basic `memoize(fn)` that caches results
- Cache should be stored in closure
- Use function arguments as cache key
- Test with Fibonacci function
- Measure performance improvement

**Bonus:**

- Add cache size limit
- Add TTL (time-to-live) for cache entries
- Implement `memoizeOne` that only caches last result
- Handle recursive functions properly

### Exercise 5: Implement Debounce and Throttle

Build debounce and throttle functions from scratch.

**Requirements:**

- `debounce(fn, delay)` - delays execution until after delay has passed since last call
- `throttle(fn, interval)` - ensures function is called at most once per interval
- Both should preserve `this` context
- Test with search input (debounce) and scroll event (throttle)

**Bonus:**

- Add `leading` and `trailing` options to debounce
- Add cancellation functionality
- Build a real form with debounced validation

### Exercise 6: Build an Event Emitter

Create a pub/sub system using closures.

**Requirements:**

- Private storage for event listeners
- `on(eventName, callback)` - subscribe to event
- `emit(eventName, ...args)` - trigger all listeners for event
- `once(eventName, callback)` - listener that fires only once
- `off(eventName, callback)` - unsubscribe
- `on()` should return unsubscribe function

**Bonus:**

- Add wildcard event support
- Add event namespacing
- Add max listener warnings
- Handle async listeners with error catching

### Exercise 7: Build a State Management System

Combine closures, higher-order functions, and pub/sub to create Redux-like state manager.

**Requirements:**

- Private state variable
- Private listeners array
- `getState()` - returns current state
- `subscribe(listener)` - returns unsubscribe function
- `dispatch(action)` - updates state via reducer, notifies listeners
- Reducer function that returns new state based on action

**Bonus:**

- Add middleware support
- Add selector pattern for derived state
- Add time-travel debugging
- Build complete todo app using this store

---

## Section 2: The `this` Keyword & Execution Context

### Understanding `this`

- What is `this` in JavaScript?
- Why does `this` exist, and what problem does it solve?
- How is `this` determined (the 4 binding rules)?
- What is implicit binding?
- What is explicit binding?
- What is new binding?
- What is default binding?
- What is lexical `this` (arrow functions)?
- How does `this` work in strict mode vs non-strict mode?
- What is the order of precedence for `this` binding rules?

### Context Binding Methods

- How does `call()` work?
- How does `apply()` work?
- How does `bind()` work?
- What's the difference between `call()` and `apply()`?
- When would you use `bind()` over `call()/apply()`?
- Can you bind `this` multiple times?
- How do arrow functions handle `this` differently?
- What is hard binding?

### Common `this` Pitfalls

- Why does `this` become `undefined` in callbacks?
- How do you preserve `this` in event handlers?
- How do you fix `this` in nested functions?
- How do you handle `this` in array methods?
- What is the `this` value in setTimeout/setInterval?
- How do you debug `this` issues?

### Arrow Functions and `this`

- How do arrow functions capture `this`?
- When should you use arrow functions?
- When should you NOT use arrow functions?
- What is lexical scoping of `this`?
- How do arrow functions behave as methods?
- Can you use `call`/`apply`/`bind` with arrow functions?

### Execution Context Deep Dive

- What is an execution context?
- What are the three types of execution contexts?
- What is the execution stack (call stack)?
- What happens when a function is invoked?
- What is the creation phase vs execution phase?
- What is the Variable Environment?
- What is the Lexical Environment?
- What is the `this` binding?
- How does the scope chain work?

### Exercise 1: Identify `this` in Different Scenarios

Create a test file with 15+ different scenarios of `this` usage:

- Global context
- Object methods
- Method assigned to variable
- Callbacks
- Arrow functions in objects
- Constructors
- Classes
- Nested functions
- Event handlers
- Array methods

For each scenario:

1. Predict what `this` will be BEFORE running
2. Run code and verify
3. Explain WHY `this` is that value
4. Draw the execution context

### Exercise 2: Implement `call`, `apply`, and `bind`

Build your own versions from scratch.

**Requirements:**

- `Function.prototype.myCall(context, ...args)`
- `Function.prototype.myApply(context, argsArray)`
- `Function.prototype.myBind(context, ...fixedArgs)`
- All should handle null/undefined context
- All should preserve return values
- Test with various functions and contexts

### Exercise 3: Fix `this` Problems

You'll be given broken code where `this` is wrong. Fix using multiple approaches:

**Problem 1:** Lost context in forEach callback  
**Problem 2:** Lost context in event handler  
**Problem 3:** Lost context in setTimeout  
**Problem 4:** Method extraction breaking context

For each problem, provide at least 3 different fixes:

- Using arrow functions
- Using bind
- Using explicit context parameter
- Other creative solutions

### Exercise 4: Build a Method Chaining System

Create a QueryBuilder class with fluent interface.

**Requirements:**

- All methods return `this` for chaining
- `select(...columns)` - choose columns
- `where(column, operator, value)` - add conditions
- `orderBy(column, direction)` - add sorting
- `limit(count)` - limit results
- `build()` - generate SQL string
- Should be able to chain: `.select('id', 'name').where('age', '>', 18).orderBy('name').limit(10)`

**Bonus:**

- Add `join()` method
- Add `groupBy()` and `having()`
- Add `orWhere()` for OR conditions

### Exercise 5: Build an Event Handler System

Create a system that correctly handles `this` in event callbacks.

**Requirements:**

- Register handlers with optional context binding
- Emit events and call handlers with correct `this`
- Support removing handlers
- Support `once` handlers
- Handle async handlers with error catching

---

## Section 3: Prototypes & Inheritance

### Prototype Fundamentals

- What is a prototype in JavaScript?
- What is the prototype chain?
- What is `__proto__` vs `prototype`?
- How does property lookup work on the prototype chain?
- What is `Object.prototype`?
- What methods exist on `Object.prototype`?
- How do you check if a property exists on an object vs its prototype?
- What is `hasOwnProperty()` and when do you use it?
- What is `Object.getPrototypeOf()`?
- What is `Object.setPrototypeOf()`?
- Should you modify built-in prototypes? Why or why not?

### Constructor Functions

- What is a constructor function?
- What happens when you use the `new` keyword?
- What are the 4 steps of `new`?
- How do you add methods to constructor function instances?
- What is the difference between adding methods in constructor vs on prototype?
- What are the performance implications of each approach?
- How do you implement inheritance with constructor functions?
- What is `Object.create()` and how does it work?

### Prototype Inheritance Patterns

- How do you create inheritance chains?
- What is the classical inheritance pattern?
- What is the parasitic combination inheritance?
- What are the problems with each pattern?
- How do you call parent constructor from child?
- How do you override parent methods?
- How do you call parent methods from overridden child methods?
- What is the difference between inheritance and composition?

### Modern Prototype Methods

- What is `Object.create()`?
- What is `Object.setPrototypeOf()`?
- What is `Object.getPrototypeOf()`?
- What is `instanceof` and how does it work?
- What is `isPrototypeOf()`?
- How do you create objects with no prototype?
- What are the use cases for prototype-less objects?

### Exercise 1: Build Constructor Functions with Prototypes

Create an `Animal` constructor and `Dog`, `Cat` subclasses.

**Requirements:**

- `Animal` has `name` and `age` properties
- `Animal.prototype` has `eat()` and `sleep()` methods
- `Dog` inherits from `Animal`
- `Dog.prototype` has `bark()` method
- `Cat` inherits from `Animal`
- `Cat.prototype` has `meow()` method
- Test that dogs can `eat()`, `sleep()`, and `bark()`
- Test that cats can `eat()`, `sleep()`, and `meow()`
- Verify prototype chain is correct

### Exercise 2: Implement `instanceof` and `Object.create()`

Build these from scratch to understand how they work.

**Requirements:**

- `myInstanceOf(obj, Constructor)` - check if obj is instance of Constructor
- Walk prototype chain to check
- `myObjectCreate(proto)` - create object with specified prototype
- Handle null prototype case
- Test both implementations thoroughly

### Exercise 3: Build a Class Hierarchy

Create a vehicle hierarchy without using `class` keyword.

**Requirements:**

- `Vehicle` base constructor
- `Car` and `Motorcycle` inherit from `Vehicle`
- `ElectricCar` inherits from `Car`
- Each level adds properties and methods
- Use proper prototype delegation
- Implement method overriding
- Call parent methods from child methods

### Exercise 4: Fix Prototype Problems

You'll be given broken inheritance code. Fix the issues:

**Problem 1:** Methods defined in constructor (memory waste)  
**Problem 2:** Broken prototype chain  
**Problem 3:** Constructor property missing  
**Problem 4:** Shared state between instances

---

## Section 4: Classes & Object-Oriented Patterns

### ES6 Classes

- What is the `class` syntax, and what does it compile to?
- How do classes relate to constructor functions and prototypes?
- What is a class constructor?
- How do you define instance methods in a class?
- How do you define static methods?
- What are getter and setter methods?
- How do you define private fields (#)?
- What are static fields?

### Inheritance with Classes

- How does `extends` work?
- What is `super()` and when must you call it?
- How do you override parent methods?
- How do you call parent methods from child?
- What is the difference between `super()` and `super.method()`?
- Can you extend built-in classes (Array, Error)?

### OOP Principles in JavaScript

- What is encapsulation, and how do you achieve it?
- What is inheritance, and when should you use it?
- What is polymorphism, and how does it work in JavaScript?
- What is abstraction?
- When should you use composition over inheritance?
- What are mixins, and how do you implement them?

### Design Patterns with Classes

- What is the Singleton pattern?
- What is the Factory pattern?
- What is the Builder pattern?
- What is the Observer pattern?
- When should you use each pattern?

### Exercise 1: Build a Shape Class Hierarchy

Create geometric shapes using classes.

**Requirements:**

- Base `Shape` class with abstract methods
- `Rectangle`, `Circle`, `Triangle` extend `Shape`
- Each has `area()` and `perimeter()` methods
- Add `describe()` method that uses polymorphism
- Add static `compare(shape1, shape2)` to compare areas
- Use getters for computed properties
- Implement `toString()` for nice printing

### Exercise 2: Implement Private Fields

Build a `BankAccount` class with true privacy.

**Requirements:**

- Private `#balance` field
- Private `#transactions` array
- Public methods: `deposit()`, `withdraw()`, `getBalance()`
- Prevent direct access to balance
- Prevent negative balances
- Track all transactions privately
- Add getters for computed values (total deposits, total withdrawals)

### Exercise 3: Build Mixins

Create reusable behavior that can be mixed into classes.

**Requirements:**

- `Timestampable` mixin - adds `createdAt`, `updatedAt`
- `Serializable` mixin - adds `toJSON()`, `fromJSON()`
- `Validatable` mixin - adds validation methods
- Apply mixins to different classes
- Ensure mixins don't conflict

### Exercise 4: Factory Pattern

Build a UI component factory.

**Requirements:**

- `ComponentFactory` class
- Register different component types
- Create components by name
- Each component has `render()` method
- Support component configuration
- Implement plugin system for adding new types

---

## Section 5: Functional Programming in JavaScript

### FP Fundamentals

- What is functional programming?
- What are pure functions?
- What is immutability?
- What are side effects?
- What is referential transparency?
- Why use functional programming?
- What are the benefits and tradeoffs?

### Immutability

- How do you work with immutable data?
- How do you update objects immutably?
- How do you update arrays immutably?
- How do you update nested structures immutably?
- What is structural sharing?
- What libraries help with immutability (Immer, Immutable.js)?

### Function Composition

- What is function composition?
- How do you compose functions?
- What is point-free style?
- What is function piping?
- How do you handle errors in composed functions?
- What is the Reader monad (conceptual)?

### Higher-Order Functions Deep Dive

- How does `map` work internally?
- How does `filter` work internally?
- How does `reduce` work internally?
- When should you use each?
- How do you chain array methods efficiently?
- What is transducing?

### Declarative vs Imperative

- What is declarative code?
- What is imperative code?
- How do you convert imperative loops to declarative operations?
- What are the readability tradeoffs?

### Exercise 1: Implement Core FP Functions

Build from scratch: `map`, `filter`, `reduce`, `compose`, `pipe`.

**Requirements:**

- Work with arrays
- Pure functions only
- Handle edge cases
- Test thoroughly
- Compare performance to native methods

### Exercise 2: Immutable Data Structures

Build functions for immutable updates.

**Requirements:**

- `updateObject(obj, path, value)` - update nested object immutably
- `updateArray(arr, index, value)` - update array immutably
- `addToArray(arr, item)` - add to array immutably
- `removeFromArray(arr, index)` - remove from array immutably
- Support deep nesting
- Don't mutate originals

### Exercise 3: Build a Data Transformation Pipeline

Process complex data using only pure functions.

**Requirements:**

- Load user data (array of objects)
- Filter by criteria
- Map to new shape
- Sort by multiple fields
- Group by category
- Calculate aggregates
- All using function composition
- No loops, no mutations

### Exercise 4: Implement Curried Utility Library

Build a lodash-like library with curried functions.

**Requirements:**

- All functions are curried
- Support partial application
- Include: `map`, `filter`, `find`, `groupBy`, `sortBy`, `pluck`
- Enable easy composition
- Test with real data transformations

---

## Section 6: Advanced Async Patterns

### Promise Internals

- How do Promises work internally?
- What are the Promise states?
- What is the microtask queue?
- How do you create a Promise from scratch?
- What is Promise chaining?
- How does `.then()` return a new Promise?
- What is Promise.resolve() and Promise.reject()?
- How do you handle errors in Promise chains?

### Async/Await Deep Dive

- How does async/await work under the hood?
- What does `async` function return?
- What does `await` actually do?
- How do you handle errors with async/await?
- Can you use await outside async functions?
- What is top-level await?
- How do you handle multiple async operations?

### Promise Combinators

- What is Promise.all()?
- What is Promise.race()?
- What is Promise.allSettled()?
- What is Promise.any()?
- When do you use each?
- How do you implement these from scratch?

### Advanced Async Patterns

- What is sequential vs parallel execution?
- How do you batch async operations?
- How do you implement retry logic?
- How do you implement timeout?
- How do you cancel async operations?
- What is the AbortController?
- How do you handle rate limiting?
- What is request deduplication?

### Exercise 1: Implement Promise from Scratch

Build your own Promise implementation.

**Requirements:**

- Support states: pending, fulfilled, rejected
- Implement `.then(onFulfilled, onRejected)`
- Implement `.catch(onRejected)`
- Implement `.finally(onFinally)`
- Handle promise chaining
- Handle async resolution
- Pass Promise A+ spec tests

### Exercise 2: Implement Promise Combinators

Build `Promise.all`, `Promise.race`, `Promise.allSettled`, `Promise.any` from scratch.

**Requirements:**

- Match native behavior exactly
- Handle edge cases
- Work with any thenable
- Test thoroughly

### Exercise 3: Build Async Control Flow

Create utilities for managing async operations.

**Requirements:**

- `retry(fn, attempts, delay)` - retry with exponential backoff
- `timeout(promise, ms)` - timeout wrapper
- `sequential(tasks)` - run async tasks in sequence
- `parallel(tasks, limit)` - run with concurrency limit
- `waterfall(tasks)` - pass result to next task
- Test with real async operations

### Exercise 4: Build an Async Queue

Implement a queue that processes items with concurrency control.

**Requirements:**

- Add items to queue
- Process with max concurrency
- Handle errors without stopping queue
- Support priority items
- Emit events for progress
- Support pause/resume
- Build real example (image processor, API batch requests)

---

## Section 7: Event Loop & Concurrency Model

### Event Loop Fundamentals

- What is the event loop?
- What is the call stack?
- What is the task queue (macrotask queue)?
- What is the microtask queue?
- What is the difference between macrotasks and microtasks?
- What order does the event loop process tasks?
- How does setTimeout work with the event loop?
- How does setInterval work?
- What is requestAnimationFrame?
- What is requestIdleCallback?

### Call Stack

- What is the call stack?
- What happens when stack overflows?
- How do you debug call stack issues?
- What is tail call optimization?
- Does JavaScript have tail call optimization?

### Task Queues

- What goes into the macrotask queue?
- What goes into the microtask queue?
- Which has higher priority?
- What are examples of each?
- How do you visualize the queue?

### Concurrency Patterns

- How do you achieve concurrency in single-threaded JavaScript?
- What are Web Workers?
- When should you use Web Workers?
- How do you communicate with Web Workers?
- What is the difference between concurrency and parallelism?

### Exercise 1: Event Loop Predictions

Given complex code with setTimeout, Promises, async/await, predict execution order.

**Requirements:**

- Create 10+ scenarios
- Predict output order BEFORE running
- Run and verify
- Explain WHY that order
- Include: setTimeout(0), Promise, queueMicrotask, async/await

### Exercise 2: Visualize the Event Loop

Build a visual simulator of the event loop.

**Requirements:**

- Show call stack
- Show task queue
- Show microtask queue
- Step through code execution
- Highlight what's happening at each step
- Use real JavaScript to demonstrate

### Exercise 3: Optimize with Batching

Prevent UI blocking with proper event loop usage.

**Requirements:**

- Process large array (10,000+ items)
- Use requestIdleCallback for non-critical work
- Use requestAnimationFrame for visual updates
- Batch operations to prevent blocking
- Show progress without freezing
- Measure and display performance

### Exercise 4: Build a Task Scheduler

Create a scheduler that respects event loop priorities.

**Requirements:**

- Schedule tasks with different priorities
- High priority: microtasks
- Normal priority: macrotasks
- Low priority: idle tasks
- Cancel scheduled tasks
- Handle errors without crashing scheduler

---

## Section 8: Modules & Code Organization

### Module Systems

- What are modules and why do we need them?
- What is the difference between CommonJS and ES Modules?
- How does `require()` work?
- How does `import/export` work?
- What is the difference between default and named exports?
- Can you mix default and named exports?
- What is dynamic import?
- What is tree-shaking?
- How do circular dependencies work?
- How do you avoid circular dependencies?

### Module Patterns

- What is the Module pattern?
- What is the Revealing Module pattern?
- What is the Singleton pattern with modules?
- How do you create private module variables?
- How do you initialize modules?

### Code Organization

- How do you structure large applications?
- What is feature-based vs layer-based structure?
- How do you organize by domain?
- When should code be split into modules?
- How do you manage dependencies between modules?
- What is dependency injection?

### Exercise 1: Build Both Module Systems

Create the same library using both CommonJS and ES Modules.

**Requirements:**

- Build a utility library
- Export using `module.exports`
- Export using `export`
- Support both default and named exports
- Show how to import each
- Understand tradeoffs

### Exercise 2: Implement a Module Loader

Build a simple module loader from scratch.

**Requirements:**

- Load modules by path
- Cache loaded modules
- Resolve dependencies
- Handle circular dependencies
- Support both sync and async loading
- Implement simple `require()` function

### Exercise 3: Organize a Large Application

Structure a todo application with proper module organization.

**Requirements:**

- Separate concerns: data, UI, business logic
- Use dependency injection
- Implement module boundaries
- No circular dependencies
- Easy to test each module
- Easy to add new features

### Exercise 4: Build a Plugin System

Create an extensible application with plugins.

**Requirements:**

- Core application with minimal features
- Plugin API for extending
- Plugins can register routes, components, actions
- Plugins can depend on other plugins
- Plugins load dynamically
- Build 3+ example plugins

---

## Section 9: Proxies, Reflect & Metaprogramming

### Proxy Fundamentals

- What is a Proxy?
- What are proxy traps?
- What operations can you intercept?
- What is the Reflect API?
- Why use Reflect with Proxy?
- What are the 13 proxy traps?
- What is a revocable proxy?

### Proxy Use Cases

- How do you use Proxy for validation?
- How do you create readonly objects with Proxy?
- How do you implement data binding with Proxy?
- How do you track property access?
- How do you create observable objects?
- How does Vue 3 use Proxy for reactivity?

### Reflect API

- What is the Reflect API?
- What methods does Reflect provide?
- Why use Reflect instead of direct operations?
- How do Reflect methods relate to proxy traps?

### Metaprogramming

- What is metaprogramming?
- How do you intercept object operations?
- How do you create custom behavior for operators?
- What are the limitations of Proxy?

### Exercise 1: Build Validation with Proxy

Create objects that validate on property assignment.

**Requirements:**

- Define schema with rules
- Throw errors on invalid assignments
- Support types: string, number, boolean, email, range
- Support custom validators
- Test thoroughly

### Exercise 2: Build Observable Objects

Implement reactive data binding like Vue.

**Requirements:**

- Wrap objects with Proxy
- Track property access
- Trigger callbacks on changes
- Support nested objects
- Support arrays
- Handle deep observation

### Exercise 3: Create Private Properties

Use Proxy to enforce truly private properties.

**Requirements:**

- Properties starting with `_` are private
- Throw error when accessing private props from outside
- Allow access from class methods
- Support getters/setters
- Test access control

### Exercise 4: Build a Query Builder with Proxy

Create a fluent query builder using Proxy magic.

**Requirements:**

- Any method name becomes part of query
- `db.users.where.age.gt(18).select('name').limit(10)`
- Use Proxy to intercept property access
- Build actual query object
- Execute and return results

---

## Section 10: Symbols, Iterators & Generators

### Symbols

- What are Symbols?
- Why do Symbols exist?
- How do you create Symbols?
- What is Symbol.for()?
- What are well-known Symbols?
- How do you use Symbols for private properties?
- What is Symbol.iterator?
- What other built-in Symbols exist?

### Iterators

- What is an iterator?
- What is the iterator protocol?
- How do you make an object iterable?
- What is Symbol.iterator?
- How does `for...of` work?
- What is the difference between iterable and iterator?
- How do you create custom iterators?

### Generators

- What are generator functions?
- What is `function*` syntax?
- What is the `yield` keyword?
- How do generators work internally?
- What is the difference between `yield` and `return`?
- How do you pass values into generators?
- What is `generator.next(value)`?
- What is `yield*` for delegation?
- Can generators be async?
- What are async generators?

### Advanced Iteration

- How do you implement iterator methods (map, filter, take)?
- What is lazy evaluation?
- How do you create infinite sequences?
- How do you compose iterators?

### Exercise 1: Build Custom Iterables

Make various objects iterable.

**Requirements:**

- Make a Range object: `for (let n of Range(1, 10))`
- Make a Fibonacci sequence iterator
- Make a Tree data structure iterable (DFS and BFS)
- Make a custom collection iterable
- Test with `for...of`, spread operator, Array.from()

### Exercise 2: Implement Generator-Based Control Flow

Use generators for async control flow.

**Requirements:**

- Implement `run(generator)` that handles yielded promises
- Build sequential task runner
- Handle errors properly
- Compare to async/await
- Build real example (fetching paginated data)

### Exercise 3: Build Lazy Evaluation System

Create lazy iterators for data transformation.

**Requirements:**

- `lazy(array)` wraps array
- `.map(fn)` lazily maps
- `.filter(fn)` lazily filters
- `.take(n)` takes first n
- Only compute when needed
- Chain operations
- Compare performance to eager evaluation

### Exercise 4: Create Infinite Sequences

Use generators for infinite sequences.

**Requirements:**

- Fibonacci sequence
- Prime number generator
- Random number stream
- Timer/interval sequence
- Take values as needed
- Compose sequences

---

## Section 11: Error Handling & Debugging Mastery

### Error Handling Fundamentals

- What is an Error in JavaScript?
- What types of errors exist?
- What is the Error object structure?
- How do you create custom errors?
- What is the stack trace?
- How do you read stack traces?

### Try/Catch/Finally

- How does try/catch work?
- What is finally?
- Can you have try/finally without catch?
- How do you handle errors in async functions?
- What is unhandled promise rejection?
- How do you catch errors globally?

### Error Handling Patterns

- When should you throw vs return errors?
- How do you create error hierarchies?
- What is error wrapping?
- How do you add context to errors?
- What is fail-fast vs fail-safe?
- How do you handle errors in callbacks?
- How do you handle errors in promises?
- How do you handle errors in async/await?

### Debugging Techniques

- How do you use `console` effectively?
- What debugging methods exist besides `console.log`?
- How do you use browser debugger?
- What are breakpoints?
- What are conditional breakpoints?
- What are logpoints?
- How do you debug async code?
- How do you debug production code?

### Exercise 1: Build Custom Error Classes

Create error hierarchy for different error types.

**Requirements:**

- Base `AppError` class
- `ValidationError`, `NetworkError`, `AuthError` subclasses
- Each has appropriate properties
- Include error codes
- Include context data
- Stack trace preservation
- Test throwing and catching

### Exercise 2: Build Error Boundary

Create error handling wrapper for functions.

**Requirements:**

- Catch all errors from function
- Log errors properly
- Add context information
- Retry failed operations
- Fallback values
- Circuit breaker pattern
- Test with various error scenarios

### Exercise 3: Implement Advanced Debugging

Build debugging utilities.

**Requirements:**

- `trace(fn)` - logs all calls with arguments
- `time(fn)` - measures execution time
- `profile(fn)` - collects performance data
- `assert(condition, message)` - custom assertions
- `debug` namespace system
- Test with complex code

### Exercise 4: Build Error Reporting System

Create production error tracking.

**Requirements:**

- Global error handler
- Capture unhandled errors
- Capture unhandled promise rejections
- Add user context
- Add session data
- Send to backend
- Prevent duplicate reports
- Don't expose sensitive data

---

## Section 12: Memory Management & Performance

### Memory Fundamentals

- How does JavaScript memory management work?
- What is the heap?
- What is the stack?
- What is garbage collection?
- What garbage collection algorithms exist?
- What is mark-and-sweep?
- What is reference counting?

### Memory Leaks

- What is a memory leak?
- What are common causes of memory leaks?
- How do detached DOM elements cause leaks?
- How do closures cause leaks?
- How do event listeners cause leaks?
- How do you detect memory leaks?
- How do you prevent memory leaks?

### WeakMap and WeakSet

- What is WeakMap?
- What is WeakSet?
- How do they help prevent memory leaks?
- When should you use them?
- What are the limitations?

### Performance Optimization

- How do you measure performance?
- What is the Performance API?
- What is performance.now()?
- What are performance marks and measures?
- How do you profile JavaScript?
- What tools help with performance?
- What are common performance bottlenecks?

### Exercise 1: Detect Memory Leaks

Find and fix memory leaks in provided code.

**Requirements:**

- Code with multiple leak types provided
- Use Chrome DevTools memory profiler
- Take heap snapshots
- Compare snapshots
- Identify leaking objects
- Fix all leaks
- Verify fixes with profiler

### Exercise 2: Optimize Performance

Given slow code, make it fast.

**Requirements:**

- Profile original code
- Identify bottlenecks
- Optimize algorithms
- Optimize data structures
- Use caching where appropriate
- Measure improvements
- Document optimization strategies

### Exercise 3: Build Performance Monitor

Create runtime performance monitoring.

**Requirements:**

- Track function execution times
- Track memory usage
- Track DOM operations
- Detect performance regressions
- Generate performance reports
- Visualize data

### Exercise 4: Memory-Efficient Data Structures

Build data structures that minimize memory.

**Requirements:**

- Implement LRU cache with size limit
- Use WeakMap for object metadata
- Clean up resources properly
- Test memory usage
- Compare to naive implementations

---

## Section 13: Design Patterns in JavaScript

### Creational Patterns

- What is the Singleton pattern?
- What is the Factory pattern?
- What is the Abstract Factory pattern?
- What is the Builder pattern?
- What is the Prototype pattern?
- When do you use each?

### Structural Patterns

- What is the Adapter pattern?
- What is the Decorator pattern?
- What is the Proxy pattern?
- What is the Facade pattern?
- What is the Composite pattern?
- When do you use each?

### Behavioral Patterns

- What is the Observer pattern?
- What is the Strategy pattern?
- What is the Command pattern?
- What is the Iterator pattern?
- What is the State pattern?
- What is the Mediator pattern?
- When do you use each?

### JavaScript-Specific Patterns

- What is the Module pattern?
- What is the Revealing Module pattern?
- What is the Mixin pattern?
- What is the Pub/Sub pattern?
- What is the Middleware pattern?

### Exercise: Implement 5 Key Patterns

For each pattern, build from scratch:

**1. Singleton Pattern**

- Ensure only one instance exists
- Provide global access point
- Lazy initialization
- Thread-safe (if applicable)

**2. Observer Pattern**

- Subject maintains observers list
- Notify all on state change
- Observers can subscribe/unsubscribe
- Build real example (event system)

**3. Factory Pattern**

- Create objects without specifying exact class
- Support multiple product types
- Easily extensible
- Build UI component factory

**4. Strategy Pattern**

- Define family of algorithms
- Make them interchangeable
- Encapsulate each algorithm
- Build validation system with strategies

**5. Decorator Pattern**

- Add behavior to objects dynamically
- Without modifying original code
- Stack multiple decorators
- Build middleware system

---

## Section 14: Advanced DOM & Browser APIs

### DOM Performance

- What is reflow vs repaint?
- How do you minimize reflows?
- What is document fragment?
- What is requestAnimationFrame?
- How do you batch DOM operations?
- What is virtual scrolling?

### Modern DOM APIs

- What is MutationObserver?
- What is IntersectionObserver?
- What is ResizeObserver?
- What is PerformanceObserver?
- When do you use each?

### Web APIs

- What is the Fetch API?
- What is the History API?
- What is the Storage API?
- What is the Geolocation API?
- What is the Notification API?
- What is the File API?

### Advanced Event Handling

- What is event delegation deep dive?
- What is event capturing vs bubbling?
- How do you stop event propagation?
- What is preventDefault()?
- What are passive event listeners?
- How do you create custom events?

### Exercise: Build Observability System

Implement a system using observer APIs.

**Requirements:**

- Use IntersectionObserver for lazy loading
- Use MutationObserver for DOM change tracking
- Use ResizeObserver for responsive behavior
- Build real application (infinite scroll, lazy images, responsive layout)

---

## Section 15: Testing Patterns & Test-Driven Development

### Testing Fundamentals

- What are the types of tests?
- What is unit testing?
- What is integration testing?
- What is end-to-end testing?
- What is the testing pyramid?
- What is TDD?
- What are the benefits of TDD?

### Test Structure

- What is AAA (Arrange, Act, Assert)?
- How do you structure tests?
- How do you name tests?
- How do you organize test files?
- What is test coverage?

### Mocking and Spies

- What is mocking?
- What is stubbing?
- What is a spy?
- When do you use each?
- How do you mock dependencies?
- How do you mock timers?
- How do you mock fetch?

### Exercise: Build Test Framework

Create your own testing library from scratch.

**Requirements:**

- `describe()` and `it()` functions
- Assertions: `expect(value).toBe()`, `.toEqual()`, `.toThrow()`
- Setup and teardown (beforeEach, afterEach)
- Async test support
- Test reporting
- Error messages
- Use it to test your previous exercises

---

## Section 16: Building Scalable Applications

### Architecture Principles

- What is separation of concerns?
- What is single responsibility?
- What is dependency inversion?
- What is loose coupling?
- What is high cohesion?

### Application Structure

- How do you structure large applications?
- What is layered architecture?
- What is the repository pattern?
- What is the service layer?
- How do you handle state in large apps?

### Code Quality

- What is code smell?
- How do you refactor code?
- What makes code maintainable?
- How do you write self-documenting code?
- What are coding standards?

### Exercise: Build a Complete Application

Build a full-featured application using everything learned.

**Requirements:**

- User authentication
- CRUD operations
- Real-time updates
- Error handling
- Testing suite
- Performance optimization
- Memory-efficient
- Proper architecture
- Documentation

---

## Section 17: Final Mastery Project

Build a complete, production-ready JavaScript library or application.

**Choose one:**

### Option 1: JavaScript Framework

- Component system
- Reactivity system
- Router
- State management
- Build tooling

### Option 2: Testing Library

- Test runner
- Assertions
- Mocking
- Coverage reporting
- CI/CD integration

### Option 3: Build Tool

- Module bundler
- Code transformer
- Development server
- Hot module replacement
- Production optimization

### Option 4: State Management Library

- Redux-like store
- Middleware
- DevTools
- Time-travel debugging
- Persistence

**Requirements for any option:**

- Production-ready code
- Complete documentation
- Test coverage
- Performance benchmarks
- Published to npm
- Example applications
- Community contributions welcome

---

## Next Steps: Framework Foundations & Beyond

After completing this workbook, you're ready for **JavaScript Framework Foundations**.

You now understand:

- ✅ Closures (how hooks work)
- ✅ Proxies (how Vue reactivity works)
- ✅ Prototypes (how class inheritance works)
- ✅ Event loop (how async rendering works)
- ✅ Patterns (how frameworks are structured)

Next, you'll learn:

- How frameworks use these patterns
- Component architectures
- Virtual DOM and reconciliation
- Server-side rendering
- Build tools and bundlers
- Production deployment

You're now equipped to:

- **Master any JavaScript framework quickly**
- **Build large-scale applications**
- **Create your own libraries**
- **Read and contribute to framework source code**

---

**End of Advanced JavaScript Self-Mastery Workbook**
