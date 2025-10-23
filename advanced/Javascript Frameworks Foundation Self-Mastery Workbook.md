# JavaScript Framework Foundations Self-Mastery Workbook

---

## Table of Contents

- [💻 Prerequisites](#-prerequisites)
- [How to Use This Workbook](#how-to-use-this-workbook)
- [🌱 Philosophy Behind This Workbook](#-philosophy-behind-this-workbook)

### 🟢 FOUNDATIONS (Framework Fundamentals)

- [Section 1: Understanding Frameworks & Paradigms](#section-1-understanding-frameworks--paradigms)
- [Section 2: Component Architecture & Lifecycle](#section-2-component-architecture--lifecycle)
- [Section 3: Routing & Navigation Patterns](#section-3-routing--navigation-patterns)
- [Section 4: State Management Architecture](#section-4-state-management-architecture)

### 🟡 CORE PATTERNS (Essential Framework Features)

- [Section 5: Reactivity Systems](#section-5-reactivity-systems)
- [Section 6: The Hooks Pattern](#section-6-the-hooks-pattern)
- [Section 7: Forms & User Input](#section-7-forms--user-input)
- [Section 8: Data Fetching & Caching](#section-8-data-fetching--caching)

### 🔵 ADVANCED PATTERNS (Production Features)

- [Section 9: Server-Side Rendering & Hydration](#section-9-server-side-rendering--hydration)
- [Section 10: Virtual DOM & Reconciliation](#section-10-virtual-dom--reconciliation)
- [Section 11: Build Tools & Module Bundling](#section-11-build-tools--module-bundling)
- [Section 12: Security & XSS Prevention](#section-12-security--xss-prevention)

### 🔴 PRODUCTION READY (Professional Development)

- [Section 13: Testing Framework Applications](#section-13-testing-framework-applications)
- [Section 14: Accessibility & Internationalization](#section-14-accessibility--internationalization)
- [Section 15: Middleware & Interceptors](#section-15-middleware--interceptors)
- [Section 16: Error Handling & Monitoring](#section-16-error-handling--monitoring)

### ⚫ MASTERY (Framework Independence)

- [Section 17: Framework Evaluation & Selection](#section-17-framework-evaluation--selection)
- [Section 18: Building Your Own Framework](#section-18-building-your-own-framework)
- [Section 19: Building & Publishing Packages](#section-19-building--publishing-packages)
- [Next Steps: Choosing and Mastering Your Framework](#next-steps-choosing-and-mastering-your-framework)

---

## 💻 Prerequisites

Before starting this workbook, you **must have completed**:

### ✅ Required Workbooks (In Order)

1. **"HTML-CSS-JavaScript Self-Mastery Workbook"**
2. **"Development Environment & Servers Mastery Workbook"**
3. **"Advanced JavaScript Self-Mastery Workbook"** ← Most Important!

### ✅ Advanced JavaScript Mastery Required

You should deeply understand:

- Closures and higher-order functions
- The `this` keyword and execution context
- Prototypes and inheritance
- Classes and OOP patterns
- Functional programming
- Advanced async patterns (Promises, async/await)
- Event loop and concurrency
- Proxies and Reflect API
- Symbols, iterators, and generators
- Design patterns

**If you skipped Advanced JavaScript, STOP.** This workbook assumes you've mastered those concepts.

### ✅ What You Should Be Able to Do

Before starting, you should comfortably:

- Build a module system with closures
- Implement your own `call`, `apply`, `bind`
- Create inheritance with prototypes
- Build an event emitter from scratch
- Implement memoization and debouncing
- Use Proxies for reactive data
- Create custom iterators
- Handle complex async operations
- Debug memory leaks
- Implement design patterns

---

## How to Use This Workbook

This document is **not a framework tutorial**. It will not teach you React, Vue, or Svelte.

Instead, it teaches you the **universal patterns** that ALL frameworks use. Once you understand these patterns, learning any specific framework becomes trivial.

### Here's how to use it effectively:

#### 1. **Build It First (Vanilla JS)**

- Every section starts with building the pattern from scratch
- Use pure JavaScript - no frameworks
- Struggle, research, debug - this is where learning happens

#### 2. **Compare Framework Implementations**

- After building, study how React, Vue, Svelte, and Solid.js solve it
- Look for similarities and differences
- Understand why each framework made different choices

#### 3. **Ask Yourself First**

- Before looking things up, try to explain the answer in your own words
- If you can't, that's fine — it means you found a gap in your knowledge
- If a new question pops up that's not in here, write it down and explore it

#### 4. **Leverage All Resources**

- Use Google, Stack Overflow, and ChatGPT to research
- Read framework documentation (React, Vue, Svelte, Solid.js)
- Study framework source code on GitHub
- Look at how different frameworks solve the same problem

#### 5. **Reflect and Explain**

- After finding an answer, try teaching it back
- Write blog posts about what you learned
- Create GitHub repos with your implementations
- Explain to other developers

---

## 🌱 Philosophy Behind This Workbook

### This is a **"understand the machinery"** document — the framework patterns version.

- The **questions** represent the knowledge every framework developer must internalize

- **Be curious** → always ask "why does this framework do it this way?"

- The **exercises** force you to build patterns from scratch in vanilla JavaScript FIRST, then compare to frameworks

- **Expect confusion** → frameworks are complex, that's why you're learning the patterns first

- **Build, then compare** → You'll understand frameworks deeply by building their core patterns yourself

### The Learning Path

```
Problem → Build vanilla JS solution → Study React's approach → Study Vue's approach →
Study Svelte's approach → Study Solid's approach → Compare tradeoffs → Choose wisely
```

By the time you've built everything here — and compared how frameworks implement it — you won't just "use frameworks." **You'll understand them deeply enough to evaluate any framework, choose the right one for your needs, build your own framework, and create professional JavaScript packages.**

---

# 🟢 FOUNDATIONS (Framework Fundamentals)

---

## Section 1: Understanding Frameworks & Paradigms

### The Problem

You can build websites with vanilla JavaScript. You've done it. But your code is getting messy:

```javascript
// Your vanilla JS app
let todos = [];

function addTodo(text) {
  todos.push({id: Date.now(), text, done: false});
  renderTodos(); // You have to remember to call this!
}

function toggleTodo(id) {
  const todo = todos.find((t) => t.id === id);
  todo.done = !todo.done;
  renderTodos(); // And this!
}

function renderTodos() {
  const list = document.querySelector("#todo-list");
  list.innerHTML = ""; // Destroying and recreating everything!
  todos.forEach((todo) => {
    const li = document.createElement("li");
    li.textContent = todo.text;
    li.addEventListener("click", () => toggleTodo(todo.id)); // Memory leak?
    list.appendChild(li);
  });
}
```

**Problems you're facing:**

- You forget to call `renderTodos()` after state changes
- You're recreating the entire DOM on every change
- Event listeners keep piling up
- State is scattered everywhere
- Your app is hard to test

**Frameworks solve this.** But how? And at what cost?

---

### Exploration Questions

Try to answer these before researching. Then verify your understanding.

#### Understanding Why Frameworks Exist

**Scenario 1: The Forgotten Render**

```javascript
let count = 0;

function increment() {
  count++;
  // Oops, forgot to update the DOM!
  // Three hours later, you're debugging why the UI doesn't update
}
```

**Explore:**

- How would you build a system that automatically updates the DOM when data changes?
- What does it mean for data to be "reactive"?
- How do frameworks detect when data changes?
- What are the tradeoffs of automatic vs manual updates?

**Scenario 2: The Component Mess**

You have a button you want to reuse:

```javascript
// How do you create a reusable button in vanilla JS?
function createButton(text, onClick) {
  const button = document.createElement("button");
  button.textContent = text;
  button.addEventListener("click", onClick);
  return button;
}

// If you use it 100 times, how do you update all instances?
// How do you pass different styling to each button?
// How do you clean up when a button is removed?
```

**Explore:**

- What makes code truly "reusable"?
- What is a "component" in framework terms?
- Why can't you just write functions for everything?
- How do frameworks manage component lifecycle?

#### Framework Paradigms

**Scenario 3: Imperative vs Declarative**

Vanilla JS (imperative - "how to do it"):

```javascript
const button = document.createElement("button");
button.textContent = "Click me";
button.addEventListener("click", handleClick);
button.classList.add("primary");
document.body.appendChild(button);
```

Framework approach (declarative - "what I want"):

```javascript
// React
<button className="primary" onClick={handleClick}>Click me</button>

// Vue
<button class="primary" @click="handleClick">Click me</button>

// Svelte
<button class="primary" on:click={handleClick}>Click me</button>
```

**Explore:**

- What's the difference between imperative and declarative code?
- Why do frameworks prefer declarative?
- Is declarative always better?
- What are the tradeoffs?
- How would you build a declarative system in vanilla JS?

**Scenario 4: Data Flow Patterns**

```javascript
// Data flows through your app - but how?

// One-way data flow (React):
// Parent owns data → passes to child via props → child sends events up

// Two-way binding (Vue, Angular):
// Data syncs automatically between model and view
```

**Explore:**

- What is one-way data flow?
- What is two-way binding?
- What are the pros and cons of each?
- How would you implement both patterns?

#### Rendering Strategies

**Scenario 5: The SEO Problem**

Your beautiful single-page app (SPA):

```html
<!-- What search engines see: -->
<div id="root"></div>
<script src="app.js"></script>

<!-- Nothing! The content is generated by JavaScript -->
```

**Explore:**

- What is client-side rendering (CSR)?
- Why can't search engines see CSR content reliably?
- What is server-side rendering (SSR)?
- What is static site generation (SSG)?
- When should you use CSR vs SSR vs SSG?
- How does each strategy work?

---

### Build It: Understanding Through Implementation

#### Exercise 1: Build Auto-Updating UI System

Create a system where data changes automatically update the DOM:

```javascript
// Goal: When data changes, UI updates automatically
function createReactive(initialValue) {
  let value = initialValue;
  const subscribers = [];

  return {
    get() {
      return value;
    },
    set(newValue) {
      value = newValue;
      // Notify all subscribers
      subscribers.forEach((fn) => fn(value));
    },
    subscribe(callback) {
      subscribers.push(callback);
      // Return unsubscribe function
      return () => {
        const index = subscribers.indexOf(callback);
        subscribers.splice(index, 1);
      };
    },
  };
}

// Test it:
const count = createReactive(0);

// Subscribe to changes
count.subscribe((value) => {
  document.querySelector("#count").textContent = value;
});

count.set(5); // DOM updates automatically!
```

**Now expand it:**

**A) Support computed values:**

```javascript
const firstName = createReactive("John");
const lastName = createReactive("Doe");

const fullName = createComputed(() => {
  return `${firstName.get()} ${lastName.get()}`;
});

fullName.subscribe((value) => {
  console.log("Full name:", value);
});

firstName.set("Jane"); // Logs "Full name: Jane Doe"
```

**B) Support nested objects:**

```javascript
const user = createReactive({
  name: "Alice",
  profile: {
    age: 30,
  },
});

user.subscribe((value) => {
  console.log("User changed:", value);
});

user.get().profile.age = 31; // Should this trigger subscribers? How?
```

**Requirements:**

- Create `createReactive(value)` function
- Create `createComputed(fn)` function
- Handle primitive values
- Handle nested objects (use Proxies)
- Prevent memory leaks (cleanup)
- Handle circular dependencies

#### Exercise 2: Build a Component System

Create reusable components with lifecycle:

```javascript
function createComponent(definition) {
  let mounted = false;
  let element = null;
  let state = definition.data ? definition.data() : {};
  let cleanup = null;

  return {
    mount(container) {
      if (mounted) return;

      // beforeMount hook
      definition.beforeMount?.();

      // Render
      element = definition.render(state);
      container.appendChild(element);
      mounted = true;

      // mounted hook
      cleanup = definition.mounted?.();
    },

    update(newProps) {
      if (!mounted) return;

      // beforeUpdate hook
      definition.beforeUpdate?.();

      // Re-render
      const newElement = definition.render(state);
      element.replaceWith(newElement);
      element = newElement;

      // updated hook
      definition.updated?.();
    },

    unmount() {
      if (!mounted) return;

      // beforeUnmount hook
      definition.beforeUnmount?.();

      // Cleanup
      cleanup?.();
      element.remove();
      mounted = false;

      // unmounted hook
      definition.unmounted?.();
    },
  };
}

// Usage:
const counter = createComponent({
  data() {
    return {count: 0};
  },

  mounted() {
    console.log("Counter mounted!");
    const interval = setInterval(() => {
      this.count++;
      this.update();
    }, 1000);

    // Return cleanup function
    return () => clearInterval(interval);
  },

  unmounted() {
    console.log("Counter unmounted and cleaned up!");
  },

  render(state) {
    const div = document.createElement("div");
    div.textContent = `Count: ${state.count}`;
    return div;
  },
});

counter.mount(document.body);
setTimeout(() => counter.unmount(), 5000);
```

**Requirements:**

- Lifecycle hooks: beforeMount, mounted, beforeUpdate, updated, beforeUnmount, unmounted
- Automatic cleanup on unmount
- State management within component
- Prevent updates after unmount
- Support async mounted hook

#### Exercise 3: Build the Same Counter in Vanilla + 4 Frameworks

Create a simple counter (increment, decrement, display) five times:

**Version 1: Pure Vanilla JavaScript (Imperative)**

```javascript
let count = 0;
const display = document.querySelector("#count");
const incBtn = document.querySelector("#inc");
const decBtn = document.querySelector("#dec");

function updateDisplay() {
  display.textContent = count;
}

incBtn.addEventListener("click", () => {
  count++;
  updateDisplay();
});

decBtn.addEventListener("click", () => {
  count--;
  updateDisplay();
});

updateDisplay();
```

**Version 2: Vanilla JavaScript (Declarative Pattern)**

```javascript
// Build a mini-framework that's declarative
function createApp(initialState, reducer, view) {
  let state = initialState;

  function setState(newState) {
    state = newState;
    render();
  }

  function dispatch(action) {
    setState(reducer(state, action));
  }

  function render() {
    const container = document.querySelector("#app");
    container.innerHTML = view(state, dispatch);
  }

  render();
}

// Use it:
createApp(
  {count: 0},
  (state, action) => {
    switch (action) {
      case "INC":
        return {count: state.count + 1};
      case "DEC":
        return {count: state.count - 1};
      default:
        return state;
    }
  },
  (state, dispatch) => `
    <div>
      <h1>${state.count}</h1>
      <button onclick="dispatch('INC')">+</button>
      <button onclick="dispatch('DEC')">-</button>
    </div>
  `
);
```

**Version 3: React**

```jsx
import {useState} from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h1>{count}</h1>
      <button onClick={() => setCount(count + 1)}>+</button>
      <button onClick={() => setCount(count - 1)}>-</button>
    </div>
  );
}
```

**Version 4: Vue**

```vue
<template>
  <div>
    <h1>{{ count }}</h1>
    <button @click="count++">+</button>
    <button @click="count--">-</button>
  </div>
</template>

<script setup>
import {ref} from "vue";
const count = ref(0);
</script>
```

**Version 5: Svelte**

```svelte
<script>
  let count = 0;
</script>

<div>
  <h1>{count}</h1>
  <button on:click={() => count++}>+</button>
  <button on:click={() => count--}>-</button>
</div>
```

**Version 6: Solid.js**

```jsx
import {createSignal} from "solid-js";

function Counter() {
  const [count, setCount] = createSignal(0);

  return (
    <div>
      <h1>{count()}</h1>
      <button onClick={() => setCount(count() + 1)}>+</button>
      <button onClick={() => setCount(count() - 1)}>-</button>
    </div>
  );
}
```

**After Building All Six:**

Compare and document:

| Aspect            | Vanilla (Imperative) | Vanilla (Declarative) | React      | Vue      | Svelte     | Solid           |
| ----------------- | -------------------- | --------------------- | ---------- | -------- | ---------- | --------------- |
| Lines of code     | ?                    | ?                     | ?          | ?        | ?          | ?               |
| State management  | Manual               | Custom                | `useState` | `ref`    | Variable   | `createSignal`  |
| How state updates | Manual call          | Dispatch              | `setState` | Direct   | Assignment | Setter function |
| How UI updates    | Manual               | Auto (re-render)      | Auto       | Auto     | Auto       | Auto            |
| Syntax            | Imperative           | Declarative           | JSX        | Template | Template   | JSX             |
| Readability       | ?                    | ?                     | ?          | ?        | ?          | ?               |

**Reflection Questions:**

- Which version was easiest to write?
- Which version will be easiest to maintain?
- How does each version handle state → UI updates?
- What patterns do frameworks share?
- What patterns are unique?
- Which approach feels most natural to you?

#### Exercise 4: Create a Framework Comparison Matrix

Research 4 frameworks and document:

**Frameworks to Compare:**

- React
- Vue 3
- Svelte
- Solid.js

**Create a detailed comparison table:**

| Feature               | React                       | Vue 3                     | Svelte                | Solid.js                |
| --------------------- | --------------------------- | ------------------------- | --------------------- | ----------------------- |
| **Philosophy**        | UI library, component-based | Progressive framework     | Compiler-first        | Fine-grained reactivity |
| **Reactivity Model**  | Virtual DOM + re-render     | Proxy-based reactive      | Compile-time reactive | Signal-based reactive   |
| **State Management**  | `useState`, `useReducer`    | `ref`, `reactive`         | Variables             | `createSignal`          |
| **How State Updates** | Call setter                 | Direct mutation or setter | Assignment            | Call setter             |
| **Component Syntax**  | JSX (JavaScript)            | SFC (HTML-like)           | SFC (HTML-like)       | JSX (JavaScript)        |
| **Learning Curve**    | ?                           | ?                         | ?                     | ?                       |
| **Bundle Size (min)** | ? KB                        | ? KB                      | ? KB                  | ? KB                    |
| **Performance**       | Good                        | Good                      | Excellent             | Excellent               |
| **SSR Support**       | Next.js                     | Nuxt                      | SvelteKit             | SolidStart              |
| **Job Market**        | Most jobs                   | Growing                   | Smaller               | Emerging                |
| **When to use**       | ?                           | ?                         | ?                     | ?                       |

**Research tasks:**

- Build the same todo app in all 4
- Read each framework's core philosophy docs
- Check npm downloads and GitHub stars
- Read performance benchmarks
- Check job listings in your area

---

### Reflection Questions

After building and researching:

1. **Understanding Frameworks:**

   - What specific problems do frameworks solve that vanilla JS can't?
   - What problems do frameworks introduce?
   - When is vanilla JS actually better?

2. **Paradigm Choices:**

   - Why is declarative code easier to reason about?
   - What are the tradeoffs of declarative vs imperative?
   - How does data flow affect architecture?

3. **Reactivity Models:**

   - What are the different ways frameworks achieve reactivity?
   - Why do different frameworks choose different approaches?
   - What are the performance implications?

4. **Deeper Understanding:**
   - How do frameworks make UI updates automatic?
   - What patterns are common across all frameworks?
   - If you were designing a framework, what choices would you make?

---

## Section 2: Component Architecture & Lifecycle

### The Problem

You're building a dashboard with multiple widgets. Each widget needs to:

- Fetch its own data when it appears
- Clean up when it's removed
- Update when its data changes
- Communicate with other widgets

In vanilla JS:

```javascript
class Widget {
  constructor(container, config) {
    this.container = container;
    this.config = config;
    this.data = null;
    this.interval = null;
    this.listeners = [];
    this.init();
  }

  async init() {
    this.data = await this.fetchData();
    this.render();
    this.interval = setInterval(() => this.refresh(), 5000);
    this.attachListeners();
  }

  attachListeners() {
    const button = this.container.querySelector("button");
    const handler = () => this.handleClick();
    button.addEventListener("click", handler);
    this.listeners.push({element: button, event: "click", handler});
  }

  async refresh() {
    this.data = await this.fetchData();
    this.render();
    this.attachListeners(); // Need to re-attach after re-render!
  }

  destroy() {
    clearInterval(this.interval);
    this.listeners.forEach(({element, event, handler}) => {
      element.removeEventListener(event, handler);
    });
    // What else did we forget to clean up?
  }

  render() {
    this.container.innerHTML = this.template();
    // All event listeners lost! Must re-attach!
  }
}
```

**Problems:**

- Manual lifecycle management is error-prone
- Easy to forget cleanup (memory leaks!)
- Re-rendering destroys event listeners
- Hard to compose small pieces into bigger ones
- Communication between components is messy

**Frameworks solve this with component lifecycle hooks and patterns.** But how do they work?

---

### Exploration Questions

#### Component Fundamentals

**Scenario 1: The Widget That Won't Die**

You create a widget, use it, then remove it from the page:

```javascript
const widget = new Widget("#container", config);
// Use it...
document.querySelector("#container").remove();

// But widget's setInterval is still running!
// And its event listeners still exist in memory!
// Memory leak!
```

**Explore:**

- How do you detect when a component is removed from the DOM?
- What resources need cleanup? (timers, listeners, subscriptions, etc.)
- How do frameworks handle this automatically?
- Build a system that tracks component lifecycle
- Build a system that auto-cleans up components

**Scenario 2: Props vs State**

```javascript
// A component receives data two ways:

// Props (from parent) - read-only
function UserCard(props) {
  // props.name, props.email
  // Should NOT modify props
}

// State (internal) - mutable
function UserCard(props) {
  let isExpanded = false; // Component's own state

  function toggle() {
    isExpanded = !isExpanded;
  }
}
```

**Explore:**

- What's the difference between props and state?
- Why shouldn't you modify props?
- When should data be props vs state?
- If props change, should the component update?
- How would you implement both concepts in vanilla JS?

#### Lifecycle Management

**Scenario 3: The Lifecycle Stages**

A component goes through stages:

```javascript
// 1. Created (initialized)
// 2. Mounted (added to DOM)
// 3. Updated (props/state changed)
// 4. Unmounted (removed from DOM)

// When should these run?
// - Fetch data?
// - Subscribe to events?
// - Clean up resources?
```

**Explore:**

- What operations belong in each lifecycle stage?
- Why separate creation from mounting?
- When should side effects run?
- How do you prevent effects from running too often?
- Build a lifecycle system from scratch

**Scenario 4: The Effect Dependency Problem**

```javascript
// You want to fetch user data when userId changes

function UserProfile({userId}) {
  // When should this run?
  async function fetchUser() {
    const user = await api.getUser(userId);
    // Update display
  }

  // Only when userId changes?
  // Also on first render?
  // Never? Only manually?
}
```

**Explore:**

- How do you run effects when specific values change?
- How do you track dependencies?
- What if you forget to declare a dependency?
- How would you implement dependency tracking?

#### Component Communication

**Scenario 5: Parent-Child Communication**

```javascript
// Parent has data, child needs it
Parent {
  data: [...]
}
  └─ Child {
    // How does child get parent's data?
    // How does child tell parent to update data?
  }
```

**Explore:**

- How do you pass data from parent to child?
- How do you pass functions from parent to child?
- How does child notify parent of events?
- Why can't child directly modify parent's data?
- Build a parent-child communication system

**Scenario 6: The Prop Drilling Problem**

```javascript
// Data needs to travel deep:
App (has user data)
└─ Dashboard
   └─ Sidebar
      └─ UserMenu
         └─ UserAvatar (needs user data!)

// Passing through every level is painful:
<Dashboard user={user}>
  <Sidebar user={user}>
    <UserMenu user={user}>
      <UserAvatar user={user} />
```

**Explore:**

- What is prop drilling?
- Why is it a problem?
- How do you skip intermediate components?
- What is context/provide-inject pattern?
- Build a context system in vanilla JS

#### Component Patterns

**Scenario 7: Composition vs Inheritance**

```javascript
// Inheritance approach
class BaseWidget {
  constructor() {
    /* common logic */
  }
  render() {
    /* base render */
  }
}

class UserWidget extends BaseWidget {
  render() {
    /* override */
  }
}

// Composition approach
function Widget({header, body, footer}) {
  return combine(header, body, footer);
}
```

**Explore:**

- Why do frameworks prefer composition over inheritance?
- What is "composition over inheritance"?
- How do you share logic between components?
- Build both approaches and compare

---

### Build It: Component System from Scratch

#### Exercise 1: Build a Full Lifecycle System

Create components with complete lifecycle:

```javascript
function createComponent(definition) {
  let state = definition.data ? definition.data() : {};
  let mounted = false;
  let element = null;
  let props = {};
  let cleanup = [];

  function scheduleCleanup(fn) {
    cleanup.push(fn);
  }

  function runCleanup() {
    cleanup.forEach((fn) => fn());
    cleanup = [];
  }

  return {
    mount(container, initialProps = {}) {
      if (mounted) return;
      props = initialProps;

      // 1. beforeMount
      definition.beforeMount?.call({state, props, scheduleCleanup});

      // 2. render
      element = definition.render.call({state, props});
      container.appendChild(element);

      mounted = true;

      // 3. mounted (can return cleanup function)
      const maybeCleanup = definition.mounted?.call({
        state,
        props,
        scheduleCleanup,
      });
      if (maybeCleanup) scheduleCleanup(maybeCleanup);
    },

    update(newProps = {}) {
      if (!mounted) return;
      const oldProps = props;
      props = {...props, ...newProps};

      // 1. beforeUpdate
      definition.beforeUpdate?.call({state, props, oldProps});

      // 2. re-render
      const newElement = definition.render.call({state, props});
      element.replaceWith(newElement);
      element = newElement;

      // 3. updated
      definition.updated?.call({state, props, oldProps});
    },

    unmount() {
      if (!mounted) return;

      // 1. beforeUnmount
      definition.beforeUnmount?.call({state, props});

      // 2. Run all cleanup functions
      runCleanup();

      // 3. Remove from DOM
      element.remove();
      mounted = false;

      // 4. unmounted
      definition.unmounted?.call({state, props});
    },

    // Expose state setter
    setState(updater) {
      if (typeof updater === "function") {
        state = {...state, ...updater(state)};
      } else {
        state = {...state, ...updater};
      }
      this.update();
    },
  };
}

// Usage:
const timer = createComponent({
  data() {
    return {count: 0};
  },

  beforeMount() {
    console.log("Timer will mount");
  },

  mounted() {
    console.log("Timer mounted!");

    const interval = setInterval(() => {
      this.setState({count: this.state.count + 1});
    }, 1000);

    // Return cleanup function
    return () => {
      clearInterval(interval);
      console.log("Timer interval cleared");
    };
  },

  beforeUpdate() {
    console.log("Timer will update");
  },

  updated() {
    console.log("Timer updated to:", this.state.count);
  },

  beforeUnmount() {
    console.log("Timer will unmount");
  },

  unmounted() {
    console.log("Timer unmounted!");
  },

  render() {
    const div = document.createElement("div");
    div.textContent = `Count: ${this.state.count}`;
    return div;
  },
});

timer.mount(document.body);
setTimeout(() => timer.unmount(), 5000);
```

**Requirements:**

- All lifecycle hooks working
- Automatic cleanup on unmount
- Support for async hooks
- Prevent operations after unmount
- State management with setState
- Props management

**Test it thoroughly:**

- Mount, update props, unmount
- Verify all hooks run in correct order
- Verify cleanup happens
- Try mounting twice (should not double-mount)
- Try updating after unmount (should not work)

#### Exercise 2: Build a Context System

Create a way to pass data deep without prop drilling:

```javascript
function createContext(defaultValue) {
  let value = defaultValue;
  const subscribers = new Set();

  return {
    Provider: {
      mount(container, newValue) {
        value = newValue;

        // Notify all consumers
        subscribers.forEach((sub) => sub(value));
      },

      setValue(newValue) {
        value = newValue;
        subscribers.forEach((sub) => sub(value));
      },
    },

    Consumer: {
      subscribe(callback) {
        subscribers.add(callback);
        callback(value); // Call immediately with current value

        // Return unsubscribe
        return () => subscribers.delete(callback);
      },

      getValue() {
        return value;
      },
    },
  };
}

// Usage:
const ThemeContext = createContext("light");

// Provider at top level
ThemeContext.Provider.mount(document.body, "dark");

// Consumer anywhere deep (no prop drilling!)
function Button() {
  let theme;

  const unsubscribe = ThemeContext.Consumer.subscribe((value) => {
    theme = value;
    console.log("Button theme:", theme);
    // Re-render button
  });

  // Later cleanup
  // unsubscribe();
}

// Change theme (all consumers update!)
ThemeContext.Provider.setValue("light");
```

**Requirements:**

- Create context with default value
- Provider sets/updates value
- Multiple consumers subscribe to changes
- Consumers auto-update when value changes
- Support nested providers (closest wins)
- Cleanup/unsubscribe mechanism

**Test it:**

- Consumer without provider (uses default)
- Consumer with provider
- Multiple consumers (all update)
- Nested providers (inner overrides outer)
- Change provider value (all consumers update)

#### Exercise 3: Compare Lifecycle Across Frameworks

Document how each framework handles lifecycle:

**Create comparison table:**

| Lifecycle Stage     | Your System         | React               | Vue 3             | Svelte           | Solid.js         |
| ------------------- | ------------------- | ------------------- | ----------------- | ---------------- | ---------------- |
| **Initialize**      | `data()`            | Constructor         | `setup()`         | Top of script    | Render function  |
| **Before Mount**    | `beforeMount`       | N/A                 | `onBeforeMount`   | N/A              | N/A              |
| **Mounted**         | `mounted`           | `useEffect(fn, [])` | `onMounted`       | `onMount`        | `onMount`        |
| **Before Update**   | `beforeUpdate`      | N/A                 | `onBeforeUpdate`  | N/A              | N/A              |
| **Updated**         | `updated`           | `useEffect(fn)`     | `onUpdated`       | `afterUpdate`    | `createEffect`   |
| **Before Unmount**  | `beforeUnmount`     | N/A                 | `onBeforeUnmount` | N/A              | `onCleanup`      |
| **Unmounted**       | `unmounted`         | `useEffect` cleanup | `onUnmounted`     | `onDestroy`      | `onCleanup`      |
| **Cleanup Pattern** | Return from mounted | Return from effect  | Return from hook  | Return from hook | Call `onCleanup` |

**Research questions:**

- Which framework has the most lifecycle hooks?
- Which has the least?
- How does React's useEffect replace multiple hooks?
- How does Svelte's compiler eliminate some hooks?
- Which approach is easier to understand?

#### Exercise 4: Build Todo App with Components

Create a complete todo app with proper component architecture:

**Component Structure:**

```
App (root component)
├─ Header
│  └─ AddTodoForm
├─ TodoList
│  └─ TodoItem (repeated for each todo)
│     ├─ Checkbox
│     ├─ Text
│     └─ DeleteButton
└─ Footer
   ├─ TodoCount
   └─ FilterButtons
```

**Requirements:**

- Each component in separate module/file
- Props flow down (parent → child)
- Events bubble up (child → parent)
- Use context for theme (light/dark mode)
- Proper lifecycle (fetch from localStorage on mount)
- Cleanup on unmount
- No prop drilling (use context where appropriate)

**Test it:**

- Add/delete/toggle todos
- Filter todos (all/active/completed)
- Switch theme
- Reload page (persist to localStorage)
- Monitor for memory leaks

---

### Reflection Questions

After building:

1. **Component Lifecycle:**

   - Why do components need lifecycle hooks?
   - What happens if you forget cleanup?
   - Which lifecycle stages are most important?

2. **Component Communication:**

   - When should you lift state up?
   - When should you use context?
   - What are the tradeoffs?

3. **Framework Comparison:**

   - Which framework's lifecycle is simplest?
   - Which gives you most control?
   - How does React's approach differ from Vue's?

4. **Deeper Understanding:**
   - How do frameworks track component lifecycle internally?
   - How do they know when to re-render?
   - What optimizations do they use?

---

## Section 3: Routing & Navigation Patterns

### The Problem

You built a multi-page app. When users click links, the whole page reloads:

```html
<a href="/about">About</a>
<!-- Full page reload! -->
```

**Problems:**

- Slow (reload everything: HTML, CSS, JS)
- Lost state (everything resets)
- Flickering (white screen between pages)
- No smooth transitions

You want a Single Page Application (SPA) where navigation is instant. But now you face new problems:

```javascript
// You intercept link clicks:
link.addEventListener("click", (e) => {
  e.preventDefault();
  showPage("about");
  // But the URL doesn't change!
  // Back button doesn't work!
  // Can't bookmark this page!
  // Can't share URL!
  // How do you solve this?
});
```

---

### Exploration Questions

#### Client-Side Routing Basics

**Scenario 1: The Broken Back Button**

You built an SPA that changes content without changing the URL:

```javascript
function navigate(page) {
  // Update content
  document.querySelector("#content").innerHTML = pages[page];

  // URL is still "/" - not updated!
  // User clicks back button → goes to previous website!
}
```

**Explore:**

- How do you change the URL without reloading the page?
- What is the History API?
- What are `pushState` and `replaceState`?
- How do you listen for back/forward button clicks?
- Build a router that updates the URL correctly

**Scenario 2: URL Pattern Matching**

You need to handle different URL patterns:

```javascript
// Static routes
/about
/contact

// Dynamic routes (parameters)
/users/123      → { userId: '123' }
/users/456/posts/789 → { userId: '456', postId: '789' }

// How do you match URLs to patterns?
// How do you extract parameters?
```

**Explore:**

- How do you match URL patterns?
- How do you extract route parameters?
- How do you handle wildcards?
- Should `/users/123` match `/users/:id`?
- Build a URL pattern matcher

#### Advanced Routing Patterns

**Scenario 3: Nested Routes**

Your app has nested structure:

```javascript
// /dashboard - shows Dashboard layout
// /dashboard/overview - Dashboard layout + Overview page
// /dashboard/users - Dashboard layout + Users page
// /dashboard/users/123 - Dashboard layout + Users page + User detail

// How do you render nested components?
```

**Explore:**

- What are nested routes?
- How do you render parent + child components?
- How do you create an "outlet" for child routes?
- Build nested routing system

**Scenario 4: Route Guards (Navigation Protection)**

You want to protect certain routes:

```javascript
// Only logged-in users can access /dashboard
// Only admins can access /admin
// Redirect to /login if unauthorized

// When should the guard run?
// Before navigation? After?
// Can guards be async? (check server)
```

**Explore:**

- What are route guards/navigation guards?
- How do you implement beforeEnter guards?
- How do you implement async guards?
- How do you redirect from guards?
- Build a guard system

**Scenario 5: Lazy Loading Routes**

Your app has many pages. Loading all code upfront is slow:

```javascript
// Don't load /admin code unless user visits /admin
// Don't load /dashboard code unless user visits /dashboard

// How do you split code by route?
// How do you load components on-demand?
// How do you show loading state?
```

**Explore:**

- What is code splitting?
- What is lazy loading?
- How do you use dynamic imports?
- How do you show loading state while loading?
- Implement lazy route loading

---

### Build It: Router from Scratch

#### Exercise 1: Build Basic Client-Side Router

Create a working router using the History API:

```javascript
function createRouter(routes) {
  let currentRoute = null;
  const listeners = [];

  function matchRoute(path) {
    for (const route of routes) {
      const match = matchPattern(route.path, path);
      if (match) {
        return {route, params: match};
      }
    }
    return null;
  }

  function matchPattern(pattern, path) {
    // Convert pattern like "/users/:id" to regex
    // Extract parameters
    // Return params object or null

    const paramNames = [];
    const regexPattern = pattern.replace(/:([^/]+)/g, (_, name) => {
      paramNames.push(name);
      return "([^/]+)";
    });

    const regex = new RegExp(`^${regexPattern}$`);
    const match = path.match(regex);

    if (!match) return null;

    const params = {};
    paramNames.forEach((name, index) => {
      params[name] = match[index + 1];
    });

    return params;
  }

  function navigate(path, replace = false) {
    const matched = matchRoute(path);

    if (!matched) {
      // Handle 404
      console.error("Route not found:", path);
      return;
    }

    // Update browser URL
    if (replace) {
      history.replaceState(null, "", path);
    } else {
      history.pushState(null, "", path);
    }

    // Update current route
    currentRoute = {...matched.route, params: matched.params};

    // Notify listeners
    listeners.forEach((fn) => fn(currentRoute));
  }

  function onRouteChange(callback) {
    listeners.push(callback);
    // Call immediately with current route
    if (currentRoute) callback(currentRoute);
  }

  // Listen for back/forward button
  window.addEventListener("popstate", () => {
    navigate(window.location.pathname, true);
  });

  // Intercept link clicks
  document.addEventListener("click", (e) => {
    if (e.target.tagName === "A" && e.target.origin === location.origin) {
      e.preventDefault();
      navigate(e.target.pathname);
    }
  });

  // Initial navigation
  navigate(window.location.pathname, true);

  return {
    navigate,
    back: () => history.back(),
    forward: () => history.forward(),
    onRouteChange,
    get currentRoute() {
      return currentRoute;
    },
  };
}

// Usage:
const router = createRouter([
  {path: "/", component: "Home"},
  {path: "/about", component: "About"},
  {path: "/users/:id", component: "UserProfile"},
  {path: "*", component: "NotFound"},
]);

router.onRouteChange((route) => {
  console.log("Route changed:", route);
  // Render the component
});

router.navigate("/users/123");
```

**Requirements:**

- Match static routes (`/about`)
- Match dynamic routes (`/users/:id`)
- Extract route parameters
- Update browser URL with `pushState`
- Handle back/forward buttons with `popstate`
- Intercept link clicks
- 404 handling (no match)
- `navigate()`, `back()`, `forward()` methods

**Test it:**

- Navigate between routes
- Use browser back/forward buttons
- Click regular links (should be intercepted)
- Reload page (should work)
- Try invalid URLs (should show 404)

#### Exercise 2: Add Advanced Features

Extend your router with:

**A) Nested Routes:**

```javascript
const routes = [
  {
    path: "/dashboard",
    component: DashboardLayout,
    children: [
      {path: "overview", component: Overview},
      {path: "users", component: Users},
      {path: "users/:id", component: UserDetail},
    ],
  },
];

// /dashboard → DashboardLayout
// /dashboard/overview → DashboardLayout + Overview
// /dashboard/users/123 → DashboardLayout + Users + UserDetail
```

**B) Route Guards:**

```javascript
const routes = [
  {
    path: "/admin",
    component: Admin,
    beforeEnter: async (to, from) => {
      const isAdmin = await checkAdminStatus();
      if (!isAdmin) {
        return {path: "/login", query: {redirect: to.path}};
      }
      // Return nothing = allow navigation
    },
  },
];
```

**C) Lazy Loading:**

```javascript
const routes = [
  {
    path: "/dashboard",
    component: () => import("./Dashboard.js"), // Lazy!
  },
];

// Show loading state while importing
// Handle import errors
```

**D) Query Parameters:**

```javascript
router.navigate({
  path: "/search",
  query: {q: "javascript", page: 2},
});
// URL: /search?q=javascript&page=2

// In component:
const query = router.query; // { q: 'javascript', page: 2 }
```

**E) Hash Fragments:**

```javascript
router.navigate("/docs#section-3");
// Scroll to element with id="section-3"
```

**F) Scroll Management:**

```javascript
// Scroll to top on navigation
// Restore scroll position on back button
// Smooth scroll to hash fragments
```

#### Exercise 3: Compare Framework Routers

Research how each framework handles routing:

**Create comparison table:**

| Feature              | Your Router   | React Router   | Vue Router           | SvelteKit       | Solid Router   |
| -------------------- | ------------- | -------------- | -------------------- | --------------- | -------------- |
| **Syntax**           | Object config | JSX components | Object config        | File-based      | JSX components |
| **Nested Routes**    | ?             | `<Outlet />`   | `<router-view />`    | Layouts         | `<Outlet />`   |
| **Route Guards**     | `beforeEnter` | Render check   | Navigation guards    | `load` function | Render check   |
| **Lazy Loading**     | `import()`    | `React.lazy`   | `import()`           | Automatic       | `lazy()`       |
| **Link Component**   | `<a>`         | `<Link>`       | `<router-link>`      | `<a>`           | `<A>`          |
| **Active Links**     | Manual        | `NavLink`      | `exact-active-class` | Manual          | `activeClass`  |
| **Programmatic Nav** | `navigate()`  | `navigate()`   | `router.push()`      | `goto()`        | `navigate()`   |

**Research:**

- How does each framework's router work?
- Which API is most intuitive?
- Which has the most features?
- Which is most performant?

#### Exercise 4: Build Real App with Routing

Create a blog app with full routing:

**Routes:**

- `/` - Home (list of posts)
- `/posts/:slug` - Single post view
- `/about` - About page
- `/login` - Login page
- `/dashboard` - Protected (requires login)
  - `/dashboard/posts` - User's posts
  - `/dashboard/posts/new` - Create new post
  - `/dashboard/posts/:id/edit` - Edit post
- `*` - 404 Not Found

**Requirements:**

- All basic routing features
- Nested routes (/dashboard/...)
- Route guards (protect /dashboard)
- Lazy load dashboard routes
- Query params for filtering posts
- Scroll to top on navigation
- Loading states for lazy routes
- Active link highlighting in nav
- Proper 404 handling
- Back button works correctly

---

### Reflection Questions

After building:

1. **Router Internals:**

   - How does the History API work?
   - Why do we need to intercept link clicks?
   - How do routers match URL patterns?

2. **SPA Tradeoffs:**

   - What are the benefits of client-side routing?
   - What are the drawbacks?
   - When is server-side routing better?
   - How do you handle SEO with client-side routing?

3. **Patterns:**

   - When should you use nested routes?
   - When should you use route guards?
   - When should you lazy load routes?

4. **Framework Comparison:**
   - How do different frameworks approach routing?
   - Which router API do you prefer and why?
   - What optimizations do framework routers have?

---

## Section 4: State Management Architecture

### The Problem

Your app is growing. State is scattered everywhere and components are passing props through many levels:

```javascript
// State in multiple places
function TodoList() {
  const todos = [
    /* local state */
  ];
}

function TodoCount() {
  // How do I get todos from TodoList?
  // Need to lift state up!
}

function AddTodoForm() {
  // How do I add a todo to TodoList's state?
  // Need to pass callback down!
}

// After lifting state up...
function App() {
  const todos = [
    /* state */
  ];

  return `
    <Header user={user} />
      <UserMenu user={user} />
        <Avatar user={user} /> <!-- Prop drilling! -->
    <Sidebar todos={todos} />
      <TodoCount todos={todos} />
    <Content todos={todos} />
      <TodoList todos={todos} />
  `;
}
```

**Problems:**

- Prop drilling (passing props through components that don't use them)
- State updates scattered across components
- Hard to track where state changes
- Hard to debug state issues
- Components tightly coupled

**You need centralized state management.** But how?

---

### Exploration Questions

#### State Management Fundamentals

**Scenario 1: The Global State Problem**

Two components far apart need the same data:

```javascript
// They don't have a common parent (or it's too far up)
// Using global variable doesn't trigger re-renders

let globalTodos = [];

function ComponentA() {
  globalTodos.push(newTodo); // Changes data
  // But UI doesn't update!
}

function ComponentB() {
  // How does it know globalTodos changed?
}
```

**Explore:**

- What is global state?
- How is it different from component state?
- How do you make components react to global state changes?
- What is a state store?
- Build a simple reactive store

**Scenario 2: Direct Mutation Problems**

```javascript
const state = {
  todos: [{text: "Buy milk", done: false}],
};

// Direct mutation
state.todos[0].done = true;
// How do you know this happened?
// How do you notify components?
// How do you debug what changed?
```

**Explore:**

- Why are direct mutations problematic?
- What is immutable state?
- How do you update nested state immutably?
- How do you track state changes?
- Build an immutable state system

#### State Management Patterns

**Scenario 3: Actions and Reducers (Redux Pattern)**

Instead of mutating directly, describe changes:

```javascript
// Current state
{
  todos: [],
  filter: 'all'
}

// Action (describes what happened)
{
  type: 'ADD_TODO',
  payload: { text: 'Buy milk' }
}

// Reducer (pure function that produces new state)
function reducer(state, action) {
  switch (action.type) {
    case 'ADD_TODO':
      return {
        ...state,
        todos: [...state.todos, action.payload]
      };
    default:
      return state;
  }
}

// Dispatch the action
dispatch({ type: 'ADD_TODO', payload: { text: 'Buy milk' } });
```

**Explore:**

- What is an action? What is a reducer?
- Why are reducers pure functions?
- Why can't you mutate state in reducers?
- What are the benefits of this pattern?
- Build a Redux-like store

**Scenario 4: Async State Updates**

You need to fetch data:

```javascript
// This won't work - reducers can't be async!
function reducer(state, action) {
  if (action.type === 'FETCH_USER') {
    const user = await api.getUser(); // ERROR!
    return { ...state, user };
  }
}

// Where do async operations go?
// How do you handle loading/error states?
```

**Explore:**

- Why can't reducers be async?
- What are side effects?
- Where do side effects belong in this pattern?
- How do you handle loading and error states?
- Build async action handling

#### Advanced State Patterns

**Scenario 5: Derived State (Computed Values)**

You have todos and need filtered todos:

```javascript
// Bad: Store computed value
{
  todos: [...],
  filter: 'active',
  filteredTodos: [...] // Duplicate data!
}

// Good: Compute on demand
function getFilteredTodos(state) {
  return state.todos.filter(t => {
    if (state.filter === 'active') return !t.done;
    if (state.filter === 'completed') return t.done;
    return true;
  });
}

// But this recomputes every time!
// How do you memoize it?
```

**Explore:**

- What is derived state?
- Why shouldn't you store derived values?
- What is memoization?
- How do selectors work?
- Build memoized selectors

**Scenario 6: Normalized State**

API returns nested data:

```javascript
{
  posts: [
    {
      id: 1,
      author: { id: 10, name: 'Alice' },
      comments: [
        { id: 100, author: { id: 10, name: 'Alice' } },
        { id: 101, author: { id: 20, name: 'Bob' } }
      ]
    }
  ]
}

// Alice's data is duplicated 3 times!
// If Alice changes name, you must update 3 places!

// Better: Normalize by entity type
{
  users: {
    10: { id: 10, name: 'Alice' },
    20: { id: 20, name: 'Bob' }
  },
  posts: {
    1: { id: 1, authorId: 10, commentIds: [100, 101] }
  },
  comments: {
    100: { id: 100, authorId: 10 },
    101: { id: 101, authorId: 20 }
  }
}
```

**Explore:**

- What is normalized state?
- How do you structure state by entity ID?
- How do you avoid data duplication?
- Build a normalization function

---

### Build It: State Management from Scratch

#### Exercise 1: Build a Redux-Like Store

Create a complete state management system:

```javascript
function createStore(reducer, initialState, enhancer) {
  // If enhancer provided (middleware), apply it
  if (enhancer) {
    return enhancer(createStore)(reducer, initialState);
  }

  let state = initialState;
  let listeners = [];

  function getState() {
    return state;
  }

  function dispatch(action) {
    // Update state with reducer
    state = reducer(state, action);

    // Notify all listeners
    listeners.forEach((listener) => listener());

    return action;
  }

  function subscribe(listener) {
    listeners.push(listener);

    // Return unsubscribe function
    return () => {
      listeners = listeners.filter((l) => l !== listener);
    };
  }

  // Initialize state
  dispatch({type: "@@INIT"});

  return {
    getState,
    dispatch,
    subscribe,
  };
}

// Usage:
function todosReducer(state = {todos: []}, action) {
  switch (action.type) {
    case "ADD_TODO":
      return {
        ...state,
        todos: [...state.todos, action.payload],
      };
    case "TOGGLE_TODO":
      return {
        ...state,
        todos: state.todos.map((t) =>
          t.id === action.payload ? {...t, done: !t.done} : t
        ),
      };
    default:
      return state;
  }
}

const store = createStore(todosReducer, {todos: []});

store.subscribe(() => {
  console.log("State changed:", store.getState());
});

store.dispatch({
  type: "ADD_TODO",
  payload: {id: 1, text: "Buy milk", done: false},
});
```

**Requirements:**

- `getState()` - returns current state
- `dispatch(action)` - updates state via reducer
- `subscribe(listener)` - register listener
- Returns unsubscribe function
- Reducers must be pure functions
- State updates are immutable

#### Exercise 2: Add Middleware Support

Create middleware system for async actions, logging, etc:

```javascript
function applyMiddleware(...middlewares) {
  return (createStore) => (reducer, initialState) => {
    const store = createStore(reducer, initialState);
    let dispatch = store.dispatch;

    // Build middleware chain
    const middlewareAPI = {
      getState: store.getState,
      dispatch: (action) => dispatch(action),
    };

    const chain = middlewares.map((middleware) => middleware(middlewareAPI));
    dispatch = chain.reduceRight(
      (next, middleware) => middleware(next),
      store.dispatch
    );

    return {
      ...store,
      dispatch,
    };
  };
}

// Logger middleware
const logger = (store) => (next) => (action) => {
  console.log("Dispatching:", action);
  const result = next(action);
  console.log("New state:", store.getState());
  return result;
};

// Thunk middleware (for async actions)
const thunk = (store) => (next) => (action) => {
  if (typeof action === "function") {
    return action(store.dispatch, store.getState);
  }
  return next(action);
};

// Usage:
const store = createStore(
  reducer,
  initialState,
  applyMiddleware(logger, thunk)
);

// Now you can dispatch async actions
store.dispatch(async (dispatch, getState) => {
  dispatch({type: "FETCH_START"});
  try {
    const data = await api.fetchData();
    dispatch({type: "FETCH_SUCCESS", payload: data});
  } catch (error) {
    dispatch({type: "FETCH_ERROR", error});
  }
});
```

#### Exercise 3: Build Memoized Selectors

Create selector system with memoization:

```javascript
function createSelector(inputSelectors, resultFunc) {
  let lastArgs = null;
  let lastResult = null;

  return (state) => {
    // Get current input values
    const currentArgs = inputSelectors.map((selector) => selector(state));

    // Check if inputs changed (shallow comparison)
    if (lastArgs && arraysEqual(currentArgs, lastArgs)) {
      // Inputs unchanged, return cached result
      return lastResult;
    }

    // Inputs changed, recompute
    lastArgs = currentArgs;
    lastResult = resultFunc(...currentArgs);
    return lastResult;
  };
}

function arraysEqual(a, b) {
  return a.length === b.length && a.every((val, i) => val === b[i]);
}

// Usage:
const selectTodos = (state) => state.todos;
const selectFilter = (state) => state.filter;

const selectFilteredTodos = createSelector(
  [selectTodos, selectFilter],
  (todos, filter) => {
    console.log("Computing filtered todos..."); // Only when needed!
    return todos.filter((t) => {
      if (filter === "active") return !t.done;
      if (filter === "completed") return t.done;
      return true;
    });
  }
);

const selectActiveCount = createSelector(
  [selectFilteredTodos],
  (filtered) => filtered.filter((t) => !t.done).length
);

// Call multiple times
selectFilteredTodos(state); // Computes
selectFilteredTodos(state); // Cached!
selectFilteredTodos(state); // Still cached!

// Change state
const newState = {...state, filter: "active"};
selectFilteredTodos(newState); // Recomputes (filter changed)
```

#### Exercise 4: Compare State Management Approaches

Build the same todo app using different patterns:

**A) Your Redux-like Store**

- Actions, reducers, dispatch
- Centralized state
- Immutable updates

**B) Observable Pattern (MobX-style)**

- Reactive observables
- Automatic tracking
- Direct mutations allowed

**C) Atom Pattern (Recoil/Jotai-style)**

- Atomic state pieces
- Derived atoms
- Fine-grained subscriptions

**D) Signal Pattern (Solid-style)**

- Fine-grained reactivity
- Computed values
- Minimal API

**Compare:**

| Aspect         | Redux     | Observable | Atom      | Signal    |
| -------------- | --------- | ---------- | --------- | --------- |
| Boilerplate    | High      | Low        | Medium    | Low       |
| Learning curve | Steep     | Medium     | Medium    | Gentle    |
| Debugging      | Excellent | Good       | Good      | Good      |
| Performance    | Good      | Excellent  | Excellent | Excellent |
| DevTools       | Excellent | Good       | Good      | Limited   |

#### Exercise 5: Build Complete Todo App

Create full-featured todo app with your state management:

**State Shape:**

```javascript
{
  todos: {
    byId: {
      '1': { id: '1', text: 'Buy milk', done: false },
      '2': { id: '2', text: 'Walk dog', done: true }
    },
    allIds: ['1', '2']
  },
  filter: 'all', // 'all' | 'active' | 'completed'
  ui: {
    loading: false,
    error: null
  }
}
```

**Actions:**

- `ADD_TODO`
- `TOGGLE_TODO`
- `DELETE_TODO`
- `SET_FILTER`
- `FETCH_TODOS_START/SUCCESS/ERROR`

**Features:**

- Add, toggle, delete todos
- Filter by all/active/completed
- Fetch from API (with loading states)
- Optimistic updates
- Error handling with retry
- Persist to localStorage
- Undo/redo functionality
- Derived selectors (filtered todos, counts)

**Requirements:**

- Use your custom store
- Use middleware for async
- Use selectors for derived state
- Normalized state shape
- Handle all edge cases
- No prop drilling (use context or similar)

---

### Reflection Questions

After building:

1. **State Management Basics:**

   - Why centralize state?
   - When is component state better?
   - What problems does immutability solve?

2. **Patterns:**

   - Why use actions and reducers?
   - When is this pattern overkill?
   - What are alternatives?

3. **Framework Comparison:**

   - How does Redux differ from MobX?
   - How does Context differ from Redux?
   - When would you choose each?

4. **Deeper Understanding:**
   - What optimizations do state libraries use?
   - How do they prevent unnecessary re-renders?
   - What's the future of state management?

---

# 🟡 CORE PATTERNS (Essential Framework Features)

---

## Section 5: Reactivity Systems

### The Problem

You update a variable but the UI doesn't update:

```javascript
let count = 0;

function increment() {
  count++;
  // UI doesn't update!
  // You must manually call render()
}
```

You need reactivity - when data changes, the UI automatically updates. But frameworks achieve this in completely different ways:

**React:** Explicit state + re-render entire component

```javascript
const [count, setCount] = useState(0);
setCount(count + 1); // Component re-renders
```

**Vue:** Proxy-based reactive objects

```javascript
const state = reactive({count: 0});
state.count++; // Auto-updates UI!
```

**Svelte:** Compiler transforms assignments

```svelte
<script>
  let count = 0;
  count++; // Compiler makes this reactive
</script>
```

**Solid:** Fine-grained signals

```javascript
const [count, setCount] = createSignal(0);
setCount(count() + 1); // Only updates what uses count
```

**How do these different approaches work?** What are the tradeoffs? Let's build them all from scratch.

---

### Exploration Questions

#### Reactivity Fundamentals

**Scenario 1: Manual vs Automatic Updates**

```javascript
// Manual (vanilla JS)
let count = 0;
function increment() {
  count++;
  document.querySelector("#count").textContent = count; // Manual!
}

// Automatic (frameworks)
// Change count → UI updates automatically
// How do they do this?
```

**Explore:**

- What makes something "reactive"?
- How do you detect when data changes?
- How do you know what to update in the UI?
- Build a system that auto-updates on change

**Scenario 2: Push vs Pull Reactivity**

```javascript
// Push: Data notifies UI when it changes (Observer pattern)
const count = observable(0);
count.subscribe(() => updateUI());
count.set(5); // Automatically calls updateUI()

// Pull: UI re-renders and pulls latest data
let count = 0;
count++; // UI doesn't know
render(); // Re-render entire UI, pull latest count
```

**Explore:**

- What's the difference between push and pull?
- Which is more efficient?
- Which does React use? Vue? Svelte? Solid?
- Build both approaches

#### Building Reactivity Systems

**Scenario 3: Simple Observable (Signal Pattern)**

```javascript
function createSignal(initialValue) {
  let value = initialValue;
  const subscribers = new Set();

  function read() {
    // Track who's reading this signal
    // (for computed values / effects)
    return value;
  }

  function write(newValue) {
    value = newValue;
    // Notify all subscribers
    subscribers.forEach((fn) => fn());
  }

  return [read, write];
}

const [count, setCount] = createSignal(0);
console.log(count()); // 0
setCount(5);
console.log(count()); // 5
```

**Explore:**

- How do you store the current value?
- How do you track subscribers?
- How do you notify subscribers?
- Build createSignal from scratch
- How is this different from useState?

**Scenario 4: Computed Values (Derived State)**

```javascript
const [firstName, setFirstName] = createSignal("John");
const [lastName, setLastName] = createSignal("Doe");

// fullName should auto-update when either name changes
const fullName = createComputed(() => {
  console.log("Computing...");
  return `${firstName()} ${lastName()}`;
});

console.log(fullName()); // "John Doe" (computes)
console.log(fullName()); // "John Doe" (cached!)

setFirstName("Jane");
console.log(fullName()); // "Jane Doe" (recomputes)
```

**Explore:**

- How do computed values track their dependencies?
- How do they know when to recompute?
- How do you prevent unnecessary recomputations?
- Build createComputed from scratch

**Scenario 5: Effects (Side Effects)**

```javascript
const [count, setCount] = createSignal(0);

// Run effect whenever count changes
createEffect(() => {
  console.log("Count is:", count());
  document.title = `Count: ${count()}`;
});

setCount(5); // Effect runs again!
```

**Explore:**

- How do effects track dependencies automatically?
- How do you run cleanup before re-running?
- How do you prevent infinite loops?
- Build createEffect from scratch

#### Advanced Reactivity

**Scenario 6: Proxy-Based Reactivity (Vue style)**

```javascript
const state = reactive({
  count: 0,
  user: {
    name: "Alice",
    age: 30,
  },
});

// Any access or mutation is tracked
state.count++; // Tracked!
state.user.name = "Bob"; // Also tracked!

// How does this work?
```

**Explore:**

- How do Proxies intercept get/set?
- How do you track what properties are accessed?
- How do you handle nested objects?
- What operations can/can't be tracked?
- Build reactive() using Proxies

**Scenario 7: Compiler-Based Reactivity (Svelte style)**

```svelte
<script>
  let count = 0;

  function increment() {
    count++; // How does Svelte make this reactive?
  }
</script>

<button on:click={increment}>{count}</button>
```

Svelte compiler transforms this to:

```javascript
let count = 0;

function increment() {
  count++;
  $$invalidate("count", count); // Compiler adds this!
}
```

**Explore:**

- How does the compiler detect reactive statements?
- What code does it inject?
- What are the benefits vs runtime reactivity?
- What are the limitations?

---

### Build It: Multiple Reactivity Systems

#### Exercise 1: Build Signal-Based Reactivity (Solid.js style)

Create a complete signal system:

```javascript
// Track current effect
let currentEffect = null;

function createSignal(initialValue) {
  let value = initialValue;
  const subscribers = new Set();

  function read() {
    // If an effect/computed is running, register dependency
    if (currentEffect) {
      subscribers.add(currentEffect);
      currentEffect.dependencies.add(read);
    }
    return value;
  }

  function write(newValue) {
    if (value === newValue) return;
    value = newValue;

    // Notify all subscribers
    subscribers.forEach((effect) => effect.execute());
  }

  return [read, write];
}

function createEffect(fn) {
  const effect = {
    execute() {
      // Clear old dependencies
      effect.dependencies.forEach((signal) => {
        // Remove this effect from signal's subscribers
        // (implementation detail omitted for brevity)
      });
      effect.dependencies.clear();

      // Run effect (will track new dependencies)
      currentEffect = effect;
      try {
        fn();
      } finally {
        currentEffect = null;
      }
    },
    dependencies: new Set(),
  };

  effect.execute();
  return effect;
}

function createComputed(fn) {
  const [read, write] = createSignal();

  createEffect(() => {
    write(fn());
  });

  return read;
}

// Test it:
const [count, setCount] = createSignal(0);
const [name, setName] = createSignal("Alice");

const message = createComputed(() => {
  return `${name()} has clicked ${count()} times`;
});

createEffect(() => {
  console.log("Message:", message());
  document.title = message();
});

setCount(5); // Effect runs
setName("Bob"); // Effect runs
setCount(5); // Effect doesn't run (value unchanged)
```

**Requirements:**

- `createSignal(value)` - create reactive value
- `createEffect(fn)` - run side effects, auto-track dependencies
- `createComputed(fn)` - derived values, memoized
- Automatic dependency tracking
- Only notify when value actually changes
- Cleanup old dependencies on re-run
- Prevent infinite loops

#### Exercise 2: Build Proxy-Based Reactivity (Vue style)

Create Vue-like reactive objects:

```javascript
// Global tracking
const targetMap = new WeakMap();
let activeEffect = null;

function track(target, key) {
  if (!activeEffect) return;

  let depsMap = targetMap.get(target);
  if (!depsMap) {
    targetMap.set(target, (depsMap = new Map()));
  }

  let deps = depsMap.get(key);
  if (!deps) {
    depsMap.set(key, (deps = new Set()));
  }

  deps.add(activeEffect);
}

function trigger(target, key) {
  const depsMap = targetMap.get(target);
  if (!depsMap) return;

  const deps = depsMap.get(key);
  if (deps) {
    deps.forEach((effect) => effect());
  }
}

function reactive(target) {
  const handler = {
    get(target, key, receiver) {
      const result = Reflect.get(target, key, receiver);

      // Track this property access
      track(target, key);

      // If result is an object, make it reactive too
      if (typeof result === "object" && result !== null) {
        return reactive(result);
      }

      return result;
    },

    set(target, key, value, receiver) {
      const oldValue = target[key];
      const result = Reflect.set(target, key, value, receiver);

      // Trigger effects if value changed
      if (oldValue !== value) {
        trigger(target, key);
      }

      return result;
    },

    deleteProperty(target, key) {
      const result = Reflect.deleteProperty(target, key);
      trigger(target, key);
      return result;
    },
  };

  return new Proxy(target, handler);
}

function effect(fn) {
  activeEffect = fn;
  fn();
  activeEffect = null;
}

function computed(getter) {
  let value;
  let dirty = true;

  const runner = effect(() => {
    if (dirty) {
      value = getter();
      dirty = false;
    }
  });

  return {
    get value() {
      if (dirty) {
        value = getter();
        dirty = false;
      }
      return value;
    },
  };
}

// Test it:
const state = reactive({
  count: 0,
  user: {
    name: "Alice",
    age: 30,
  },
});

effect(() => {
  console.log("Count:", state.count);
  document.querySelector("#count").textContent = state.count;
});

effect(() => {
  console.log("User:", state.user.name);
});

state.count++; // First effect runs
state.user.name = "Bob"; // Second effect runs
state.user.age = 31; // No effect runs (age not tracked)
```

**Requirements:**

- `reactive(obj)` - make object reactive
- Deep reactivity (nested objects)
- Track property access
- Trigger on property changes
- `effect(fn)` - run side effects
- `computed(fn)` - memoized computed values
- Handle arrays
- Handle property deletion

#### Exercise 3: Build Observable System (RxJS style)

Create observable streams:

```javascript
class Observable {
  constructor(subscriber) {
    this._subscriber = subscriber;
  }

  subscribe(observer) {
    return this._subscriber(observer);
  }

  static create(producer) {
    return new Observable(producer);
  }

  map(fn) {
    return Observable.create((observer) => {
      return this.subscribe({
        next: (value) => observer.next(fn(value)),
        error: (err) => observer.error(err),
        complete: () => observer.complete(),
      });
    });
  }

  filter(predicate) {
    return Observable.create((observer) => {
      return this.subscribe({
        next: (value) => {
          if (predicate(value)) {
            observer.next(value);
          }
        },
        error: (err) => observer.error(err),
        complete: () => observer.complete(),
      });
    });
  }

  static interval(ms) {
    return Observable.create((observer) => {
      const id = setInterval(() => {
        observer.next(Date.now());
      }, ms);

      // Return cleanup function
      return () => clearInterval(id);
    });
  }

  static fromEvent(element, eventName) {
    return Observable.create((observer) => {
      const handler = (event) => observer.next(event);
      element.addEventListener(eventName, handler);

      return () => {
        element.removeEventListener(eventName, handler);
      };
    });
  }
}

// Test it:
const numbers = Observable.create((observer) => {
  observer.next(1);
  observer.next(2);
  observer.next(3);
  observer.complete();

  return () => console.log("Cleaned up");
});

numbers
  .map((x) => x * 2)
  .filter((x) => x > 2)
  .subscribe({
    next: (value) => console.log(value), // 4, 6
    complete: () => console.log("Done!"),
  });

// Mouse clicks
const clicks = Observable.fromEvent(document, "click");
clicks.subscribe({
  next: (event) => console.log("Clicked!", event),
});

// Interval
const ticks = Observable.interval(1000);
const subscription = ticks.subscribe({
  next: (time) => console.log("Tick:", time),
});

// Later: cleanup
setTimeout(() => subscription(), 5000);
```

**Requirements:**

- `Observable` class
- `subscribe(observer)` method
- `map`, `filter` operators
- `fromEvent`, `interval` factories
- Cleanup/unsubscribe support
- Error handling
- Completion handling

#### Exercise 4: Compare All Reactivity Systems

Build the same real-time search filter app using all systems:

**App Requirements:**

- Input field for search term
- List of 1000+ items
- Filter items as user types
- Show count of matches
- Debounce input (300ms)

**Build with:**

1. Signal-based (your Solid-style system)
2. Proxy-based (your Vue-style system)
3. Observable-based (your RxJS-style system)
4. React-style (re-render on setState)

**Measure and compare:**

| Metric                    | Signals | Proxy | Observable | React |
| ------------------------- | ------- | ----- | ---------- | ----- |
| Lines of code             | ?       | ?     | ?          | ?     |
| Initial setup             | ?       | ?     | ?          | ?     |
| Ease of use               | ?       | ?     | ?          | ?     |
| Performance (1000 items)  | ?       | ?     | ?          | ?     |
| Performance (10000 items) | ?       | ?     | ?          | ?     |
| Memory usage              | ?       | ?     | ?          | ?     |
| Debugging ease            | ?       | ?     | ?          | ?     |

**Reflection:**

- Which system felt most natural?
- Which had best performance?
- Which would you choose for what use case?
- What tradeoffs did each make?

---

### Reflection Questions

After building:

1. **Reactivity Models:**

   - What are the fundamental approaches to reactivity?
   - Why does React re-render entire components?
   - Why does Vue use Proxies?
   - Why does Solid use signals?
   - Why does Svelte use a compiler?

2. **Performance:**

   - Which reactivity model is fastest? Why?
   - What are the tradeoffs of fine-grained vs coarse-grained?
   - When does fine-grained reactivity matter?
   - When is re-rendering the entire component fine?

3. **Developer Experience:**

   - Which model is easiest to understand?
   - Which has the least boilerplate?
   - Which gives you most control?
   - Which is hardest to debug?

4. **Framework Choices:**
   - Why did React choose its model?
   - Why did Vue choose Proxies?
   - Why did Svelte choose compilation?
   - Why did Solid choose signals?
   - What constraints influenced each choice?

---

## Section 6: The Hooks Pattern

### The Problem

React introduced hooks as a way to use state and lifecycle in function components. But hooks are actually a **universal pattern** that any framework can use.

**Before hooks (class-based):**

```javascript
class Counter {
  constructor() {
    this.state = {count: 0};
  }

  componentDidMount() {
    // Fetch data, setup listeners
  }

  componentWillUnmount() {
    // Cleanup listeners
  }

  render() {
    return `<div>${this.state.count}</div>`;
  }
}
```

**With hooks (function-based):**

```javascript
function Counter() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    // Fetch data, setup listeners

    return () => {
      // Cleanup
    };
  }, []);

  return `<div>${count}</div>`;
}
```

**But wait - how does `useState` remember values between calls? How does `useEffect` know when to run?** Let's build the hooks pattern from scratch to understand.

---

### Exploration Questions

**Scenario 1: The useState Mystery**

```javascript
function Counter() {
  const [count, setCount] = useState(0);
  // How does this work?
  // Where is count stored between renders?
  // How does React know which component this belongs to?

  setCount(5); // Component re-renders with count === 5

  // On second render:
  const [count, setCount] = useState(0); // Still returns 5!
}
```

**Explore:**

- Where is the state actually stored?
- How does it survive between function calls?
- How does it know which component's state to return?
- Build your own useState

**Scenario 2: Multiple useState Calls**

```javascript
function Component() {
  const [count, setCount] = useState(0);
  const [name, setName] = useState("Alice");
  const [age, setAge] = useState(30);

  // How does useState know which value to return?
  // They're called in the same order every time
  // What if the order changes?
}
```

**Explore:**

- How are multiple state values tracked?
- Why must hooks be called in the same order?
- What breaks if you call hooks conditionally?
- Build a system that tracks multiple states

**Scenario 3: The useEffect Puzzle**

```javascript
// Runs on every render
useEffect(() => {
  console.log("Every render");
});

// Runs once (on mount)
useEffect(() => {
  console.log("Only once");
}, []);

// Runs when count changes
useEffect(() => {
  console.log("Count changed");
}, [count]);
```

**Explore:**

- How does the dependency array work?
- How does it know when dependencies changed?
- What happens if you forget a dependency?
- Build your own useEffect

**Scenario 4: Effect Cleanup**

```javascript
useEffect(() => {
  const interval = setInterval(() => {
    console.log("Tick");
  }, 1000);

  return () => {
    clearInterval(interval);
  };
}, []);

// When does cleanup run?
// What if there's no cleanup function?
```

**Explore:**

- When does cleanup function run?
- How is it stored between renders?
- What if cleanup is async?
- Build cleanup handling

---

### Build It: Hooks System from Scratch

#### Exercise 1: Build useState and useEffect

Create working hooks implementation:

```javascript
// Global state for current component
let currentComponent = null;
let hookIndex = 0;

function useState(initialValue) {
  // Get current component's hooks array
  const component = currentComponent;
  const index = hookIndex++;

  // Initialize hooks array if needed
  if (!component.hooks) {
    component.hooks = [];
  }

  // Initialize this hook if first time
  if (component.hooks[index] === undefined) {
    component.hooks[index] = initialValue;
  }

  // Setter function
  const setState = (newValue) => {
    component.hooks[index] = newValue;
    // Re-render component
    component.render();
  };

  return [component.hooks[index], setState];
}

function useEffect(callback, dependencies) {
  const component = currentComponent;
  const index = hookIndex++;

  if (!component.hooks) {
    component.hooks = [];
  }

  const hasNoDeps = !dependencies;
  const hasChangedDeps = component.hooks[index]
    ? !dependencies.every((dep, i) => dep === component.hooks[index].deps[i])
    : true;

  if (hasNoDeps || hasChangedDeps) {
    // Run cleanup from previous effect
    if (component.hooks[index]?.cleanup) {
      component.hooks[index].cleanup();
    }

    // Run effect and store cleanup
    const cleanup = callback();

    component.hooks[index] = {
      deps: dependencies,
      cleanup,
    };
  }
}

// Component system
function createComponent(fn) {
  const component = {
    fn,
    hooks: [],

    render() {
      // Reset hook index
      hookIndex = 0;
      currentComponent = this;

      // Call component function
      const result = this.fn();

      currentComponent = null;
      return result;
    },
  };

  return component;
}

// Test it:
function Counter() {
  const [count, setCount] = useState(0);
  const [name, setName] = useState("Alice");

  useEffect(() => {
    console.log("Count changed:", count);
    document.title = `Count: ${count}`;

    // Cleanup
    return () => {
      console.log("Cleanup count effect");
    };
  }, [count]);

  useEffect(() => {
    console.log("Name changed:", name);

    return () => {
      console.log("Cleanup name effect");
    };
  }, [name]);

  return {
    count,
    setCount,
    name,
    setName,
  };
}

const counter = createComponent(Counter);
const state1 = counter.render(); // Effects run
state1.setCount(5); // Re-render, count effect runs
state1.setName("Bob"); // Re-render, name effect runs
```

**Requirements:**

- `useState(initialValue)` works correctly
- Multiple `useState` calls work
- `useEffect(fn, deps)` tracks dependencies
- Effects run when dependencies change
- Effects don't run when dependencies unchanged
- Cleanup functions run before next effect
- Must be called in same order every render

#### Exercise 2: Build More Hooks

Implement these hooks from scratch:

**A) useReducer:**

```javascript
function useReducer(reducer, initialState) {
  const [state, setState] = useState(initialState);

  function dispatch(action) {
    const newState = reducer(state, action);
    setState(newState);
  }

  return [state, dispatch];
}

// Usage:
const [state, dispatch] = useReducer(
  (state, action) => {
    switch (action.type) {
      case "INCREMENT":
        return {count: state.count + 1};
      default:
        return state;
    }
  },
  {count: 0}
);

dispatch({type: "INCREMENT"});
```

**B) useMemo:**

```javascript
function useMemo(factory, dependencies) {
  const component = currentComponent;
  const index = hookIndex++;

  if (!component.hooks[index]) {
    component.hooks[index] = {
      value: factory(),
      deps: dependencies,
    };
  } else {
    const hasChanged = !dependencies.every(
      (dep, i) => dep === component.hooks[index].deps[i]
    );

    if (hasChanged) {
      component.hooks[index] = {
        value: factory(),
        deps: dependencies,
      };
    }
  }

  return component.hooks[index].value;
}

// Usage:
const expensiveValue = useMemo(() => {
  console.log("Computing...");
  return someExpensiveOperation(a, b);
}, [a, b]);
```

**C) useCallback:**

```javascript
function useCallback(callback, dependencies) {
  return useMemo(() => callback, dependencies);
}

// Usage:
const memoizedCallback = useCallback(() => {
  doSomething(a, b);
}, [a, b]);
```

**D) useRef:**

```javascript
function useRef(initialValue) {
  const [ref] = useState({current: initialValue});
  return ref;
}

// Usage:
const countRef = useRef(0);
countRef.current++; // Doesn't trigger re-render
```

#### Exercise 3: Build Custom Hooks

Create reusable custom hooks:

**A) useLocalStorage:**

```javascript
function useLocalStorage(key, initialValue) {
  const [value, setValue] = useState(() => {
    const saved = localStorage.getItem(key);
    return saved !== null ? JSON.parse(saved) : initialValue;
  });

  useEffect(() => {
    localStorage.setItem(key, JSON.stringify(value));
  }, [key, value]);

  return [value, setValue];
}

// Usage:
const [theme, setTheme] = useLocalStorage("theme", "light");
```

**B) useDebounce:**

```javascript
function useDebounce(value, delay) {
  const [debouncedValue, setDebouncedValue] = useState(value);

  useEffect(() => {
    const timer = setTimeout(() => {
      setDebouncedValue(value);
    }, delay);

    return () => clearTimeout(timer);
  }, [value, delay]);

  return debouncedValue;
}

// Usage:
const [searchTerm, setSearchTerm] = useState("");
const debouncedSearch = useDebounce(searchTerm, 500);

useEffect(() => {
  // Search API with debouncedSearch
}, [debouncedSearch]);
```

**C) useFetch:**

```javascript
function useFetch(url) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    let cancelled = false;

    setLoading(true);
    fetch(url)
      .then((res) => res.json())
      .then((data) => {
        if (!cancelled) {
          setData(data);
          setLoading(false);
        }
      })
      .catch((err) => {
        if (!cancelled) {
          setError(err);
          setLoading(false);
        }
      });

    return () => {
      cancelled = true;
    };
  }, [url]);

  return {data, loading, error};
}

// Usage:
const {data, loading, error} = useFetch("/api/users");
```

#### Exercise 4: Compare Hooks Across Frameworks

Document how different frameworks implement hooks pattern:

| Hook         | Your Implementation | React         | Vue Composition API  | Solid.js       | Svelte         |
| ------------ | ------------------- | ------------- | -------------------- | -------------- | -------------- |
| **State**    | `useState`          | `useState`    | `ref` / `reactive`   | `createSignal` | Variables      |
| **Effect**   | `useEffect`         | `useEffect`   | `watchEffect`        | `createEffect` | `$:` statement |
| **Computed** | `useMemo`           | `useMemo`     | `computed`           | `createMemo`   | `$: derived`   |
| **Callback** | `useCallback`       | `useCallback` | -                    | -              | -              |
| **Ref**      | `useRef`            | `useRef`      | `ref` (different!)   | -              | `bind:`        |
| **Context**  | -                   | `useContext`  | `inject` / `provide` | `useContext`   | Context API    |

**Research:**

- How is Vue's Composition API similar to React hooks?
- How does Solid's approach differ?
- Why doesn't Svelte need hooks?
- What are the tradeoffs of each approach?

---

### Reflection Questions

After building:

1. **Hooks Internals:**

   - How do hooks store state between calls?
   - Why must hooks be called in the same order?
   - What breaks if you call hooks conditionally?
   - Why can't you call hooks in loops?

2. **Hooks vs Classes:**

   - What problems do hooks solve?
   - What are the benefits over classes?
   - Are there situations where classes are better?

3. **Custom Hooks:**

   - What makes something a custom hook?
   - When should you create a custom hook?
   - How do you design a good hook API?

4. **Framework Comparison:**
   - How does React's approach differ from Vue's?
   - Why did Solid take a different approach?
   - What can we learn from each?

---

## Section 7: Forms & User Input

### The Problem

Forms are deceptively complex in vanilla JavaScript:

```html
<input type="text" value="Hello" />
<!-- User types - but value attribute doesn't change!
     Browser shows new text but DOM attribute stays "Hello" -->
```

You need to:

- Keep input synchronized with state
- Validate as user types
- Handle different input types (text, checkbox, select, file)
- Show validation errors
- Submit forms
- Prevent invalid submissions
- Debounce expensive operations

**Vanilla JS gets messy fast:**

```javascript
const form = {
  email: "",
  password: "",
  agreeToTerms: false,
};

const emailInput = document.querySelector("#email");
const passwordInput = document.querySelector("#password");
const checkboxInput = document.querySelector("#agree");

// Sync input → state
emailInput.addEventListener("input", (e) => {
  form.email = e.target.value;
  validateEmail(); // Manual validation
});

passwordInput.addEventListener("input", (e) => {
  form.password = e.target.value;
  validatePassword(); // Manual validation
});

checkboxInput.addEventListener("change", (e) => {
  form.agreeToTerms = e.target.checked; // Different property!
  validateForm();
});

// Sync state → input (if state changes from code)
function updateInputs() {
  emailInput.value = form.email;
  passwordInput.value = form.password;
  checkboxInput.checked = form.agreeToTerms;
}
```

**How do frameworks make this easier?**

---

### Exploration Questions

#### Controlled vs Uncontrolled Inputs

**Scenario 1: Who Controls the Value?**

```javascript
// Uncontrolled: Browser controls value
<input type="text" defaultValue="Hello" />;
// Get value when needed: input.value

// Controlled: JavaScript controls value
const input = document.createElement("input");
input.value = state.text;
input.addEventListener("input", (e) => {
  state.text = e.target.value;
  input.value = state.text; // Keep in sync!
});
```

**Explore:**

- What's the difference?
- Why would you control the value?
- When is uncontrolled better?
- What happens if you set value but don't update it?
- Build both patterns

**Scenario 2: Two-Way Binding**

Some frameworks offer automatic two-way binding:

```javascript
// Vue
<input v-model="email" />
// Changes input → updates email
// Changes email → updates input

// How does this work behind the scenes?
```

**Explore:**

- What is two-way binding?
- How do you implement it in vanilla JS?
- What are the benefits?
- What are the drawbacks?
- Build a two-way binding system

#### Form State Management

**Scenario 3: Multiple Form Fields**

```javascript
// Bad: Separate event listener for each field
document.querySelector('#email').addEventListener('input', ...);
document.querySelector('#password').addEventListener('input', ...);
document.querySelector('#name').addEventListener('input', ...);
// Doesn't scale!

// Better: Generic handler
function handleChange(e) {
  const { name, value, type, checked } = e.target;
  form[name] = type === 'checkbox' ? checked : value;
}

// But how do you validate?
// How do you track which fields were touched?
// How do you show errors?
```

**Explore:**

- How do you create a reusable form handler?
- How do you track touched fields?
- How do you validate multiple fields?
- Build a form state manager

**Scenario 4: Validation Timing**

```javascript
// When should you validate?
// 1. On every keystroke? (annoying for user)
// 2. On blur (leave field)? (better UX)
// 3. On submit? (too late)
// 4. Combination?

function validateEmail(email) {
  return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
}

// Show error immediately? After first blur? After submit attempt?
```

**Explore:**

- When is the right time to validate?
- How do you show/hide errors gracefully?
- How do you validate async? (check if username taken)
- Build a validation timing system

#### Complex Input Types

**Scenario 5: Different Input Types Need Different Handling**

```javascript
// Text input
<input value={text} onInput={handleText} />

// Checkbox - uses 'checked' not 'value'
<input type="checkbox" checked={agreed} onChange={handleCheck} />

// Select
<select value={country} onChange={handleSelect}>
  <option value="us">USA</option>
  <option value="uk">UK</option>
</select>

// File - can't set value programmatically
<input type="file" onChange={handleFile} />
// How do you get the file? e.target.files

// Date - returns string, not Date object
<input type="date" value={dateStr} onChange={handleDate} />
```

**Explore:**

- How do you handle each input type consistently?
- How do you create a universal input handler?
- How do you handle file uploads?
- Build a multi-type input system

---

### Build It: Form Management System

#### Exercise 1: Build a Form Manager

Create a reusable form state manager:

```javascript
function createForm(initialValues) {
  let values = {...initialValues};
  let errors = {};
  let touched = {};
  let validators = {};
  const subscribers = new Set();

  function notify() {
    subscribers.forEach((fn) => fn(getState()));
  }

  function getState() {
    return {values, errors, touched};
  }

  function setValue(name, value) {
    values = {...values, [name]: value};

    // Validate if field has validator and was touched
    if (validators[name] && touched[name]) {
      const error = validators[name](value, values);
      errors = {...errors, [name]: error};
    }

    notify();
  }

  function setTouched(name, isTouched = true) {
    touched = {...touched, [name]: isTouched};

    // Validate on first touch
    if (isTouched && validators[name]) {
      const error = validators[name](values[name], values);
      errors = {...errors, [name]: error};
    }

    notify();
  }

  function setValidator(name, validator) {
    validators[name] = validator;
  }

  function validateAll() {
    const newErrors = {};

    for (const name in validators) {
      const error = validators[name](values[name], values);
      if (error) newErrors[name] = error;
    }

    errors = newErrors;

    // Mark all as touched
    touched = Object.keys(validators).reduce((acc, name) => {
      acc[name] = true;
      return acc;
    }, {});

    notify();
    return Object.keys(newErrors).length === 0;
  }

  function reset() {
    values = {...initialValues};
    errors = {};
    touched = {};
    notify();
  }

  function subscribe(callback) {
    subscribers.add(callback);
    callback(getState()); // Call immediately
    return () => subscribers.delete(callback);
  }

  return {
    getValue: (name) => values[name],
    setValue,
    setTouched,
    setValidator,
    validateAll,
    reset,
    subscribe,
    getState,
  };
}

// Usage:
const form = createForm({
  email: "",
  password: "",
  agreeToTerms: false,
});

// Set validators
form.setValidator("email", (value) => {
  if (!value) return "Email is required";
  if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(value)) return "Invalid email";
  return null;
});

form.setValidator("password", (value) => {
  if (!value) return "Password is required";
  if (value.length < 8) return "Password must be at least 8 characters";
  return null;
});

// Subscribe to changes
form.subscribe(({values, errors, touched}) => {
  console.log("Form state:", {values, errors, touched});
  // Update UI
});

// Handle input
emailInput.addEventListener("input", (e) => {
  form.setValue("email", e.target.value);
});

emailInput.addEventListener("blur", () => {
  form.setTouched("email");
});

// Handle submit
formElement.addEventListener("submit", (e) => {
  e.preventDefault();

  if (form.validateAll()) {
    console.log("Form valid! Submit:", form.getState().values);
  } else {
    console.log("Form invalid:", form.getState().errors);
  }
});
```

**Requirements:**

- Track values, errors, touched state
- Generic setValue for any field
- Validate on blur (first touch)
- Validate on change (after first touch)
- Validate all on submit
- Subscribe to state changes
- Reset form

#### Exercise 2: Build a Validation System

Create flexible validators:

```javascript
// Validator factory functions
const validators = {
  required:
    (message = "This field is required") =>
    (value) => {
      return value ? null : message;
    },

  minLength: (min, message) => (value) => {
    return value && value.length >= min
      ? null
      : message || `Must be at least ${min} characters`;
  },

  maxLength: (max, message) => (value) => {
    return value && value.length <= max
      ? null
      : message || `Must be at most ${max} characters`;
  },

  email:
    (message = "Invalid email address") =>
    (value) => {
      return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(value) ? null : message;
    },

  pattern: (regex, message) => (value) => {
    return regex.test(value) ? null : message;
  },

  matches: (fieldName, label) => (value, allValues) => {
    return value === allValues[fieldName] ? null : `Must match ${label}`;
  },

  custom: (validatorFn) => validatorFn,
};

// Compose validators
function composeValidators(...validators) {
  return (value, allValues) => {
    for (const validator of validators) {
      const error = validator(value, allValues);
      if (error) return error;
    }
    return null;
  };
}

// Usage:
const loginValidators = {
  email: composeValidators(
    validators.required("Email is required"),
    validators.email("Please enter a valid email")
  ),

  password: composeValidators(
    validators.required("Password is required"),
    validators.minLength(8, "Password must be at least 8 characters")
  ),

  confirmPassword: composeValidators(
    validators.required("Please confirm your password"),
    validators.matches("password", "password")
  ),
};

// Apply to form
for (const field in loginValidators) {
  form.setValidator(field, loginValidators[field]);
}
```

**Add async validators:**

```javascript
const asyncValidators = {
  uniqueEmail:
    (message = "Email already taken") =>
    async (value) => {
      // Debounce this!
      const available = await checkEmailAvailability(value);
      return available ? null : message;
    },

  uniqueUsername:
    (message = "Username already taken") =>
    async (value) => {
      const available = await checkUsernameAvailability(value);
      return available ? null : message;
    },
};

// Modify form to support async validation
form.setAsyncValidator("email", asyncValidators.uniqueEmail());
```

#### Exercise 3: Build Input Components

Create reusable input wrappers:

```javascript
function createInput(config) {
  const {name, type = "text", label, placeholder, form} = config;

  const container = document.createElement("div");
  container.className = "form-field";

  // Label
  if (label) {
    const labelEl = document.createElement("label");
    labelEl.htmlFor = name;
    labelEl.textContent = label;
    container.appendChild(labelEl);
  }

  // Input
  const input = document.createElement("input");
  input.type = type;
  input.name = name;
  input.id = name;
  input.placeholder = placeholder || "";

  // Sync form → input
  const unsubscribe = form.subscribe(({values, errors, touched}) => {
    if (type === "checkbox") {
      input.checked = values[name] || false;
    } else {
      input.value = values[name] || "";
    }

    // Show error if touched and has error
    if (touched[name] && errors[name]) {
      container.classList.add("has-error");
      errorSpan.textContent = errors[name];
      errorSpan.style.display = "block";
    } else {
      container.classList.remove("has-error");
      errorSpan.style.display = "none";
    }
  });

  // Sync input → form
  if (type === "checkbox") {
    input.addEventListener("change", (e) => {
      form.setValue(name, e.target.checked);
    });
  } else {
    input.addEventListener("input", (e) => {
      form.setValue(name, e.target.value);
    });
  }

  input.addEventListener("blur", () => {
    form.setTouched(name);
  });

  container.appendChild(input);

  // Error message
  const errorSpan = document.createElement("span");
  errorSpan.className = "error-message";
  errorSpan.style.display = "none";
  container.appendChild(errorSpan);

  return {
    element: container,
    destroy() {
      unsubscribe();
    },
  };
}

// Usage:
const emailInput = createInput({
  name: "email",
  type: "email",
  label: "Email Address",
  placeholder: "you@example.com",
  form,
});

document.querySelector("#form").appendChild(emailInput.element);
```

#### Exercise 4: Compare Framework Form Handling

Research and document how each framework handles forms:

**Create comparison table:**

| Feature              | Vanilla (Your System) | React                   | Vue 3            | Svelte           | Solid.js    |
| -------------------- | --------------------- | ----------------------- | ---------------- | ---------------- | ----------- |
| **Input Binding**    | Manual sync           | Controlled              | `v-model`        | `bind:value`     | Controlled  |
| **Validation**       | Custom                | Manual/libraries        | Manual/Vuelidate | Manual/libraries | Manual      |
| **Error Display**    | Manual                | Manual                  | Manual           | Manual           | Manual      |
| **Built-in Support** | Custom                | None                    | `v-model`        | `bind:`          | None        |
| **Form Libraries**   | -                     | Formik, React Hook Form | VeeValidate      | Svelte Forms Lib | Solid Forms |

**Research popular form libraries:**

- **React:** Formik, React Hook Form
- **Vue:** VeeValidate, Vuelidate
- **Svelte:** Svelte Forms Lib, Felte
- **Solid:** Solid Forms

**What do they provide?**

- Field-level validation
- Form-level validation
- Async validation
- Field arrays (dynamic fields)
- Dirty state tracking
- Submit count tracking
- Integration with UI libraries

#### Exercise 5: Build Complete Registration Form

Create a multi-step registration form:

**Steps:**

1. Account Info (email, password, confirm password)
2. Personal Info (name, phone, birthday)
3. Preferences (newsletter, notifications)
4. Review and Submit

**Requirements:**

- Use your form manager
- Navigate between steps
- Validate each step before proceeding
- Show progress indicator
- Save progress to localStorage
- Allow back navigation
- Show summary on review step
- Handle async submission
- Show success/error messages
- Can't proceed to next step if current invalid
- Can edit previous steps

---

### Reflection Questions

After building:

1. **Form Patterns:**

   - What's easier: controlled or uncontrolled inputs?
   - When is two-way binding beneficial?
   - What are the tradeoffs?

2. **Validation:**

   - When is the best time to validate?
   - How do you balance UX and validation?
   - How do you handle async validation without annoying the user?

3. **Framework Comparison:**

   - Which framework makes forms easiest?
   - Why do most frameworks not include form validation?
   - What patterns are universal?

4. **Deeper Understanding:**
   - How do form libraries optimize re-renders?
   - How do they handle field arrays?
   - What makes a good form library?

---

## Section 8: Data Fetching & Caching

### The Problem

Every component that fetches data looks like this:

```javascript
let user = null;
let loading = true;
let error = null;

async function fetchUser(id) {
  loading = true;
  error = null;

  try {
    const response = await fetch(`/api/users/${id}`);
    user = await response.json();
  } catch (e) {
    error = e.message;
  } finally {
    loading = false;
    render(); // Update UI
  }
}

fetchUser(123);
```

**Problems:**

- Duplicate code everywhere
- No caching (refetch same data repeatedly)
- Race conditions (what if ID changes mid-fetch?)
- No retry on failure
- No background refetching
- No optimistic updates
- No request deduplication

**You need a data fetching layer.** But how do frameworks solve this?

---

### Exploration Questions

#### Data Fetching Basics

**Scenario 1: The Race Condition**

```javascript
let currentUserId = 1;

async function loadUser(id) {
  currentUserId = id;
  const user = await fetchUser(id); // Takes 2 seconds
  displayUser(user);
}

// User rapidly changes ID
loadUser(1); // Request 1 starts
loadUser(2); // Request 2 starts (Request 1 still pending)

// Request 2 finishes first → shows user 2
// Request 1 finishes second → shows user 1 (WRONG!)
```

**Explore:**

- What is a race condition?
- How do you cancel previous requests?
- What is AbortController?
- How do you ensure latest request wins?
- Build race-condition-safe fetching

**Scenario 2: Request Deduplication**

```javascript
// Three components render at once
ComponentA: fetch("/api/posts"); // Request 1
ComponentB: fetch("/api/posts"); // Request 2 (duplicate!)
ComponentC: fetch("/api/posts"); // Request 3 (duplicate!)

// Should only make ONE request and share the result
```

**Explore:**

- How do you detect duplicate requests?
- How do you share one request across multiple callers?
- How do you handle errors in shared requests?
- Build request deduplication

#### Caching Strategies

**Scenario 3: Simple Cache**

```javascript
const cache = new Map();

async function fetchWithCache(url) {
  if (cache.has(url)) {
    return cache.get(url);
  }

  const data = await fetch(url).then((r) => r.json());
  cache.set(url, data);
  return data;
}

// But:
// - Cache never expires
// - No cache invalidation
// - Cache grows forever
```

**Explore:**

- How do you expire cache entries?
- How do you invalidate cache?
- How do you limit cache size?
- Build a cache with expiration

**Scenario 4: Stale-While-Revalidate**

```javascript
// 1. Return cached data immediately (even if stale)
// 2. Fetch fresh data in background
// 3. Update UI when fresh data arrives

async function fetchSWR(url) {
  // Return stale cache immediately
  if (cache.has(url)) {
    render(cache.get(url));
  }

  // Fetch fresh data
  const fresh = await fetch(url).then((r) => r.json());
  cache.set(url, fresh);
  render(fresh);
}
```

**Explore:**

- What is stale-while-revalidate?
- What are stale time vs cache time?
- When should you refetch?
- Build SWR pattern

#### Advanced Patterns

**Scenario 5: Optimistic Updates**

```javascript
// User clicks "like" button
async function likePost(postId) {
  // 1. Update UI immediately (optimistic)
  post.likes++;
  render();

  // 2. Update server
  try {
    await api.likePost(postId);
    // Success! Keep the optimistic update
  } catch (error) {
    // Failed! Rollback
    post.likes--;
    render();
    showError("Failed to like post");
  }
}
```

**Explore:**

- What are optimistic updates?
- How do you rollback on error?
- How do you handle concurrent updates?
- What if server responds differently than optimistic update?
- Build optimistic update system

**Scenario 6: Pagination & Infinite Scroll**

```javascript
// Load more as user scrolls
let page = 1;
let allPosts = [];

async function loadMore() {
  const posts = await fetch(`/api/posts?page=${page}`).then((r) => r.json());
  allPosts = [...allPosts, ...posts];
  page++;
  render();
}

// But:
// - What if page 2 request fails?
// - How do you know when there's no more data?
// - How do you invalidate all pages?
```

**Explore:**

- How do you handle paginated data?
- How do you implement infinite scroll?
- How do you invalidate paginated cache?
- Build pagination system

---

### Build It: Data Fetching Library

#### Exercise 1: Build Basic Fetcher with Cache

Create a data fetching system:

```javascript
function createFetcher() {
  const cache = new Map();
  const pending = new Map();

  async function fetch(url, options = {}) {
    const cacheKey = JSON.stringify({url, ...options});

    // Check cache
    if (cache.has(cacheKey)) {
      const cached = cache.get(cacheKey);
      if (!isCacheExpired(cached, options.cacheTime)) {
        return cached.data;
      }
    }

    // Check if request is already pending (deduplication)
    if (pending.has(cacheKey)) {
      return pending.get(cacheKey);
    }

    // Make request
    const promise = window
      .fetch(url, options)
      .then((res) => res.json())
      .then((data) => {
        // Cache it
        cache.set(cacheKey, {
          data,
          timestamp: Date.now(),
        });

        // Remove from pending
        pending.delete(cacheKey);

        return data;
      })
      .catch((error) => {
        // Remove from pending
        pending.delete(cacheKey);
        throw error;
      });

    // Store as pending
    pending.set(cacheKey, promise);

    return promise;
  }

  function isCacheExpired(cached, cacheTime = 5 * 60 * 1000) {
    return Date.now() - cached.timestamp > cacheTime;
  }

  function invalidate(url) {
    // Remove all cache entries matching URL
    for (const key of cache.keys()) {
      const parsed = JSON.parse(key);
      if (parsed.url === url) {
        cache.delete(key);
      }
    }
  }

  function invalidateAll() {
    cache.clear();
  }

  return {
    fetch,
    invalidate,
    invalidateAll,
  };
}

// Usage:
const fetcher = createFetcher();

const user = await fetcher.fetch("/api/users/123", {
  cacheTime: 60000, // 1 minute
});

// Later, invalidate
fetcher.invalidate("/api/users/123");
```

#### Exercise 2: Build Query Manager (React Query style)

Create a query management system:

```javascript
function createQueryManager() {
  const queries = new Map();
  const subscribers = new Map();

  function createQuery(key, fetcher, options = {}) {
    const queryKey = JSON.stringify(key);

    if (!queries.has(queryKey)) {
      queries.set(queryKey, {
        data: null,
        error: null,
        status: 'idle', // idle | loading | success | error
        fetchedAt: null,
        subscribers: new Set()
      });
    }

    const query = queries.get(queryKey);

    async function fetch() {
      query.status = 'loading';
      notifySubscribers(queryKey);

      try {
        const data = await fetcher();
        query.data = data;
        query.error = null;
        query.status = 'success';
        query.fetchedAt = Date.now();
      } catch (error) {
        query.error = error;
        query.status = 'error';
      }

      notifySubscribers(queryKey);
    }

    // Fetch if not fetched or stale
    const isStale = query.fetchedAt === null ||
      (Date.now() - query.fetchedAt > (options.staleTime || 0));

    if (isStale) {
      fetch();
    }

    return {
      data: query.data,
      error: query.error,
      status: query.status,
      isLoading: query.status === 'loading',
      isError: query.status === 'error',
      isSuccess: query.status === 'success',
      refetch: fetch
    };
  }

  function subscribe(key, callback) {
    const queryKey = JSON.stringify(key);

    if (!subscribers.has(queryKey)) {
      subscribers.set(queryKey, new Set());
    }

    subscribers.get(queryKey).add(callback);

    return () => {
      subscribers.get(queryKey).delete(callback);
    };
  }

  function notifySubscribers(queryKey) {
    const subs = subscribers.get(queryKey);
    if (subs) {
      const query = queries.get(queryKey);
      subs.forEach(callback => callback(query));
    }
  }

  function invalidateQuery(key) {
    const queryKey = JSON.stringify(key);
    const query = queries.get(queryKey);

    if (query) {
      query.fetchedAt = null; // Mark as stale
    }
  }

  return {
    createQuery,
    subscribe,
    invalidateQuery
  };
}

// Usage:
const queryManager = createQueryManager();

// Component A
const userQuery = queryManager.createQuery(
  ['user', 123],
  () => fetch('/api/users/123').then(r => r.json()),
  { staleTime: 60000 }
);

queryManager.subscribe(['user', 123], (query) => {
  console.log('Query updated:', query);
  // Re-render component
});

// Component B (reuses same query!)
const sameUserQuery = queryManager.createQuery(['user', 123], ...);

// Invalidate
queryManager.invalidateQuery(['user', 123]);
```

#### Exercise 3: Build Mutation System

Create a system for data mutations (create, update, delete):

```javascript
function createMutationManager(queryManager) {
  function createMutation(mutationFn, options = {}) {
    let status = "idle";
    let data = null;
    let error = null;

    async function mutate(variables, mutationOptions = {}) {
      status = "loading";

      // Optimistic update
      if (mutationOptions.optimisticData && mutationOptions.queryKey) {
        queryManager.setQueryData(
          mutationOptions.queryKey,
          mutationOptions.optimisticData
        );
      }

      try {
        data = await mutationFn(variables);
        status = "success";

        // On success callback
        if (options.onSuccess) {
          options.onSuccess(data, variables);
        }

        // Invalidate queries
        if (mutationOptions.invalidate) {
          mutationOptions.invalidate.forEach((key) => {
            queryManager.invalidateQuery(key);
          });
        }

        return data;
      } catch (e) {
        error = e;
        status = "error";

        // Rollback optimistic update
        if (mutationOptions.optimisticData && mutationOptions.queryKey) {
          queryManager.invalidateQuery(mutationOptions.queryKey);
        }

        // On error callback
        if (options.onError) {
          options.onError(e, variables);
        }

        throw e;
      }
    }

    return {
      mutate,
      get status() {
        return status;
      },
      get data() {
        return data;
      },
      get error() {
        return error;
      },
      get isLoading() {
        return status === "loading";
      },
      get isSuccess() {
        return status === "success";
      },
      get isError() {
        return status === "error";
      },
    };
  }

  return {createMutation};
}

// Usage:
const mutationManager = createMutationManager(queryManager);

const likeMutation = mutationManager.createMutation(
  (postId) => fetch(`/api/posts/${postId}/like`, {method: "POST"}),
  {
    onSuccess: (data, postId) => {
      console.log("Liked post:", postId);
    },
    onError: (error, postId) => {
      console.error("Failed to like:", error);
    },
  }
);

// Use it
async function handleLike(postId) {
  await likeMutation.mutate(postId, {
    optimisticData: {...post, likes: post.likes + 1},
    queryKey: ["post", postId],
    invalidate: [["posts"], ["post", postId]],
  });
}
```

#### Exercise 4: Compare Data Fetching Libraries

Research and compare popular data fetching libraries:

| Feature                   | Your System | React Query | SWR      | Apollo Client | RTK Query |
| ------------------------- | ----------- | ----------- | -------- | ------------- | --------- |
| **Caching**               | Yes         | Yes         | Yes      | Yes           | Yes       |
| **Auto Refetch**          | Manual      | Yes         | Yes      | Yes           | Yes       |
| **Optimistic Updates**    | Yes         | Yes         | Yes      | Yes           | Yes       |
| **Request Deduplication** | Yes         | Yes         | Yes      | Yes           | Yes       |
| **Pagination**            | Basic       | Advanced    | Advanced | Advanced      | Advanced  |
| **Framework**             | Agnostic    | React       | React    | Any           | Redux     |
| **Bundle Size**           | Small       | Medium      | Small    | Large         | Medium    |
| **GraphQL Support**       | No          | No          | No       | Yes           | No        |

**Study their APIs:**

**React Query:**

```javascript
const {data, isLoading, error} = useQuery(["users"], fetchUsers);
const mutation = useMutation(createUser);
```

**SWR:**

```javascript
const {data, error, isLoading} = useSWR("/api/users", fetcher);
```

**Apollo Client (GraphQL):**

```javascript
const {data, loading, error} = useQuery(GET_USERS);
const [createUser] = useMutation(CREATE_USER);
```

#### Exercise 5: Build Complete Data Layer

Create a full todo app with data fetching:

**Features:**

- Fetch todos from API
- Cache todos
- Optimistic add/update/delete
- Background refetch every 30 seconds
- Refetch on window focus
- Show loading/error states
- Retry failed requests
- Request deduplication
- Paginated loading (load more)

**Requirements:**

- Use your query manager
- Use your mutation manager
- Handle all edge cases
- Proper error handling
- Loading states everywhere
- No race conditions

---

### Reflection Questions

After building:

1. **Data Fetching Basics:**

   - Why is caching important?
   - What problems does it solve?
   - What problems does it create?

2. **Patterns:**

   - When should you use optimistic updates?
   - What is stale-while-revalidate good for?
   - When is request deduplication important?

3. **Framework Comparison:**

   - Why are data fetching libraries so popular?
   - What do they provide beyond fetch()?
   - When should you build your own vs use a library?

4. **Deeper Understanding:**
   - How do libraries prevent re-renders?
   - How do they handle race conditions?
   - What optimizations do they use?

---

# 🔵 ADVANCED PATTERNS (Production Features)

---

## Section 9: Server-Side Rendering & Hydration

### The Problem

Your SPA is fast once loaded, but the initial load is slow and search engines can't see your content:

```html
<!-- What browser receives (CSR): -->
<div id="root"></div>
<script src="bundle.js"></script>
<!-- Nothing until JavaScript executes! -->

<!-- What search engines see: -->
<!-- Empty page! -->
```

**Problems with Client-Side Rendering:**

- Blank page until JavaScript loads
- SEO issues (search engines may not wait)
- Slow Time to First Paint
- Poor performance on slow devices

**Solution: Server-Side Rendering (SSR)**

```html
<!-- What browser receives (SSR): -->
<div id="root">
  <h1>Hello World</h1>
  <p>Fully rendered HTML!</p>
</div>
<script src="bundle.js"></script>
<!-- Content is visible immediately! -->
```

But now you have a new problem: **Hydration**

---

### Exploration Questions

#### Understanding SSR

**Scenario 1: Rendering HTML on the Server**

```javascript
// Server (Node.js)
function renderToString(component) {
  // How do you turn a component into HTML string?
  // How do you execute component logic server-side?
  // How do you handle state?

  const html = /* somehow render component */;

  return `
    <!DOCTYPE html>
    <html>
      <body>
        <div id="root">${html}</div>
        <script src="/client.js"></script>
      </body>
    </html>
  `;
}
```

**Explore:**

- How do you render components to HTML string?
- What JavaScript can run on the server?
- What API calls happen server-side?
- How do you pass data to client?
- Build a server-side renderer

**Scenario 2: The Hydration Process**

```javascript
// Server rendered this:
<button>Count: 0</button>

// Client receives it:
// 1. HTML is visible (good!)
// 2. JavaScript loads
// 3. React "hydrates" - attaches event listeners
// 4. Button becomes interactive

// But what if:
// - Server rendered: "Count: 0"
// - Client hydrates with: "Count: 5"
// - Mismatch error!
```

**Explore:**

- What is hydration?
- Why not just replace the HTML?
- What are hydration mismatches?
- How do you debug mismatches?
- Build a hydration system

#### Rendering Strategies

**Scenario 3: Static vs Dynamic**

```javascript
// Static page (same for everyone)
/about
/blog/post-1
/blog/post-2

// Dynamic page (personalized)
/dashboard (needs user data)
/profile (needs auth)

// How do you handle both?
```

**Explore:**

- What is Static Site Generation (SSG)?
- What is Server-Side Rendering (SSR)?
- What is Incremental Static Regeneration (ISR)?
- When should you use each?
- Build all three strategies

**Scenario 4: Data Fetching Patterns**

```javascript
// Client-side (CSR)
useEffect(() => {
  fetch("/api/posts").then(setPosts);
}, []);
// Fetches after page load

// Server-side (SSR)
// Fetch during server render
const posts = await fetchPosts();
// Send HTML with data already in it

// Static (SSG)
// Fetch at build time
const posts = await fetchPosts();
// Generate HTML file
```

**Explore:**

- Where should data fetching happen?
- How do you fetch on the server?
- How do you pass data to client?
- How do you avoid fetching twice?
- Build data fetching for SSR

---

### Build It: SSR System

#### Exercise 1: Build Simple SSR

Create a basic server-side renderer:

```javascript
// shared/Component.js
function App({posts}) {
  return {
    type: "div",
    props: {
      children: [
        {
          type: "h1",
          props: {children: "My Blog"},
        },
        {
          type: "ul",
          props: {
            children: posts.map((post) => ({
              type: "li",
              props: {children: post.title},
            })),
          },
        },
      ],
    },
  };
}

// server.js
function renderToString(vnode) {
  if (typeof vnode === "string" || typeof vnode === "number") {
    return String(vnode);
  }

  const {type, props} = vnode;
  const {children, ...attrs} = props || {};

  // Build opening tag
  const attrsStr = Object.entries(attrs)
    .map(([key, value]) => `${key}="${value}"`)
    .join(" ");

  const openTag = attrsStr ? `<${type} ${attrsStr}>` : `<${type}>`;

  // Render children
  const childrenStr = Array.isArray(children)
    ? children.map(renderToString).join("")
    : children
    ? renderToString(children)
    : "";

  return `${openTag}${childrenStr}</${type}>`;
}

// Express server
app.get("*", async (req, res) => {
  // Fetch data
  const posts = await fetchPosts();

  // Render component to string
  const vnode = App({posts});
  const html = renderToString(vnode);

  // Send HTML
  res.send(`
    <!DOCTYPE html>
    <html>
      <head>
        <title>My Blog</title>
      </head>
      <body>
        <div id="root">${html}</div>
        <script>
          window.__INITIAL_DATA__ = ${JSON.stringify({posts})};
        </script>
        <script src="/client.js"></script>
      </body>
    </html>
  `);
});

// client.js
const initialData = window.__INITIAL_DATA__;
// Use initialData to hydrate without refetching
const vnode = App(initialData);
hydrate(vnode, document.getElementById("root"));
```

**Requirements:**

- Render components to HTML string
- Handle nested components
- Pass data from server to client
- Client uses server data (no refetch)

#### Exercise 2: Build Hydration

Create a hydration system:

```javascript
function hydrate(vnode, container) {
  // Don't destroy and recreate DOM
  // Instead, attach event listeners to existing DOM

  const domNode = container.firstChild;

  function hydrateNode(vnode, domNode) {
    if (typeof vnode === "string" || typeof vnode === "number") {
      // Text node - already rendered correctly
      return;
    }

    const {type, props} = vnode;
    const {children, onClick, ...attrs} = props || {};

    // Attach event listeners (server can't render these)
    if (onClick) {
      domNode.addEventListener("click", onClick);
    }

    // Hydrate children
    if (Array.isArray(children)) {
      let childDomNode = domNode.firstChild;
      children.forEach((childVnode) => {
        hydrateNode(childVnode, childDomNode);
        childDomNode = childDomNode.nextSibling;
      });
    } else if (children) {
      hydrateNode(children, domNode.firstChild);
    }
  }

  hydrateNode(vnode, domNode);
}

// Usage:
const initialData = window.__INITIAL_DATA__;
const vnode = App(initialData);
hydrate(vnode, document.getElementById("root"));
```

#### Exercise 3: Build Static Site Generator

Create a build-time HTML generator:

```javascript
// build.js
async function generateStaticSite() {
  const routes = [
    {path: "/", component: Home},
    {path: "/about", component: About},
    {path: "/blog/post-1", component: () => BlogPost({id: 1})},
    {path: "/blog/post-2", component: () => BlogPost({id: 2})},
  ];

  for (const route of routes) {
    // Fetch data at build time
    const data = await fetchDataForRoute(route.path);

    // Render component
    const vnode = route.component(data);
    const html = renderToString(vnode);

    // Write HTML file
    const filePath = path.join("dist", route.path, "index.html");
    await fs.mkdir(path.dirname(filePath), {recursive: true});
    await fs.writeFile(
      filePath,
      `
      <!DOCTYPE html>
      <html>
        <body>
          <div id="root">${html}</div>
          <script src="/client.js"></script>
        </body>
      </html>
    `
    );
  }
}

// Run at build time
generateStaticSite();
```

**Requirements:**

- Generate HTML files at build time
- One HTML file per route
- Include all data in HTML
- Works without JavaScript
- JavaScript enhances when loaded

#### Exercise 4: Compare SSR Frameworks

Research how frameworks handle SSR:

| Feature                | Your System | Next.js | Nuxt | SvelteKit | SolidStart |
| ---------------------- | ----------- | ------- | ---- | --------- | ---------- |
| **SSR**                | Basic       | Yes     | Yes  | Yes       | Yes        |
| **SSG**                | Basic       | Yes     | Yes  | Yes       | Yes        |
| **ISR**                | No          | Yes     | Yes  | No        | No         |
| **Streaming**          | No          | Yes     | Yes  | Yes       | Yes        |
| **API Routes**         | Manual      | Yes     | Yes  | Yes       | Yes        |
| **File-based Routing** | No          | Yes     | Yes  | Yes       | Yes        |

**Study their approaches:**

**Next.js:**

```javascript
// pages/posts/[id].js
export async function getServerSideProps({params}) {
  const post = await fetchPost(params.id);
  return {props: {post}};
}

export default function Post({post}) {
  return <div>{post.title}</div>;
}
```

**Nuxt:**

```javascript
// pages/posts/_id.vue
export default {
  async asyncData({params}) {
    const post = await fetchPost(params.id);
    return {post};
  },
};
```

**SvelteKit:**

```javascript
// routes/posts/[id]/+page.server.js
export async function load({params}) {
  const post = await fetchPost(params.id);
  return {post};
}
```

---

### Reflection Questions

After building:

1. **SSR Fundamentals:**

   - Why is SSR beneficial?
   - What are the tradeoffs?
   - When is CSR better than SSR?

2. **Hydration:**

   - What is hydration?
   - Why not just recreate the DOM?
   - What causes hydration mismatches?

3. **Rendering Strategies:**

   - When should you use SSG vs SSR?
   - What is ISR good for?
   - How do you choose?

4. **Framework Comparison:**
   - How do frameworks simplify SSR?
   - What do meta-frameworks provide?
   - Why is SSR so complex?

---

## Section 10: Virtual DOM & Reconciliation

### The Problem

Updating the real DOM is slow:

```javascript
// Naive approach: Recreate everything
function render() {
  container.innerHTML = ""; // Destroy everything!

  items.forEach((item) => {
    const li = document.createElement("li");
    li.textContent = item.text;
    li.addEventListener("click", () => handleClick(item));
    container.appendChild(li);
  });
}

// Problems:
// - Destroys and recreates all DOM nodes
// - Loses focus, scroll position
// - Event listeners need reattaching
// - Slow for large lists
```

**Solution: Only update what changed**

But how do you know what changed? **Virtual DOM!**

---

### Exploration Questions

**Scenario 1: What is a Virtual DOM?**

```javascript
// Real DOM
<div>
  <h1>Hello</h1>
  <p>World</p>
</div>

// Virtual DOM (JavaScript object representation)
{
  type: 'div',
  props: {
    children: [
      { type: 'h1', props: { children: 'Hello' } },
      { type: 'p', props: { children: 'World' } }
    ]
  }
}
```

**Explore:**

- What is a Virtual DOM?
- Why use a JavaScript object instead of real DOM?
- What are the benefits?
- What are the tradeoffs?
- Build a Virtual DOM representation

**Scenario 2: The Diffing Algorithm**

```javascript
// Old virtual DOM
{ type: 'div', children: [
  { type: 'p', children: 'Hello' },
  { type: 'p', children: 'World' }
]}

// New virtual DOM
{ type: 'div', children: [
  { type: 'p', children: 'Hello' },
  { type: 'p', children: 'Universe' } // Changed!
]}

// How do you find the difference?
// How do you generate minimal DOM updates?
```

**Explore:**

- How do you compare two virtual DOM trees?
- What algorithm finds differences efficiently?
- How do you generate patch operations?
- Build a diffing algorithm

**Scenario 3: Reconciliation**

```javascript
// Diff result:
[{type: "UPDATE", node: p2, newText: "Universe"}];

// Now apply to real DOM:
document.querySelector("p:nth-child(2)").textContent = "Universe";

// Instead of recreating everything!
```

**Explore:**

- What is reconciliation?
- How do you apply minimal changes to real DOM?
- How do you handle adding/removing nodes?
- Build a reconciliation system

**Scenario 4: Keys and List Reconciliation**

```javascript
// Without keys
["A", "B", "C"][("A", "C", "B", "D")][
  // Algorithm thinks: B changed to C, C changed to B, add D
  // 3 updates!

  // With keys
  ({key: "A"}, {key: "B"}, {key: "C"})
][({key: "A"}, {key: "C"}, {key: "B"}, {key: "D"})];
// Algorithm sees: C and B swapped, D added
// 1 move, 1 add!
```

**Explore:**

- Why do lists need keys?
- How do keys improve reconciliation?
- What makes a good key?
- Why not use array index as key?
- Build keyed reconciliation

---

### Build It: Virtual DOM System

#### Exercise 1: Build Virtual DOM & Diff

Create a complete Virtual DOM system:

```javascript
// 1. Create Virtual DOM nodes
function h(type, props, ...children) {
  return {
    type,
    props: props || {},
    children: children.flat(),
  };
}

// Usage:
const vdom = h(
  "div",
  {id: "app"},
  h("h1", null, "Hello"),
  h("p", null, "World")
);

// 2. Render virtual DOM to real DOM
function render(vnode) {
  if (typeof vnode === "string" || typeof vnode === "number") {
    return document.createTextNode(vnode);
  }

  const {type, props, children} = vnode;
  const element = document.createElement(type);

  // Set properties
  Object.entries(props).forEach(([key, value]) => {
    if (key.startsWith("on")) {
      const event = key.substring(2).toLowerCase();
      element.addEventListener(event, value);
    } else {
      element.setAttribute(key, value);
    }
  });

  // Render children
  children.forEach((child) => {
    element.appendChild(render(child));
  });

  return element;
}

// 3. Diff algorithm
function diff(oldVNode, newVNode) {
  // Different types - replace
  if (oldVNode.type !== newVNode.type) {
    return {type: "REPLACE", newVNode};
  }

  // Text nodes
  if (typeof oldVNode === "string" || typeof oldVNode === "number") {
    if (oldVNode !== newVNode) {
      return {type: "TEXT", newText: newVNode};
    }
    return null;
  }

  // Check props
  const propsPatches = diffProps(oldVNode.props, newVNode.props);

  // Check children
  const childrenPatches = diffChildren(oldVNode.children, newVNode.children);

  if (propsPatches.length === 0 && childrenPatches.length === 0) {
    return null; // No changes
  }

  return {
    type: "UPDATE",
    propsPatches,
    childrenPatches,
  };
}

function diffProps(oldProps, newProps) {
  const patches = [];

  // Check for changed/removed props
  for (const key in oldProps) {
    if (!(key in newProps)) {
      patches.push({type: "REMOVE_PROP", key});
    } else if (oldProps[key] !== newProps[key]) {
      patches.push({type: "SET_PROP", key, value: newProps[key]});
    }
  }

  // Check for new props
  for (const key in newProps) {
    if (!(key in oldProps)) {
      patches.push({type: "SET_PROP", key, value: newProps[key]});
    }
  }

  return patches;
}

function diffChildren(oldChildren, newChildren) {
  const patches = [];
  const maxLength = Math.max(oldChildren.length, newChildren.length);

  for (let i = 0; i < maxLength; i++) {
    if (!oldChildren[i]) {
      patches.push({type: "ADD", index: i, vnode: newChildren[i]});
    } else if (!newChildren[i]) {
      patches.push({type: "REMOVE", index: i});
    } else {
      const patch = diff(oldChildren[i], newChildren[i]);
      if (patch) {
        patches.push({type: "PATCH", index: i, patch});
      }
    }
  }

  return patches;
}

// 4. Apply patches
function patch(domNode, patches) {
  if (!patches) return domNode;

  if (patches.type === "REPLACE") {
    const newNode = render(patches.newVNode);
    domNode.replaceWith(newNode);
    return newNode;
  }

  if (patches.type === "TEXT") {
    domNode.textContent = patches.newText;
    return domNode;
  }

  if (patches.type === "UPDATE") {
    // Apply prop patches
    patches.propsPatches.forEach((propPatch) => {
      if (propPatch.type === "SET_PROP") {
        if (propPatch.key.startsWith("on")) {
          // Event listener
          const event = propPatch.key.substring(2).toLowerCase();
          domNode.addEventListener(event, propPatch.value);
        } else {
          domNode.setAttribute(propPatch.key, propPatch.value);
        }
      } else if (propPatch.type === "REMOVE_PROP") {
        domNode.removeAttribute(propPatch.key);
      }
    });

    // Apply children patches
    patches.childrenPatches.forEach((childPatch) => {
      if (childPatch.type === "ADD") {
        const newNode = render(childPatch.vnode);
        domNode.appendChild(newNode);
      } else if (childPatch.type === "REMOVE") {
        domNode.removeChild(domNode.childNodes[childPatch.index]);
      } else if (childPatch.type === "PATCH") {
        patch(domNode.childNodes[childPatch.index], childPatch.patch);
      }
    });
  }

  return domNode;
}

// Complete example:
let oldVDom = h(
  "div",
  {id: "app"},
  h("h1", null, "Count: 0"),
  h("button", {onClick: () => update()}, "Increment")
);

let container = render(oldVDom);
document.body.appendChild(container);

let count = 0;
function update() {
  count++;

  const newVDom = h(
    "div",
    {id: "app"},
    h("h1", null, `Count: ${count}`),
    h("button", {onClick: () => update()}, "Increment")
  );

  const patches = diff(oldVDom, newVDom);
  container = patch(container, patches);
  oldVDom = newVDom;
}
```

**Requirements:**

- Create virtual DOM nodes
- Render virtual DOM to real DOM
- Diff two virtual DOM trees
- Generate minimal patch operations
- Apply patches to real DOM
- Handle props and events
- Handle children

#### Exercise 2: Add Key-Based Reconciliation

Improve list handling with keys:

```javascript
function diffChildren(oldChildren, newChildren) {
  const oldKeyed = new Map();
  const newKeyed = new Map();

  // Collect keyed nodes
  oldChildren.forEach((child, i) => {
    const key = child.props?.key;
    if (key !== undefined) {
      oldKeyed.set(key, {child, index: i});
    }
  });

  newChildren.forEach((child, i) => {
    const key = child.props?.key;
    if (key !== undefined) {
      newKeyed.set(key, {child, index: i});
    }
  });

  const patches = [];

  // Process new children
  newChildren.forEach((newChild, newIndex) => {
    const key = newChild.props?.key;

    if (key !== undefined && oldKeyed.has(key)) {
      // Keyed node exists in old children
      const {child: oldChild, index: oldIndex} = oldKeyed.get(key);

      if (oldIndex !== newIndex) {
        patches.push({
          type: "MOVE",
          from: oldIndex,
          to: newIndex,
          key,
        });
      }

      const patch = diff(oldChild, newChild);
      if (patch) {
        patches.push({
          type: "PATCH",
          index: newIndex,
          patch,
        });
      }
    } else {
      // New node
      patches.push({
        type: "ADD",
        index: newIndex,
        vnode: newChild,
      });
    }
  });

  // Find removed nodes
  oldKeyed.forEach((value, key) => {
    if (!newKeyed.has(key)) {
      patches.push({
        type: "REMOVE",
        index: value.index,
        key,
      });
    }
  });

  return patches;
}

// Test with list reordering:
const list1 = [
  h("li", {key: "A"}, "Item A"),
  h("li", {key: "B"}, "Item B"),
  h("li", {key: "C"}, "Item C"),
];

const list2 = [
  h("li", {key: "C"}, "Item C"),
  h("li", {key: "A"}, "Item A"),
  h("li", {key: "D"}, "Item D"),
  h("li", {key: "B"}, "Item B"),
];

// Should generate minimal moves, not recreate all nodes
```

#### Exercise 3: Compare Virtual DOM Approaches

Research different reconciliation strategies:

| Approach            | Description              | Used By       | Pros                | Cons                |
| ------------------- | ------------------------ | ------------- | ------------------- | ------------------- |
| **Virtual DOM**     | Diff virtual trees       | React, Preact | Simple mental model | Memory overhead     |
| **Incremental DOM** | Diff while rendering     | -             | Low memory          | More complex        |
| **Fine-grained**    | Track at signal level    | Solid.js      | Fastest, no diffing | Different paradigm  |
| **Compiler**        | Generate optimal updates | Svelte        | No runtime overhead | Build step required |
| **Dirty checking**  | Check all bindings       | Angular 1     | Simple              | Poor performance    |

**Study frameworks:**

**React's Virtual DOM:**

- Fiber architecture
- Concurrent rendering
- Time-slicing

**Svelte's Compilation:**

- No virtual DOM
- Compiles to optimal updates
- No runtime overhead

**Solid's Fine-Grained:**

- No virtual DOM
- Signals track dependencies
- Surgical updates

#### Exercise 4: Benchmark Performance

Create performance tests:

```javascript
// Test 1: Create 1000 nodes
function benchmarkCreate() {
  const items = Array.from({length: 1000}, (_, i) => ({
    id: i,
    text: `Item ${i}`,
  }));

  console.time("Create 1000 nodes");
  const vdom = h(
    "ul",
    null,
    ...items.map((item) => h("li", {key: item.id}, item.text))
  );
  const dom = render(vdom);
  console.timeEnd("Create 1000 nodes");
}

// Test 2: Update 10 out of 1000 nodes
function benchmarkPartialUpdate() {
  // Initial render
  const items1 = Array.from({length: 1000}, (_, i) => ({
    id: i,
    text: `Item ${i}`,
  }));
  const vdom1 = createList(items1);
  const dom = render(vdom1);

  // Update 10 items
  const items2 = items1.map((item) =>
    item.id % 100 === 0 ? {...item, text: `Updated ${item.id}`} : item
  );

  console.time("Update 10/1000 nodes");
  const vdom2 = createList(items2);
  const patches = diff(vdom1, vdom2);
  patch(dom, patches);
  console.timeEnd("Update 10/1000 nodes");
}

// Test 3: Reorder large list
function benchmarkReorder() {
  const items1 = Array.from({length: 1000}, (_, i) => ({
    id: i,
    text: `Item ${i}`,
  }));
  const vdom1 = createList(items1);
  const dom = render(vdom1);

  // Reverse order
  const items2 = [...items1].reverse();

  console.time("Reorder 1000 nodes");
  const vdom2 = createList(items2);
  const patches = diff(vdom1, vdom2);
  patch(dom, patches);
  console.timeEnd("Reorder 1000 nodes");
}
```

**Compare your implementation to:**

- Native DOM manipulation
- React
- Vue
- Svelte
- Solid.js

---

### Reflection Questions

After building:

1. **Virtual DOM:**

   - What problem does Virtual DOM solve?
   - What are the tradeoffs?
   - When is Virtual DOM not needed?

2. **Reconciliation:**

   - How does diffing work?
   - Why are keys important?
   - What makes a good diffing algorithm?

3. **Alternatives:**

   - How does fine-grained reactivity compare?
   - How does compilation compare?
   - Which approach is "best"?

4. **Performance:**
   - Where is Virtual DOM slow?
   - Where is it fast?
   - How do frameworks optimize it?

---

## Section 11: Build Tools & Module Bundling

### The Problem

Your app has grown to 50+ files:

```
src/
├── components/
│   ├── Header.js
│   ├── Footer.js
│   ├── Button.js
│   └── ... 20 more
├── utils/
│   ├── api.js
│   ├── format.js
│   └── ... 10 more
├── styles/
│   ├── main.css
│   ├── components.css
│   └── ... 5 more
└── index.js
```

**Problems:**

- How do you load 50+ files in the browser?
- Each file is a separate HTTP request (slow!)
- Files have dependencies on each other
- Need to load in correct order
- CSS needs processing (vendor prefixes, minification)
- Modern JS features not supported in old browsers

**You need a build tool!**

---

### Exploration Questions

#### Module Systems

**Scenario 1: The Module Problem**

```javascript
// utils.js
function formatDate(date) { ... }

// app.js
// How do you use formatDate here?

// Option 1: Global variable (bad!)
window.formatDate = formatDate;

// Option 2: Module system
export function formatDate(date) { ... }
import { formatDate } from './utils.js';
```

**Explore:**

- What is a module system?
- What are CommonJS, ESM, AMD, UMD?
- How do imports/exports work?
- Why do we need bundlers?
- Build a simple module loader

**Scenario 2: Dependency Resolution**

```javascript
// a.js
import {b} from "./b.js";
import {c} from "./c.js";

// b.js
import {c} from "./c.js";

// c.js
export const c = "value";

// What order should files load?
// How do you prevent loading c.js twice?
// How do you detect circular dependencies?
```

**Explore:**

- How do you resolve dependencies?
- What is a dependency graph?
- How do you detect circular dependencies?
- Build a dependency resolver

#### Bundling Concepts

**Scenario 3: Code Splitting**

```javascript
// app.js (100 KB)
import "./home.js"; // 20 KB
import "./dashboard.js"; // 80 KB (rarely used!)

// User visits home page
// Downloads 100 KB but only needs 20 KB!

// Better: Code splitting
const home = import("./home.js"); // 20 KB
const dashboard = import("./dashboard.js"); // Lazy load when needed
```

**Explore:**

- What is code splitting?
- How do dynamic imports work?
- How do you split by route?
- Build code splitting system

**Scenario 4: Tree Shaking**

```javascript
// utils.js
export function used() { ... }
export function unused() { ... }

// app.js
import { used } from './utils.js';

// Bundle should only include used()!
// How does bundler know unused() is never called?
```

**Explore:**

- What is tree shaking?
- How do bundlers eliminate dead code?
- What prevents tree shaking?
- How do you enable tree shaking?

#### Transpilation & Polyfills

**Scenario 5: Modern JS in Old Browsers**

```javascript
// You write modern JS
const greet = (name = 'World') => `Hello ${name}`;
class User { ... }
const data = await fetch('/api');

// Old browsers don't support:
// - Arrow functions
// - Default parameters
// - Classes
// - Async/await

// Transpiler converts to ES5:
var greet = function(name) {
  if (name === undefined) name = 'World';
  return 'Hello ' + name;
};
```

**Explore:**

- What is transpilation?
- How does Babel work?
- What are polyfills?
- When do you need transpilation?
- Build a simple transpiler

---

### Build It: Module Bundler

#### Exercise 1: Build Basic Module Bundler

Create a simple bundler:

```javascript
const fs = require("fs");
const path = require("path");
const babel = require("@babel/core");

function createBundler(entry) {
  // Store modules by filepath
  const modules = new Map();
  let moduleId = 0;

  // Parse a module and its dependencies
  function parseModule(filepath) {
    if (modules.has(filepath)) {
      return modules.get(filepath);
    }

    const id = moduleId++;
    const dirname = path.dirname(filepath);
    const code = fs.readFileSync(filepath, "utf8");

    // Parse with Babel
    const ast = babel.parseSync(code, {
      sourceType: "module",
    });

    const dependencies = [];

    // Find all imports
    babel.traverse(ast, {
      ImportDeclaration({node}) {
        const importPath = node.source.value;
        const absolutePath = path.resolve(dirname, importPath);
        dependencies.push(absolutePath);
      },
    });

    // Transform to regular JS
    const {code: transformedCode} = babel.transformFromAstSync(ast, code, {
      presets: ["@babel/preset-env"],
    });

    const module = {
      id,
      filepath,
      dependencies,
      code: transformedCode,
    };

    modules.set(filepath, module);

    // Recursively parse dependencies
    dependencies.forEach((dep) => {
      parseModule(dep);
    });

    return module;
  }

  // Build dependency graph
  const entryModule = parseModule(entry);

  // Generate bundle
  function generateBundle() {
    const modulesArray = Array.from(modules.values());

    // Create module map
    const moduleMap = modulesArray
      .map((mod) => {
        return `
        ${mod.id}: {
          code: function(require, module, exports) {
            ${mod.code}
          },
          dependencies: ${JSON.stringify(
            mod.dependencies.map((dep) => modules.get(dep).id)
          )}
        }
      `;
      })
      .join(",\n");

    // Bundle template
    return `
      (function(modules) {
        const installedModules = {};
        
        function require(moduleId) {
          if (installedModules[moduleId]) {
            return installedModules[moduleId].exports;
          }
          
          const module = {
            exports: {}
          };
          
          installedModules[moduleId] = module;
          
          modules[moduleId].code(require, module, module.exports);
          
          return module.exports;
        }
        
        require(${entryModule.id});
      })({
        ${moduleMap}
      });
    `;
  }

  return {
    modules,
    bundle: generateBundle(),
  };
}

// Usage:
const bundler = createBundler("./src/index.js");
fs.writeFileSync("./dist/bundle.js", bundler.bundle);
```

**Requirements:**

- Parse entry file
- Find all imports
- Recursively parse dependencies
- Build dependency graph
- Generate single bundle file
- Handle circular dependencies

#### Exercise 2: Add Code Splitting

Implement dynamic imports:

```javascript
function handleDynamicImports(ast) {
  const dynamicImports = [];

  babel.traverse(ast, {
    CallExpression({node}) {
      if (
        node.callee.type === "Import" &&
        node.arguments.length === 1 &&
        node.arguments[0].type === "StringLiteral"
      ) {
        dynamicImports.push(node.arguments[0].value);
      }
    },
  });

  return dynamicImports;
}

function createChunks(modules, entryId) {
  const chunks = new Map();

  // Main chunk (entry + dependencies)
  const mainChunk = {
    id: "main",
    modules: new Set(),
  };

  function addToChunk(moduleId, chunk) {
    if (chunk.modules.has(moduleId)) return;

    chunk.modules.add(moduleId);
    const module = modules.get(moduleId);

    // Add sync dependencies
    module.dependencies.forEach((depId) => {
      if (!module.dynamicDependencies.includes(depId)) {
        addToChunk(depId, chunk);
      }
    });
  }

  addToChunk(entryId, mainChunk);
  chunks.set("main", mainChunk);

  // Create chunk for each dynamic import
  modules.forEach((module) => {
    module.dynamicDependencies.forEach((depId) => {
      const chunkId = `chunk-${depId}`;

      if (!chunks.has(chunkId)) {
        const chunk = {
          id: chunkId,
          modules: new Set(),
        };

        addToChunk(depId, chunk);
        chunks.set(chunkId, chunk);
      }
    });
  });

  return chunks;
}

// Generate multiple bundle files
function generateChunks(chunks) {
  return Array.from(chunks.values()).map((chunk) => {
    return {
      filename: `${chunk.id}.js`,
      code: generateChunkCode(chunk),
    };
  });
}
```

#### Exercise 3: Add Tree Shaking

Eliminate unused exports:

```javascript
function analyzeExports(ast) {
  const exports = new Set();

  babel.traverse(ast, {
    ExportNamedDeclaration({node}) {
      if (node.declaration) {
        if (node.declaration.declarations) {
          node.declaration.declarations.forEach((decl) => {
            exports.add(decl.id.name);
          });
        } else if (node.declaration.id) {
          exports.add(node.declaration.id.name);
        }
      }

      if (node.specifiers) {
        node.specifiers.forEach((spec) => {
          exports.add(spec.exported.name);
        });
      }
    },

    ExportDefaultDeclaration({node}) {
      exports.add("default");
    },
  });

  return exports;
}

function analyzeImports(ast) {
  const imports = new Map();

  babel.traverse(ast, {
    ImportDeclaration({node}) {
      const source = node.source.value;
      const imported = new Set();

      node.specifiers.forEach((spec) => {
        if (spec.type === "ImportSpecifier") {
          imported.add(spec.imported.name);
        } else if (spec.type === "ImportDefaultSpecifier") {
          imported.add("default");
        } else if (spec.type === "ImportNamespaceSpecifier") {
          imported.add("*");
        }
      });

      imports.set(source, imported);
    },
  });

  return imports;
}

function eliminateDeadCode(modules) {
  // Build usage graph
  const used = new Set();

  // Start from entry
  function markUsed(moduleId) {
    if (used.has(moduleId)) return;
    used.add(moduleId);

    const module = modules.get(moduleId);
    const imports = analyzeImports(module.ast);

    imports.forEach((importedNames, source) => {
      const depModule = modules.get(source);
      const exports = analyzeExports(depModule.ast);

      // Mark imported names as used
      importedNames.forEach((name) => {
        if (name === "*") {
          // Import everything
          markUsed(depModule.id);
        } else if (exports.has(name)) {
          // Mark this export as used
          depModule.usedExports.add(name);
          markUsed(depModule.id);
        }
      });
    });
  }

  markUsed(entryModule.id);

  // Remove unused modules
  modules.forEach((module, id) => {
    if (!used.has(id)) {
      modules.delete(id);
    }
  });

  // Remove unused exports
  modules.forEach((module) => {
    if (module.usedExports.size > 0) {
      removeUnusedExports(module.ast, module.usedExports);
    }
  });
}
```

#### Exercise 4: Compare Build Tools

Research popular build tools:

| Feature            | Your Bundler | Webpack    | Rollup    | Vite        | esbuild        | Parcel    |
| ------------------ | ------------ | ---------- | --------- | ----------- | -------------- | --------- |
| **Speed**          | Slow         | Medium     | Fast      | Very Fast   | Fastest        | Fast      |
| **Config**         | Code         | Complex    | Simple    | Minimal     | Minimal        | Zero      |
| **Code Splitting** | Basic        | Advanced   | Advanced  | Advanced    | Advanced       | Advanced  |
| **Tree Shaking**   | Basic        | Yes        | Best      | Yes         | Yes            | Yes       |
| **HMR**            | No           | Yes        | Plugin    | Built-in    | No             | Yes       |
| **Use Case**       | Learning     | Production | Libraries | Development | Speed critical | Beginners |

**Study their approaches:**

**Webpack:**

- Most configurable
- Loader system
- Plugin ecosystem
- Code splitting built-in

**Vite:**

- ESM in development
- No bundling in dev
- Lightning fast
- Rollup in production

**esbuild:**

- Written in Go
- Fastest bundler
- Limited plugins
- Growing ecosystem

#### Exercise 5: Build Development Server with HMR

Create dev server with Hot Module Replacement:

```javascript
const express = require("express");
const WebSocket = require("ws");
const chokidar = require("chokidar");

function createDevServer(bundler, options = {}) {
  const app = express();
  const wss = new WebSocket.Server({port: options.wsPort || 3001});

  // Serve bundle
  app.get("/bundle.js", (req, res) => {
    const bundle = bundler.bundle();
    res.type("application/javascript");
    res.send(bundle);
  });

  // Inject HMR client
  const hmrClient = `
    const ws = new WebSocket('ws://localhost:${options.wsPort || 3001}');
    
    ws.onmessage = (event) => {
      const data = JSON.parse(event.data);
      
      if (data.type === 'reload') {
        window.location.reload();
      } else if (data.type === 'update') {
        // Hot update
        const script = document.createElement('script');
        script.src = '/bundle.js?' + Date.now();
        document.body.appendChild(script);
      }
    };
  `;

  app.get("/hmr-client.js", (req, res) => {
    res.type("application/javascript");
    res.send(hmrClient);
  });

  // Watch files
  const watcher = chokidar.watch("./src", {
    ignored: /node_modules/,
  });

  watcher.on("change", (filepath) => {
    console.log(`File changed: ${filepath}`);

    // Rebuild
    bundler.rebuild();

    // Notify clients
    wss.clients.forEach((client) => {
      if (client.readyState === WebSocket.OPEN) {
        client.send(
          JSON.stringify({
            type: "update",
            file: filepath,
          })
        );
      }
    });
  });

  app.listen(options.port || 3000, () => {
    console.log(
      `Dev server running on http://localhost:${options.port || 3000}`
    );
  });
}

// Usage:
const bundler = createBundler("./src/index.js");
createDevServer(bundler, {port: 3000, wsPort: 3001});
```

---

### Reflection Questions

After building:

1. **Bundling Basics:**

   - Why do we need bundlers?
   - What problems do they solve?
   - What complexity do they add?

2. **Performance:**

   - How does code splitting help?
   - When is tree shaking important?
   - What are the tradeoffs?

3. **Tool Comparison:**

   - When would you use Webpack vs Vite?
   - When is zero-config better?
   - How do you choose?

4. **Future:**
   - Will we always need bundlers?
   - What is ESM native?
   - What's the trend?

---

## Section 12: Security & XSS Prevention

### The Problem

Your app accepts user input and displays it:

```javascript
const comment = getUserComment(); // "<script>alert('hacked')</script>"
container.innerHTML = comment; // XSS vulnerability!
// Script executes! User can steal data, cookies, etc.
```

**Security threats:**

- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- SQL Injection (backend)
- Sensitive data exposure
- Dependency vulnerabilities

**How do you build secure apps?**

---

### Exploration Questions

#### XSS Attacks

**Scenario 1: The innerHTML Trap**

```javascript
// User submits: <img src=x onerror="alert('XSS')">
const userInput = "<img src=x onerror=\"alert('XSS')\">";

// Vulnerable:
container.innerHTML = userInput; // XSS!

// Safe:
container.textContent = userInput; // Just text

// But what if you need HTML?
const safeName = escapeHtml(userInput);
container.innerHTML = `<div>${safeName}</div>`;
```

**Explore:**

- What is XSS?
- How do XSS attacks work?
- What's the difference between innerHTML and textContent?
- How do you sanitize HTML?
- Build HTML sanitizer

**Scenario 2: Different XSS Types**

```javascript
// Stored XSS (saved in database)
saveComment("<script>steal()</script>");
// Later displayed to all users

// Reflected XSS (in URL)
https://site.com/search?q=<script>steal()</script>
// Displayed back to user

// DOM-based XSS
const hash = location.hash;
element.innerHTML = hash; // Vulnerable!
```

**Explore:**

- What are XSS types?
- How do you prevent each?
- What is CSP (Content Security Policy)?
- Build XSS protection

**Scenario 3: URL Injection**

```javascript
// User input: javascript:alert('XSS')
const url = getUserInput();

// Vulnerable:
<a href="${url}">Click</a>;
// Clicking executes JavaScript!

// Safe:
const safeUrl = sanitizeUrl(url);
```

**Explore:**

- What protocols are dangerous?
- How do you validate URLs?
- What is allowlist vs denylist?
- Build URL validator

#### Framework Protection

**Scenario 4: How Frameworks Prevent XSS**

```javascript
// React (safe by default)
const name = "<script>alert('xss')</script>";
<div>{name}</div>
// Renders as text, not script!

// Vue (safe by default)
<div>{{ userInput }}</div>
// Automatically escaped

// Svelte (safe by default)
<div>{userInput}</div>
// Automatically escaped

// BUT: Can be bypassed!
// React:
<div dangerouslySetInnerHTML={{__html: userInput}} />
// Vue:
<div v-html="userInput"></div>
// Svelte:
<div>{@html userInput}</div>
```

**Explore:**

- How do frameworks escape by default?
- When do you need to bypass escaping?
- How do you do it safely?
- Build auto-escaping template system

#### CSRF Protection

**Scenario 5: Cross-Site Request Forgery**

```javascript
// User is logged into bank.com
// Visits evil.com which has:
<img src="https://bank.com/transfer?to=hacker&amount=1000" />;
// Transfers money using user's cookies!

// Protection: CSRF tokens
// Server sends token
const csrfToken = generateToken();

// Client includes token in requests
fetch("/transfer", {
  method: "POST",
  headers: {
    "X-CSRF-Token": csrfToken,
  },
  body: {to: "recipient", amount: 100},
});
```

**Explore:**

- What is CSRF?
- How does CSRF token work?
- What is SameSite cookie attribute?
- Build CSRF protection

---

### Build It: Security Layer

#### Exercise 1: Build HTML Sanitizer

Create safe HTML renderer:

```javascript
function sanitizeHtml(html) {
  // Parse HTML
  const doc = new DOMParser().parseFromString(html, "text/html");

  // Allowlist of safe tags
  const allowedTags = [
    "p",
    "br",
    "strong",
    "em",
    "u",
    "a",
    "ul",
    "ol",
    "li",
    "h1",
    "h2",
    "h3",
    "h4",
    "h5",
    "h6",
    "blockquote",
    "code",
    "pre",
  ];

  // Allowlist of safe attributes
  const allowedAttrs = {
    a: ["href", "title"],
    img: ["src", "alt"],
    "*": ["class"], // All tags can have class
  };

  function sanitizeNode(node) {
    // Remove if not allowed tag
    if (node.nodeType === Node.ELEMENT_NODE) {
      const tagName = node.tagName.toLowerCase();

      if (!allowedTags.includes(tagName)) {
        node.remove();
        return;
      }

      // Remove disallowed attributes
      Array.from(node.attributes).forEach((attr) => {
        const attrName = attr.name.toLowerCase();
        const allowed = allowedAttrs[tagName] || [];
        const globalAllowed = allowedAttrs["*"] || [];

        if (!allowed.includes(attrName) && !globalAllowed.includes(attrName)) {
          node.removeAttribute(attrName);
        }

        // Special handling for href
        if (attrName === "href") {
          const href = attr.value;
          if (!isUrlSafe(href)) {
            node.removeAttribute("href");
          }
        }
      });

      // Remove event handlers
      Array.from(node.attributes).forEach((attr) => {
        if (attr.name.toLowerCase().startsWith("on")) {
          node.removeAttribute(attr.name);
        }
      });

      // Recursively sanitize children
      Array.from(node.childNodes).forEach(sanitizeNode);
    }
  }

  function isUrlSafe(url) {
    try {
      const parsed = new URL(url, window.location.origin);
      const protocol = parsed.protocol;

      // Only allow safe protocols
      return ["http:", "https:", "mailto:"].includes(protocol);
    } catch {
      return false;
    }
  }

  Array.from(doc.body.childNodes).forEach(sanitizeNode);

  return doc.body.innerHTML;
}

// Usage:
const userHtml = `
  <p>Hello <strong>world</strong></p>
  <script>alert('xss')</script>
  <img src=x onerror="alert('xss')">
  <a href="javascript:alert('xss')">Click</a>
  <a href="https://safe.com">Safe link</a>
`;

const safeHtml = sanitizeHtml(userHtml);
// Result:
// <p>Hello <strong>world</strong></p>
// <a href="https://safe.com">Safe link</a>
```

**Requirements:**

- Parse HTML safely
- Allowlist safe tags only
- Remove dangerous attributes
- Remove event handlers
- Validate URLs
- Handle nested elements

#### Exercise 2: Build Auto-Escaping Template System

Create templates that escape by default:

```javascript
function createTemplate(strings, ...values) {
  return {
    toString() {
      return strings.reduce((result, string, i) => {
        const value = values[i - 1];
        const escaped = escapeHtml(value);
        return result + escaped + string;
      });
    },

    toHtmlString() {
      return this.toString();
    },
  };
}

function escapeHtml(unsafe) {
  if (unsafe == null) return "";

  return String(unsafe)
    .replace(/&/g, "&amp;")
    .replace(/</g, "&lt;")
    .replace(/>/g, "&gt;")
    .replace(/"/g, "&quot;")
    .replace(/'/g, "&#039;");
}

function html(strings, ...values) {
  return createTemplate(strings, ...values);
}

// Mark as safe (already sanitized)
function safe(htmlString) {
  return {
    __safe: true,
    toString() {
      return htmlString;
    },
  };
}

function render(template) {
  return template.toString();
}

// Usage:
const name = "<script>alert('xss')</script>";
const greeting = html`<div>Hello ${name}</div>`;

console.log(render(greeting));
// <div>Hello &lt;script&gt;alert('xss')&lt;/script&gt;</div>

// Explicitly mark as safe
const safeHtml = safe("<strong>Bold</strong>");
const content = html`<div>${safeHtml}</div>`;

console.log(render(content));
// <div><strong>Bold</strong></div>
```

#### Exercise 3: Build CSP Helper

Create Content Security Policy generator:

```javascript
function createCspPolicy(options = {}) {
  const directives = [];

  // default-src
  if (options.defaultSrc) {
    directives.push(`default-src ${options.defaultSrc.join(" ")}`);
  } else {
    directives.push("default-src 'self'");
  }

  // script-src
  if (options.scriptSrc) {
    const sources = options.scriptSrc;

    if (options.allowInlineScripts) {
      sources.push("'unsafe-inline'");
    }
    if (options.allowEval) {
      sources.push("'unsafe-eval'");
    }
    if (options.scriptNonce) {
      sources.push(`'nonce-${options.scriptNonce}'`);
    }

    directives.push(`script-src ${sources.join(" ")}`);
  }

  // style-src
  if (options.styleSrc) {
    const sources = options.styleSrc;

    if (options.allowInlineStyles) {
      sources.push("'unsafe-inline'");
    }

    directives.push(`style-src ${sources.join(" ")}`);
  }

  // img-src
  if (options.imgSrc) {
    directives.push(`img-src ${options.imgSrc.join(" ")}`);
  }

  // connect-src (APIs)
  if (options.connectSrc) {
    directives.push(`connect-src ${options.connectSrc.join(" ")}`);
  }

  // font-src
  if (options.fontSrc) {
    directives.push(`font-src ${options.fontSrc.join(" ")}`);
  }

  // frame-src
  if (options.frameSrc) {
    directives.push(`frame-src ${options.frameSrc.join(" ")}`);
  }

  return directives.join("; ");
}

// Usage:
const csp = createCspPolicy({
  defaultSrc: ["'self'"],
  scriptSrc: ["'self'", "https://cdn.example.com"],
  styleSrc: ["'self'", "https://fonts.googleapis.com"],
  imgSrc: ["'self'", "data:", "https:"],
  connectSrc: ["'self'", "https://api.example.com"],
  fontSrc: ["'self'", "https://fonts.gstatic.com"],
  frameSrc: ["'none'"],
});

// Set in HTTP header:
// Content-Security-Policy: default-src 'self'; script-src 'self' https://cdn.example.com; ...

// Or in HTML:
// <meta http-equiv="Content-Security-Policy" content="...">
```

#### Exercise 4: Build Security Checklist Tool

Create security audit tool:

```javascript
function auditSecurity(code) {
  const issues = [];

  // Check for innerHTML usage
  if (code.includes("innerHTML")) {
    issues.push({
      severity: "high",
      type: "xss",
      message: "innerHTML usage detected - potential XSS",
      line: findLine(code, "innerHTML"),
    });
  }

  // Check for eval usage
  if (code.includes("eval(")) {
    issues.push({
      severity: "critical",
      type: "code-injection",
      message: "eval() usage detected - avoid eval",
      line: findLine(code, "eval("),
    });
  }

  // Check for dangerouslySetInnerHTML
  if (code.includes("dangerouslySetInnerHTML")) {
    issues.push({
      severity: "high",
      type: "xss",
      message: "dangerouslySetInnerHTML usage - ensure input is sanitized",
      line: findLine(code, "dangerouslySetInnerHTML"),
    });
  }

  // Check for document.write
  if (code.includes("document.write")) {
    issues.push({
      severity: "medium",
      type: "xss",
      message: "document.write usage - prefer safe DOM methods",
      line: findLine(code, "document.write"),
    });
  }

  // Check for window.location usage
  if (code.includes("window.location.hash") || code.includes("location.hash")) {
    issues.push({
      severity: "medium",
      type: "xss",
      message: "Using location.hash - ensure proper sanitization",
      line: findLine(code, "location.hash"),
    });
  }

  return {
    issues,
    score: calculateScore(issues),
    recommendations: generateRecommendations(issues),
  };
}

function calculateScore(issues) {
  const weights = {
    critical: 25,
    high: 10,
    medium: 5,
    low: 2,
  };

  const deductions = issues.reduce((total, issue) => {
    return total + weights[issue.severity];
  }, 0);

  return Math.max(0, 100 - deductions);
}

// Usage:
const code = fs.readFileSync("./app.js", "utf8");
const audit = auditSecurity(code);

console.log(`Security Score: ${audit.score}/100`);
console.log("\nIssues found:");
audit.issues.forEach((issue) => {
  console.log(`  [${issue.severity}] ${issue.message} (line ${issue.line})`);
});
```

#### Exercise 5: Compare Framework Security

Research how frameworks handle security:

| Feature                   | React                     | Vue 3    | Svelte    | Solid.js    |
| ------------------------- | ------------------------- | -------- | --------- | ----------- |
| **Default Escaping**      | Yes                       | Yes      | Yes       | Yes         |
| **Bypass Escaping**       | `dangerouslySetInnerHTML` | `v-html` | `{@html}` | `innerHTML` |
| **URL Sanitization**      | Manual                    | Manual   | Manual    | Manual      |
| **CSP Support**           | Yes                       | Yes      | Yes       | Yes         |
| **Built-in Sanitization** | No                        | No       | No        | No          |
| **XSS Protection**        | Good                      | Good     | Good      | Good        |

**Best practices across frameworks:**

- Always escape user input
- Use CSP headers
- Validate URLs
- Sanitize HTML if needed
- Avoid eval, Function constructor
- Use HTTPS only
- Validate on server too
- Keep dependencies updated

---

### Reflection Questions

After building:

1. **XSS Prevention:**

   - Why is XSS so common?
   - How do frameworks help?
   - What can still go wrong?

2. **Security Layers:**

   - What is defense in depth?
   - Where should validation happen?
   - Client-side vs server-side?

3. **Framework Comparison:**

   - Do frameworks make security easier?
   - What are common pitfalls?
   - What's the developer's responsibility?

4. **Best Practices:**
   - What should ALWAYS be done?
   - What are acceptable risks?
   - How do you stay secure?

---

## Section 13: Testing Framework Applications

### The Problem

You built a complex app. How do you know it works?

```javascript
// Manual testing:
// 1. Open browser
// 2. Click button
// 3. Check if it works
// 4. Repeat for every feature
// 5. Repeat after every change
// Time-consuming! Error-prone!

// Better: Automated tests
test("button increments count", () => {
  const button = render(<Counter />);
  button.click();
  expect(count).toBe(1);
});
```

**Types of tests:**

- Unit tests (test functions)
- Component tests (test components)
- Integration tests (test features)
- E2E tests (test full user flows)

**How do you test framework applications?**

---

### Exploration Questions

#### Testing Fundamentals

**Scenario 1: What Makes Code Testable?**

```javascript
// Hard to test (side effects)
function saveUser() {
  const name = document.querySelector("#name").value;
  fetch("/api/users", {
    method: "POST",
    body: JSON.stringify({name}),
  });
}

// Easy to test (pure function)
function createUser(name) {
  return {name, createdAt: Date.now()};
}

test("createUser creates user object", () => {
  const user = createUser("Alice");
  expect(user.name).toBe("Alice");
  expect(user.createdAt).toBeDefined();
});
```

**Explore:**

- What makes code testable?
- What are pure functions?
- How do you test side effects?
- How do you mock dependencies?
- Build a test framework

**Scenario 2: Component Testing**

```javascript
// Component
function Counter() {
  let count = 0;

  return {
    increment() {
      count++;
    },
    decrement() {
      count--;
    },
    getCount() {
      return count;
    },
  };
}

// How do you test this?
test("counter increments", () => {
  const counter = Counter();
  counter.increment();
  expect(counter.getCount()).toBe(1);
});

// But what about DOM rendering?
// What about user interactions?
```

**Explore:**

- How do you test components?
- How do you simulate user interactions?
- How do you check DOM output?
- Build component testing utilities

#### Test Types

**Scenario 3: The Testing Pyramid**

```
       /\
      /E2E\      ← Few, slow, high confidence
     /------\
    /  INT   \   ← Some, medium speed
   /----------\
  /   UNIT     \ ← Many, fast, low confidence
 /--------------\
```

**Explore:**

- What is the testing pyramid?
- When do you use each test type?
- How do you balance tests?
- Build all three types

**Scenario 4: Mocking**

```javascript
// Code that fetches data
async function loadUser(id) {
  const response = await fetch(`/api/users/${id}`);
  return response.json();
}

// How do you test without making real API calls?
test("loadUser fetches user", async () => {
  // Mock fetch
  global.fetch = jest.fn(() =>
    Promise.resolve({
      json: () => Promise.resolve({id: 1, name: "Alice"}),
    })
  );

  const user = await loadUser(1);
  expect(user.name).toBe("Alice");
});
```

**Explore:**

- What is mocking?
- When should you mock?
- When should you NOT mock?
- Build a mocking system

---

### Build It: Testing Framework

#### Exercise 1: Build Simple Test Framework

Create a test runner:

```javascript
class TestFramework {
  constructor() {
    this.tests = [];
    this.beforeEachFns = [];
    this.afterEachFns = [];
  }

  test(description, fn) {
    this.tests.push({description, fn});
  }

  beforeEach(fn) {
    this.beforeEachFns.push(fn);
  }

  afterEach(fn) {
    this.afterEachFns.push(fn);
  }

  async run() {
    console.log("\n🧪 Running tests...\n");

    let passed = 0;
    let failed = 0;

    for (const test of this.tests) {
      // Run beforeEach hooks
      for (const fn of this.beforeEachFns) {
        await fn();
      }

      try {
        await test.fn();
        console.log(`✅ ${test.description}`);
        passed++;
      } catch (error) {
        console.log(`❌ ${test.description}`);
        console.log(`   ${error.message}`);
        failed++;
      }

      // Run afterEach hooks
      for (const fn of this.afterEachFns) {
        await fn();
      }
    }

    console.log(`\n📊 Results: ${passed} passed, ${failed} failed`);

    return {passed, failed, total: this.tests.length};
  }
}

// Assertion library
class Expect {
  constructor(actual) {
    this.actual = actual;
  }

  toBe(expected) {
    if (this.actual !== expected) {
      throw new Error(
        `Expected ${JSON.stringify(expected)} but got ${JSON.stringify(
          this.actual
        )}`
      );
    }
  }

  toEqual(expected) {
    if (JSON.stringify(this.actual) !== JSON.stringify(expected)) {
      throw new Error(
        `Expected ${JSON.stringify(expected)} but got ${JSON.stringify(
          this.actual
        )}`
      );
    }
  }

  toBeTruthy() {
    if (!this.actual) {
      throw new Error(`Expected truthy but got ${this.actual}`);
    }
  }

  toContain(item) {
    if (!this.actual.includes(item)) {
      throw new Error(`Expected array to contain ${item}`);
    }
  }

  toThrow() {
    try {
      this.actual();
      throw new Error("Expected function to throw");
    } catch (error) {
      // Expected
    }
  }
}

function expect(actual) {
  return new Expect(actual);
}

// Usage:
const framework = new TestFramework();

framework.beforeEach(() => {
  console.log("  Setting up test...");
});

framework.test("addition works", () => {
  expect(1 + 1).toBe(2);
});

framework.test("arrays are equal", () => {
  expect([1, 2, 3]).toEqual([1, 2, 3]);
});

framework.test("string contains substring", () => {
  expect("hello world").toContain("world");
});

framework.run();
```

#### Exercise 2: Build Component Testing Utilities

Create DOM testing helpers:

```javascript
function createTestEnvironment() {
  // Create clean DOM for each test
  const container = document.createElement("div");
  document.body.appendChild(container);

  function cleanup() {
    document.body.removeChild(container);
  }

  function render(component) {
    const element = component.render();
    container.appendChild(element);

    return {
      container,
      element,

      // Query helpers
      getByText(text) {
        return Array.from(container.querySelectorAll("*")).find(
          (el) => el.textContent === text
        );
      },

      getByTestId(testId) {
        return container.querySelector(`[data-testid="${testId}"]`);
      },

      getByRole(role) {
        return container.querySelector(`[role="${role}"]`);
      },

      // Event helpers
      async click(element) {
        element.click();
        await waitForUpdate();
      },

      async type(element, text) {
        element.value = text;
        element.dispatchEvent(new Event("input", {bubbles: true}));
        await waitForUpdate();
      },

      // Wait helpers
      async waitForUpdate() {
        return new Promise((resolve) => setTimeout(resolve, 0));
      },

      async waitFor(callback, {timeout = 1000} = {}) {
        const startTime = Date.now();

        while (Date.now() - startTime < timeout) {
          try {
            const result = callback();
            if (result) return result;
          } catch (e) {
            // Keep waiting
          }

          await new Promise((resolve) => setTimeout(resolve, 50));
        }

        throw new Error("Timeout waiting for condition");
      },
    };
  }

  return {render, cleanup};
}

// Usage:
test("Counter component increments", async () => {
  const {render, cleanup, click, getByText} = createTestEnvironment();

  try {
    const counter = createCounter();
    const {element} = render(counter);

    const button = getByText("Increment");
    await click(button);

    const count = getByText("Count: 1");
    expect(count).toBeTruthy();
  } finally {
    cleanup();
  }
});
```

#### Exercise 3: Build Mock System

Create mocking utilities:

```javascript
class Mock {
  constructor() {
    this.calls = [];
    this.returnValue = undefined;
    this.implementation = null;
  }

  mockReturnValue(value) {
    this.returnValue = value;
    return this;
  }

  mockImplementation(fn) {
    this.implementation = fn;
    return this;
  }

  mockResolvedValue(value) {
    this.implementation = () => Promise.resolve(value);
    return this;
  }

  mockRejectedValue(error) {
    this.implementation = () => Promise.reject(error);
    return this;
  }

  call(...args) {
    this.calls.push(args);

    if (this.implementation) {
      return this.implementation(...args);
    }

    return this.returnValue;
  }

  toHaveBeenCalled() {
    return this.calls.length > 0;
  }

  toHaveBeenCalledTimes(times) {
    return this.calls.length === times;
  }

  toHaveBeenCalledWith(...args) {
    return this.calls.some(
      (call) => JSON.stringify(call) === JSON.stringify(args)
    );
  }
}

function createMock() {
  const mock = new Mock();
  const fn = (...args) => mock.call(...args);

  // Copy methods to function
  fn.mockReturnValue = mock.mockReturnValue.bind(mock);
  fn.mockImplementation = mock.mockImplementation.bind(mock);
  fn.mockResolvedValue = mock.mockResolvedValue.bind(mock);
  fn.mockRejectedValue = mock.mockRejectedValue.bind(mock);
  fn.toHaveBeenCalled = mock.toHaveBeenCalled.bind(mock);
  fn.toHaveBeenCalledTimes = mock.toHaveBeenCalledTimes.bind(mock);
  fn.toHaveBeenCalledWith = mock.toHaveBeenCalledWith.bind(mock);

  return fn;
}

// Usage:
test("API call is made correctly", async () => {
  const mockFetch = createMock();
  mockFetch.mockResolvedValue({
    json: () => Promise.resolve({id: 1, name: "Alice"}),
  });

  global.fetch = mockFetch;

  const user = await loadUser(1);

  expect(user.name).toBe("Alice");
  expect(mockFetch.toHaveBeenCalledTimes(1));
  expect(mockFetch.toHaveBeenCalledWith("/api/users/1"));
});
```

#### Exercise 4: Compare Testing Libraries

Research popular testing tools:

| Tool                | Type             | Framework        | Features                    |
| ------------------- | ---------------- | ---------------- | --------------------------- |
| **Jest**            | Unit/Integration | Any              | Snapshot, mocking, coverage |
| **Vitest**          | Unit/Integration | Vite             | Fast, ESM native            |
| **Testing Library** | Component        | React/Vue/Svelte | User-centric queries        |
| **Cypress**         | E2E              | Any              | Browser automation          |
| **Playwright**      | E2E              | Any              | Multi-browser               |
| **Puppeteer**       | E2E              | Any              | Chrome automation           |

**Study their approaches:**

**React Testing Library:**

```javascript
import {render, screen, fireEvent} from "@testing-library/react";

test("button increments count", () => {
  render(<Counter />);

  const button = screen.getByRole("button", {name: /increment/i});
  fireEvent.click(button);

  expect(screen.getByText("Count: 1")).toBeInTheDocument();
});
```

**Cypress:**

```javascript
describe("Counter", () => {
  it("increments count", () => {
    cy.visit("/counter");
    cy.contains("Increment").click();
    cy.contains("Count: 1");
  });
});
```

#### Exercise 5: Write Complete Test Suite

Test a todo app thoroughly:

```javascript
describe("Todo App", () => {
  describe("Unit Tests", () => {
    test("createTodo creates todo object", () => {
      const todo = createTodo("Buy milk");
      expect(todo).toEqual({
        id: expect.any(String),
        text: "Buy milk",
        done: false,
      });
    });

    test("toggleTodo toggles done status", () => {
      const todo = {id: "1", text: "Task", done: false};
      const toggled = toggleTodo(todo);
      expect(toggled.done).toBe(true);
    });
  });

  describe("Component Tests", () => {
    test("renders todo list", () => {
      const todos = [
        {id: "1", text: "Task 1", done: false},
        {id: "2", text: "Task 2", done: true},
      ];

      const {getByText} = render(TodoList, {todos});

      expect(getByText("Task 1")).toBeTruthy();
      expect(getByText("Task 2")).toBeTruthy();
    });

    test("adds new todo", async () => {
      const {getByTestId, getByText, type, click} = render(TodoApp);

      await type(getByTestId("todo-input"), "New task");
      await click(getByText("Add"));

      expect(getByText("New task")).toBeTruthy();
    });

    test("toggles todo", async () => {
      const todos = [{id: "1", text: "Task", done: false}];
      const {getByTestId, click} = render(TodoList, {todos});

      await click(getByTestId("todo-checkbox-1"));

      expect(getByTestId("todo-checkbox-1").checked).toBe(true);
    });
  });

  describe("Integration Tests", () => {
    test("todo persists to localStorage", async () => {
      const {getByTestId, type, click} = render(TodoApp);

      await type(getByTestId("todo-input"), "Persistent task");
      await click(getByText("Add"));

      const saved = JSON.parse(localStorage.getItem("todos"));
      expect(saved).toContainEqual(
        expect.objectContaining({text: "Persistent task"})
      );
    });

    test("filter buttons work", async () => {
      const todos = [
        {id: "1", text: "Active", done: false},
        {id: "2", text: "Done", done: true},
      ];

      const {getByText, click} = render(TodoApp, {todos});

      // Show active
      await click(getByText("Active"));
      expect(getByText("Active")).toBeTruthy();
      expect(() => getByText("Done")).toThrow();

      // Show completed
      await click(getByText("Completed"));
      expect(() => getByText("Active")).toThrow();
      expect(getByText("Done")).toBeTruthy();
    });
  });

  describe("E2E Tests", () => {
    test("complete user flow", async () => {
      await page.goto("http://localhost:3000");

      // Add todo
      await page.fill('[data-testid="todo-input"]', "E2E task");
      await page.click("text=Add");

      // Verify added
      await page.waitForSelector("text=E2E task");

      // Toggle todo
      await page.click('[data-testid="todo-checkbox-1"]');

      // Verify toggled
      const checkbox = await page.$('[data-testid="todo-checkbox-1"]');
      expect(await checkbox.isChecked()).toBe(true);

      // Delete todo
      await page.click('[data-testid="todo-delete-1"]');

      // Verify deleted
      expect(await page.$("text=E2E task")).toBeNull();
    });
  });
});
```

---

### Reflection Questions

After building:

1. **Testing Strategy:**

   - How many tests of each type?
   - When is each type appropriate?
   - What's the right balance?

2. **Test Quality:**

   - What makes a good test?
   - What makes a bad test?
   - How do you avoid brittle tests?

3. **Mocking:**

   - When should you mock?
   - When should you NOT mock?
   - What are integration tests for?

4. **Framework Testing:**
   - How do frameworks make testing easier?
   - What's still hard to test?
   - What are best practices?

---

## Section 14: Accessibility & Internationalization

### The Problem

Your app works great for you, but:

- Screen reader users can't navigate it
- Keyboard users can't use it
- Users in other countries can't read it
- Right-to-left language users see broken layouts

**Accessibility (a11y) and Internationalization (i18n) are essential for inclusive apps.**

---

### Exploration Questions

#### Accessibility Basics

**Scenario 1: Keyboard Navigation**

```javascript
// Bad: Only works with mouse
<div onClick={handleClick}>Click me</div>
// Can't be focused or activated with keyboard!

// Good: Semantic HTML
<button onClick={handleClick}>Click me</button>
// Focusable, keyboard accessible, screen reader friendly

// Custom element that needs keyboard support
<div
  role="button"
  tabIndex={0}
  onClick={handleClick}
  onKeyPress={(e) => {
    if (e.key === 'Enter' || e.key === ' ') {
      handleClick();
    }
  }}
>
  Click me
</div>
```

**Explore:**

- Why is keyboard navigation important?
- What is focus management?
- How do you make custom elements accessible?
- Build keyboard navigation system

**Scenario 2: Screen Readers**

```javascript
// Bad: No context
<button>Submit</button>
// Screen reader: "Button, Submit" - submit what?

// Good: Descriptive
<button aria-label="Submit registration form">Submit</button>
// Screen reader: "Button, Submit registration form"

// Images need alt text
<img src="graph.png" alt="Sales graph showing 30% increase" />

// Loading states
<div aria-live="polite" aria-busy={loading}>
  {loading ? 'Loading...' : content}
</div>
// Screen reader announces when content changes
```

**Explore:**

- How do screen readers work?
- What are ARIA attributes?
- When do you need ARIA?
- Build accessible components

#### Internationalization

**Scenario 3: Text Translation**

```javascript
// Bad: Hardcoded text
<button>Submit</button>

// Good: Translatable
<button>{t('form.submit')}</button>

// Translation files:
// en.json
{
  "form": {
    "submit": "Submit",
    "cancel": "Cancel"
  }
}

// es.json
{
  "form": {
    "submit": "Enviar",
    "cancel": "Cancelar"
  }
}
```

**Explore:**

- How do you structure translations?
- How do you handle plurals?
- How do you handle variables?
- Build i18n system

**Scenario 4: Date/Number Formatting**

```javascript
// Bad: US-centric
const date = "12/31/2024"; // Ambiguous!
const price = "$" + amount;

// Good: Locale-aware
const date = new Intl.DateTimeFormat("en-US").format(new Date());
// en-US: "12/31/2024"
// en-GB: "31/12/2024"

const price = new Intl.NumberFormat("en-US", {
  style: "currency",
  currency: "USD",
}).format(amount);
// en-US: "$1,234.56"
// de-DE: "1.234,56 $"
```

**Explore:**

- How do you format dates/numbers by locale?
- What is the Intl API?
- How do you detect user locale?
- Build formatting utilities

---

### Build It: Accessible & International App

#### Exercise 1: Build Accessible Component Library

Create accessible components:

```javascript
// Accessible Button
function AccessibleButton({
  children,
  onClick,
  disabled = false,
  ariaLabel,
  ariaDescribedBy,
  type = "button",
}) {
  return {
    render() {
      const button = document.createElement("button");
      button.type = type;
      button.textContent = children;
      button.disabled = disabled;

      if (ariaLabel) {
        button.setAttribute("aria-label", ariaLabel);
      }

      if (ariaDescribedBy) {
        button.setAttribute("aria-describedby", ariaDescribedBy);
      }

      button.addEventListener("click", onClick);

      return button;
    },
  };
}

// Accessible Modal
function AccessibleModal({title, content, onClose}) {
  let previousFocus = null;

  return {
    render() {
      const overlay = document.createElement("div");
      overlay.setAttribute("role", "dialog");
      overlay.setAttribute("aria-modal", "true");
      overlay.setAttribute("aria-labelledby", "modal-title");

      const modal = document.createElement("div");

      // Title
      const titleEl = document.createElement("h2");
      titleEl.id = "modal-title";
      titleEl.textContent = title;
      modal.appendChild(titleEl);

      // Content
      const contentEl = document.createElement("div");
      contentEl.textContent = content;
      modal.appendChild(contentEl);

      // Close button
      const closeBtn = document.createElement("button");
      closeBtn.textContent = "Close";
      closeBtn.setAttribute("aria-label", "Close dialog");
      closeBtn.addEventListener("click", () => {
        this.close();
        onClose();
      });
      modal.appendChild(closeBtn);

      overlay.appendChild(modal);

      return overlay;
    },

    open() {
      // Save current focus
      previousFocus = document.activeElement;

      // Focus first focusable element
      const focusable = this.element.querySelectorAll(
        'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
      );
      focusable[0]?.focus();

      // Trap focus within modal
      this.trapFocus();
    },

    close() {
      // Restore focus
      previousFocus?.focus();
    },

    trapFocus() {
      const focusable = Array.from(
        this.element.querySelectorAll(
          'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
        )
      );

      const firstFocusable = focusable[0];
      const lastFocusable = focusable[focusable.length - 1];

      this.element.addEventListener("keydown", (e) => {
        if (e.key !== "Tab") return;

        if (e.shiftKey) {
          // Shift + Tab
          if (document.activeElement === firstFocusable) {
            e.preventDefault();
            lastFocusable.focus();
          }
        } else {
          // Tab
          if (document.activeElement === lastFocusable) {
            e.preventDefault();
            firstFocusable.focus();
          }
        }
      });
    },
  };
}

// Accessible Form Field
function AccessibleFormField({
  label,
  type = "text",
  id,
  required = false,
  error,
  helpText,
}) {
  return {
    render() {
      const container = document.createElement("div");

      // Label
      const labelEl = document.createElement("label");
      labelEl.htmlFor = id;
      labelEl.textContent = label + (required ? " *" : "");
      container.appendChild(labelEl);

      // Input
      const input = document.createElement("input");
      input.type = type;
      input.id = id;
      input.required = required;

      if (error) {
        input.setAttribute("aria-invalid", "true");
        input.setAttribute("aria-describedby", `${id}-error`);
      } else if (helpText) {
        input.setAttribute("aria-describedby", `${id}-help`);
      }

      container.appendChild(input);

      // Help text
      if (helpText) {
        const help = document.createElement("div");
        help.id = `${id}-help`;
        help.textContent = helpText;
        container.appendChild(help);
      }

      // Error message
      if (error) {
        const errorEl = document.createElement("div");
        errorEl.id = `${id}-error`;
        errorEl.setAttribute("role", "alert");
        errorEl.textContent = error;
        container.appendChild(errorEl);
      }

      return container;
    },
  };
}
```

#### Exercise 2: Build i18n System

Create translation system:

```javascript
class I18n {
  constructor(defaultLocale = "en") {
    this.locale = defaultLocale;
    this.translations = {};
    this.fallbackLocale = defaultLocale;
  }

  setLocale(locale) {
    this.locale = locale;
    this.notifyListeners();
  }

  loadTranslations(locale, translations) {
    this.translations[locale] = translations;
  }

  t(key, params = {}) {
    const translation =
      this.getTranslation(key, this.locale) ||
      this.getTranslation(key, this.fallbackLocale) ||
      key;

    return this.interpolate(translation, params);
  }

  getTranslation(key, locale) {
    const keys = key.split(".");
    let value = this.translations[locale];

    for (const k of keys) {
      if (value && typeof value === "object") {
        value = value[k];
      } else {
        return null;
      }
    }

    return value;
  }

  interpolate(text, params) {
    if (typeof text !== "string") return text;

    return text.replace(/\{\{(\w+)\}\}/g, (match, key) => {
      return params[key] !== undefined ? params[key] : match;
    });
  }

  // Pluralization
  plural(key, count, params = {}) {
    const pluralKey = count === 1 ? `${key}.one` : `${key}.other`;
    return this.t(pluralKey, {...params, count});
  }

  // Date formatting
  formatDate(date, options = {}) {
    return new Intl.DateTimeFormat(this.locale, options).format(date);
  }

  // Number formatting
  formatNumber(number, options = {}) {
    return new Intl.NumberFormat(this.locale, options).format(number);
  }

  // Currency formatting
  formatCurrency(amount, currency) {
    return new Intl.NumberFormat(this.locale, {
      style: "currency",
      currency,
    }).format(amount);
  }

  // Listeners for reactive updates
  listeners = new Set();

  subscribe(callback) {
    this.listeners.add(callback);
    return () => this.listeners.delete(callback);
  }

  notifyListeners() {
    this.listeners.forEach((callback) => callback(this.locale));
  }
}

// Usage:
const i18n = new I18n("en");

i18n.loadTranslations("en", {
  greeting: "Hello, {{name}}!",
  items: {
    one: "{{count}} item",
    other: "{{count}} items",
  },
  cart: {
    total: "Total: {{amount}}",
  },
});

i18n.loadTranslations("es", {
  greeting: "¡Hola, {{name}}!",
  items: {
    one: "{{count}} artículo",
    other: "{{count}} artículos",
  },
  cart: {
    total: "Total: {{amount}}",
  },
});

console.log(i18n.t("greeting", {name: "Alice"}));
// "Hello, Alice!"

i18n.setLocale("es");
console.log(i18n.t("greeting", {name: "Alice"}));
// "¡Hola, Alice!"

console.log(i18n.plural("items", 1)); // "1 item"
console.log(i18n.plural("items", 5)); // "5 items"

console.log(i18n.formatCurrency(1234.56, "USD"));
// en: "$1,234.56"
// es: "1234,56 US$"
```

#### Exercise 3: Build Accessibility Testing Tool

Create a11y auditor:

```javascript
function auditAccessibility(element) {
  const issues = [];

  // Check for missing alt text
  element.querySelectorAll("img").forEach((img) => {
    if (!img.hasAttribute("alt")) {
      issues.push({
        severity: "error",
        element: img,
        message: "Image missing alt attribute",
      });
    }
  });

  // Check for empty links
  element.querySelectorAll("a").forEach((link) => {
    if (!link.textContent.trim() && !link.getAttribute("aria-label")) {
      issues.push({
        severity: "error",
        element: link,
        message: "Link has no accessible text",
      });
    }
  });

  // Check for button accessibility
  element.querySelectorAll('[role="button"]').forEach((btn) => {
    if (!btn.hasAttribute("tabindex")) {
      issues.push({
        severity: "error",
        element: btn,
        message: "Button role without tabindex",
      });
    }
  });

  // Check heading hierarchy
  const headings = Array.from(
    element.querySelectorAll("h1, h2, h3, h4, h5, h6")
  );
  headings.forEach((heading, i) => {
    const level = parseInt(heading.tagName[1]);
    const prevLevel = i > 0 ? parseInt(headings[i - 1].tagName[1]) : 0;

    if (level - prevLevel > 1) {
      issues.push({
        severity: "warning",
        element: heading,
        message: `Heading levels skipped (h${prevLevel} to h${level})`,
      });
    }
  });

  // Check form labels
  element.querySelectorAll("input, select, textarea").forEach((input) => {
    const id = input.id;
    const label = id && element.querySelector(`label[for="${id}"]`);
    const ariaLabel = input.getAttribute("aria-label");
    const ariaLabelledBy = input.getAttribute("aria-labelledby");

    if (!label && !ariaLabel && !ariaLabelledBy) {
      issues.push({
        severity: "error",
        element: input,
        message: "Form control has no label",
      });
    }
  });

  // Check color contrast
  // (This is complex - would need computed styles)

  // Check for keyboard traps
  const focusable = element.querySelectorAll(
    'a[href], button, input, select, textarea, [tabindex]:not([tabindex="-1"])'
  );

  if (focusable.length === 0) {
    issues.push({
      severity: "warning",
      element,
      message: "No focusable elements found",
    });
  }

  return {
    issues,
    score: calculateA11yScore(issues),
  };
}

function calculateA11yScore(issues) {
  const weights = {error: 10, warning: 5};
  const deductions = issues.reduce((total, issue) => {
    return total + weights[issue.severity];
  }, 0);

  return Math.max(0, 100 - deductions);
}

// Usage:
const audit = auditAccessibility(document.body);
console.log(`Accessibility Score: ${audit.score}/100`);
console.log("Issues:", audit.issues);
```

#### Exercise 4: Compare Framework a11y/i18n

Research framework support:

| Feature               | React                  | Vue 3                             | Svelte           | Solid.js                 |
| --------------------- | ---------------------- | --------------------------------- | ---------------- | ------------------------ |
| **ARIA Support**      | Yes                    | Yes                               | Yes              | Yes                      |
| **Built-in i18n**     | No                     | No                                | No               | No                       |
| **Popular i18n Libs** | react-i18next          | vue-i18n                          | svelte-i18n      | @solid-primitives/i18n   |
| **a11y Linting**      | eslint-plugin-jsx-a11y | eslint-plugin-vuejs-accessibility | -                | -                        |
| **Testing Tools**     | @testing-library       | @testing-library                  | @testing-library | @solidjs/testing-library |

**Best practices across frameworks:**

- Use semantic HTML
- Add ARIA when needed
- Manage focus properly
- Support keyboard navigation
- Use i18n library for translations
- Test with screen readers
- Run accessibility audits

---

### Reflection Questions

After building:

1. **Accessibility:**

   - Why is a11y important?
   - What are common mistakes?
   - How do you test accessibility?

2. **Internationalization:**

   - What are i18n challenges?
   - How do you handle RTL languages?
   - What about date/number formats?

3. **Framework Support:**

   - Do frameworks make a11y easier?
   - What's still the developer's responsibility?
   - What tools help?

4. **Best Practices:**
   - When do you add a11y?
   - How do you prioritize?
   - What's the minimum required?

---

## Section 15: Middleware & Interceptors

### The Problem

You need to run code at specific points:

- Before every API request (add auth token)
- After every response (handle errors globally)
- Before navigation (check if user is logged in)
- After state changes (log analytics)

**Middleware/interceptors let you inject behavior without modifying every function.**

---

### Exploration Questions

**Scenario 1: Request Interceptors**

```javascript
// Without middleware: Repeat everywhere
fetch("/api/users", {
  headers: {
    Authorization: `Bearer ${token}`,
    "Content-Type": "application/json",
  },
});

// With middleware: Once
api.use((config) => {
  config.headers["Authorization"] = `Bearer ${token}`;
  return config;
});

api.get("/users"); // Auth header added automatically
```

**Explore:**

- What is middleware?
- How do you chain middleware?
- How do you pass data between middleware?
- Build middleware system

**Scenario 2: Navigation Guards**

```javascript
router.beforeEach((to, from, next) => {
  if (to.requires Auth && !isLoggedIn()) {
    next('/login');
  } else {
    next();
  }
});
```

**Explore:**

- What are navigation guards?
- When do they run?
- How do you implement them?
- Build route middleware

---

### Build It: Middleware Systems

#### Exercise 1: Build HTTP Interceptors

```javascript
class HttpClient {
  constructor() {
    this.requestInterceptors = [];
    this.responseInterceptors = [];
  }

  useRequest(interceptor) {
    this.requestInterceptors.push(interceptor);
  }

  useResponse(interceptor) {
    this.responseInterceptors.push(interceptor);
  }

  async request(config) {
    // Run request interceptors
    let finalConfig = config;
    for (const interceptor of this.requestInterceptors) {
      finalConfig = await interceptor(finalConfig);
    }

    // Make request
    let response = await fetch(finalConfig.url, finalConfig);

    // Run response interceptors
    for (const interceptor of this.responseInterceptors) {
      response = await interceptor(response);
    }

    return response;
  }
}

// Usage:
const api = new HttpClient();

api.useRequest((config) => {
  config.headers = {
    ...config.headers,
    Authorization: `Bearer ${getToken()}`,
  };
  return config;
});

api.useResponse(async (response) => {
  if (response.status === 401) {
    // Redirect to login
    window.location.href = "/login";
  }
  return response;
});
```

#### Exercise 2: Build State Change Middleware

```javascript
function createStore(reducer, initialState, middleware = []) {
  let state = initialState;
  const listeners = [];

  function dispatch(action) {
    // Build middleware chain
    const chain = middleware.map((mw) => mw({getState, dispatch}));
    const enhancedDispatch = chain.reduceRight(
      (next, mw) => mw(next),
      (action) => {
        state = reducer(state, action);
        listeners.forEach((fn) => fn());
        return action;
      }
    );

    return enhancedDispatch(action);
  }

  function getState() {
    return state;
  }

  function subscribe(listener) {
    listeners.push(listener);
    return () => {
      const index = listeners.indexOf(listener);
      listeners.splice(index, 1);
    };
  }

  return {dispatch, getState, subscribe};
}

// Logger middleware
const logger = (store) => (next) => (action) => {
  console.log("Dispatching:", action);
  const result = next(action);
  console.log("New state:", store.getState());
  return result;
};

// Thunk middleware
const thunk = (store) => (next) => (action) => {
  if (typeof action === "function") {
    return action(store.dispatch, store.getState);
  }
  return next(action);
};
```

---

## Section 16: Error Handling & Monitoring

### The Problem

Your app crashes and you have no idea why:

```javascript
// User reports: "It's broken!"
// You: "What happened?"
// User: "I don't know, it just stopped working"

// No error logs, no stack traces, no context
// How do you debug production issues?
```

**Problems:**

- Uncaught errors crash the app
- No visibility into production errors
- Can't reproduce user issues
- No performance monitoring

**You need error handling and monitoring!**

---

### Exploration Questions

#### Error Handling Basics

**Scenario 1: The Uncaught Error**

```javascript
function loadUser(id) {
  const response = await fetch(`/api/users/${id}`);
  const user = response.json(); // Forgot await! Runtime error!
  return user;
}

// App crashes with no recovery
```

**Explore:**

- How do you catch errors globally?
- What is an error boundary?
- How do you recover from errors gracefully?
- Build error handling system

**Scenario 2: Error Types**

```javascript
// Network errors
fetch("/api").catch((err) => {
  // How do you handle timeouts?
  // How do you retry?
  // How do you show offline state?
});

// Validation errors
if (!email.includes("@")) {
  throw new Error("Invalid email"); // User-facing
}

// Programming errors
const user = null;
console.log(user.name); // TypeError - bug!

// Different errors need different handling
```

**Explore:**

- What are error categories?
- How do you handle each type?
- Which errors are recoverable?
- Build error classification

**Scenario 3: Error Boundaries**

```javascript
// One component crashes → whole app crashes
function BrokenComponent() {
  throw new Error("Oops!");
}

// Better: Isolate errors
<ErrorBoundary fallback={<ErrorMessage />}>
  <BrokenComponent />
</ErrorBoundary>;
// Only this component fails, rest of app works
```

**Explore:**

- What is an error boundary?
- How do you catch render errors?
- How do you implement error boundaries?
- Build error boundary system

#### Production Monitoring

**Scenario 4: Error Tracking**

```javascript
// Production error occurs
// Need to know:
// - What error?
// - Where in code?
// - What user was doing?
// - Browser/device info?
// - How to reproduce?

window.addEventListener("error", (event) => {
  // Send to error tracking service
  trackError({
    message: event.error.message,
    stack: event.error.stack,
    url: window.location.href,
    userAgent: navigator.userAgent,
    timestamp: Date.now(),
  });
});
```

**Explore:**

- How do you capture errors in production?
- What context do you need?
- How do you send errors to server?
- Build error tracking system

**Scenario 5: Performance Monitoring**

```javascript
// App is slow, but where?
// Need to measure:
// - Page load time
// - Component render time
// - API response time
// - User interactions

performance.mark("start");
// ... do work
performance.mark("end");
performance.measure("work", "start", "end");

const measure = performance.getEntriesByName("work")[0];
console.log(`Took ${measure.duration}ms`);
```

**Explore:**

- How do you measure performance?
- What metrics matter?
- How do you track in production?
- Build performance monitoring

---

### Build It: Error & Monitoring System

#### Exercise 1: Build Error Boundary

Create error catching system:

```javascript
class ErrorBoundary {
  constructor(options = {}) {
    this.fallback = options.fallback;
    this.onError = options.onError;
    this.hasError = false;
    this.error = null;
  }

  wrap(componentFn) {
    return (...args) => {
      try {
        this.hasError = false;
        this.error = null;
        return componentFn(...args);
      } catch (error) {
        this.hasError = true;
        this.error = error;

        // Call error handler
        if (this.onError) {
          this.onError(error, this.getErrorInfo());
        }

        // Return fallback UI
        return this.fallback
          ? this.fallback(error)
          : this.renderDefaultError(error);
      }
    };
  }

  getErrorInfo() {
    return {
      componentStack: this.getComponentStack(),
      timestamp: Date.now(),
      url: window.location.href,
    };
  }

  getComponentStack() {
    // Parse stack trace to get component hierarchy
    if (!this.error || !this.error.stack) return "";

    const lines = this.error.stack.split("\n");
    return lines.slice(0, 5).join("\n");
  }

  renderDefaultError(error) {
    const container = document.createElement("div");
    container.style.cssText = `
      padding: 20px;
      margin: 20px;
      border: 2px solid #ff0000;
      border-radius: 4px;
      background: #fff5f5;
    `;

    container.innerHTML = `
      <h3 style="color: #ff0000; margin-top: 0;">Something went wrong</h3>
      <p><strong>Error:</strong> ${error.message}</p>
      <details>
        <summary>Stack trace</summary>
        <pre style="overflow: auto; padding: 10px; background: #f5f5f5;">${error.stack}</pre>
      </details>
      <button onclick="window.location.reload()">Reload page</button>
    `;

    return container;
  }

  reset() {
    this.hasError = false;
    this.error = null;
  }
}

// Usage:
const errorBoundary = new ErrorBoundary({
  fallback: (error) => {
    const div = document.createElement("div");
    div.innerHTML = `<p>Error: ${error.message}</p><button>Retry</button>`;
    return div;
  },
  onError: (error, errorInfo) => {
    console.error("Caught by boundary:", error);
    // Send to error tracking service
    trackError({error, errorInfo});
  },
});

// Wrap risky component
const SafeComponent = errorBoundary.wrap(RiskyComponent);
```

#### Exercise 2: Build Error Tracking Service

Create error reporting system:

```javascript
class ErrorTracker {
  constructor(config = {}) {
    this.apiEndpoint = config.apiEndpoint;
    this.apiKey = config.apiKey;
    this.appVersion = config.appVersion;
    this.environment = config.environment || "production";
    this.userId = null;
    this.context = {};

    this.setupGlobalHandlers();
  }

  setupGlobalHandlers() {
    // Catch unhandled errors
    window.addEventListener("error", (event) => {
      this.captureError(event.error, {
        type: "unhandled",
        filename: event.filename,
        lineno: event.lineno,
        colno: event.colno,
      });
    });

    // Catch unhandled promise rejections
    window.addEventListener("unhandledrejection", (event) => {
      this.captureError(event.reason, {
        type: "unhandled-promise",
      });
    });
  }

  setUser(userId, userData = {}) {
    this.userId = userId;
    this.context.user = {id: userId, ...userData};
  }

  setContext(key, value) {
    this.context[key] = value;
  }

  captureError(error, extra = {}) {
    const errorData = {
      // Error details
      message: error.message,
      stack: error.stack,
      name: error.name,

      // Context
      url: window.location.href,
      timestamp: new Date().toISOString(),

      // Environment
      environment: this.environment,
      appVersion: this.appVersion,
      userId: this.userId,

      // Browser info
      userAgent: navigator.userAgent,
      viewport: {
        width: window.innerWidth,
        height: window.innerHeight,
      },
      screen: {
        width: screen.width,
        height: screen.height,
      },

      // Custom context
      context: this.context,
      extra,
    };

    // Send to server
    this.sendError(errorData);

    // Also log to console in development
    if (this.environment !== "production") {
      console.error("Error tracked:", errorData);
    }
  }

  async sendError(errorData) {
    try {
      await fetch(this.apiEndpoint, {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
          "X-API-Key": this.apiKey,
        },
        body: JSON.stringify(errorData),
      });
    } catch (err) {
      // Silently fail - don't create infinite error loop
      console.error("Failed to send error to tracking service:", err);
    }
  }

  captureMessage(message, level = "info") {
    this.sendError({
      message,
      level,
      timestamp: new Date().toISOString(),
      context: this.context,
    });
  }
}

// Usage:
const tracker = new ErrorTracker({
  apiEndpoint: "https://errors.example.com/api/errors",
  apiKey: "your-api-key",
  appVersion: "1.0.0",
  environment: process.env.NODE_ENV,
});

// Set user context
tracker.setUser("user-123", {
  email: "user@example.com",
  plan: "premium",
});

// Set custom context
tracker.setContext("page", "checkout");
tracker.setContext("cart", {items: 3, total: 99.99});

// Manually capture errors
try {
  riskyOperation();
} catch (error) {
  tracker.captureError(error, {
    context: "checkout-process",
    step: "payment",
  });
}

// Capture messages
tracker.captureMessage("User completed purchase", "info");
```

#### Exercise 3: Build Performance Monitor

Create performance tracking:

```javascript
class PerformanceMonitor {
  constructor(config = {}) {
    this.apiEndpoint = config.apiEndpoint;
    this.sampleRate = config.sampleRate || 1.0; // 100% by default
    this.metrics = [];

    this.setupObservers();
  }

  setupObservers() {
    // Observe navigation timing
    window.addEventListener("load", () => {
      this.captureNavigationTiming();
    });

    // Observe resource timing
    if (window.PerformanceObserver) {
      const observer = new PerformanceObserver((list) => {
        list.getEntries().forEach((entry) => {
          this.captureResourceTiming(entry);
        });
      });

      observer.observe({entryTypes: ["resource", "measure", "mark"]});
    }
  }

  captureNavigationTiming() {
    if (!performance.timing) return;

    const timing = performance.timing;
    const metrics = {
      type: "navigation",
      // DNS lookup
      dns: timing.domainLookupEnd - timing.domainLookupStart,
      // TCP connection
      tcp: timing.connectEnd - timing.connectStart,
      // Request + Response
      request: timing.responseEnd - timing.requestStart,
      // DOM processing
      domProcessing: timing.domComplete - timing.domLoading,
      // Total load time
      loadTime: timing.loadEventEnd - timing.navigationStart,
      // DOM ready
      domReady: timing.domContentLoadedEventEnd - timing.navigationStart,
      // Time to first byte
      ttfb: timing.responseStart - timing.navigationStart,
    };

    this.reportMetrics(metrics);
  }

  captureResourceTiming(entry) {
    const metrics = {
      type: "resource",
      name: entry.name,
      duration: entry.duration,
      size: entry.transferSize,
      cached: entry.transferSize === 0,
    };

    this.reportMetrics(metrics);
  }

  measureFunction(name, fn) {
    const startMark = `${name}-start`;
    const endMark = `${name}-end`;

    performance.mark(startMark);

    try {
      const result = fn();

      if (result instanceof Promise) {
        return result.finally(() => {
          performance.mark(endMark);
          performance.measure(name, startMark, endMark);
        });
      } else {
        performance.mark(endMark);
        performance.measure(name, startMark, endMark);
        return result;
      }
    } catch (error) {
      performance.mark(endMark);
      performance.measure(name, startMark, endMark);
      throw error;
    }
  }

  measureRender(componentName, renderFn) {
    return this.measureFunction(`render:${componentName}`, renderFn);
  }

  reportMetrics(metrics) {
    // Sample based on sample rate
    if (Math.random() > this.sampleRate) return;

    this.metrics.push({
      ...metrics,
      timestamp: Date.now(),
      url: window.location.href,
    });

    // Batch send metrics
    if (this.metrics.length >= 10) {
      this.sendMetrics();
    }
  }

  async sendMetrics() {
    if (this.metrics.length === 0) return;

    const batch = this.metrics.splice(0, this.metrics.length);

    try {
      await fetch(this.apiEndpoint, {
        method: "POST",
        headers: {"Content-Type": "application/json"},
        body: JSON.stringify({metrics: batch}),
      });
    } catch (error) {
      console.error("Failed to send metrics:", error);
    }
  }

  // Core Web Vitals
  measureWebVitals() {
    // Largest Contentful Paint (LCP)
    const lcpObserver = new PerformanceObserver((list) => {
      const entries = list.getEntries();
      const lastEntry = entries[entries.length - 1];

      this.reportMetrics({
        type: "web-vital",
        name: "LCP",
        value: lastEntry.renderTime || lastEntry.loadTime,
      });
    });
    lcpObserver.observe({entryTypes: ["largest-contentful-paint"]});

    // First Input Delay (FID)
    const fidObserver = new PerformanceObserver((list) => {
      const entries = list.getEntries();
      entries.forEach((entry) => {
        this.reportMetrics({
          type: "web-vital",
          name: "FID",
          value: entry.processingStart - entry.startTime,
        });
      });
    });
    fidObserver.observe({entryTypes: ["first-input"]});

    // Cumulative Layout Shift (CLS)
    let clsValue = 0;
    const clsObserver = new PerformanceObserver((list) => {
      list.getEntries().forEach((entry) => {
        if (!entry.hadRecentInput) {
          clsValue += entry.value;
        }
      });

      this.reportMetrics({
        type: "web-vital",
        name: "CLS",
        value: clsValue,
      });
    });
    clsObserver.observe({entryTypes: ["layout-shift"]});
  }
}

// Usage:
const monitor = new PerformanceMonitor({
  apiEndpoint: "https://metrics.example.com/api/metrics",
  sampleRate: 0.1, // Sample 10% of users
});

// Measure function performance
monitor.measureFunction("loadUser", async () => {
  const user = await fetchUser(123);
  return user;
});

// Measure component render
function MyComponent() {
  return monitor.measureRender("MyComponent", () => {
    // Render logic
    return createElement("div", "Hello");
  });
}

// Track Core Web Vitals
monitor.measureWebVitals();
```

#### Exercise 4: Build Retry Logic

Create automatic retry system:

```javascript
class RetryHandler {
  constructor(options = {}) {
    this.maxRetries = options.maxRetries || 3;
    this.baseDelay = options.baseDelay || 1000;
    this.maxDelay = options.maxDelay || 10000;
    this.backoffMultiplier = options.backoffMultiplier || 2;
    this.retryableStatuses = options.retryableStatuses || [
      408, 429, 500, 502, 503, 504,
    ];
  }

  async execute(fn, context = {}) {
    let lastError;

    for (let attempt = 0; attempt <= this.maxRetries; attempt++) {
      try {
        return await fn();
      } catch (error) {
        lastError = error;

        // Check if error is retryable
        if (!this.shouldRetry(error, attempt)) {
          throw error;
        }

        // Calculate delay with exponential backoff
        const delay = this.calculateDelay(attempt);

        console.log(
          `Retry attempt ${attempt + 1}/${this.maxRetries} after ${delay}ms`
        );

        // Wait before retry
        await this.sleep(delay);
      }
    }

    // All retries exhausted
    throw lastError;
  }

  shouldRetry(error, attempt) {
    // Don't retry if max attempts reached
    if (attempt >= this.maxRetries) return false;

    // Retry on network errors
    if (error.name === "NetworkError" || error.message.includes("fetch")) {
      return true;
    }

    // Retry on specific HTTP status codes
    if (error.status && this.retryableStatuses.includes(error.status)) {
      return true;
    }

    // Retry on timeout
    if (error.name === "TimeoutError") {
      return true;
    }

    return false;
  }

  calculateDelay(attempt) {
    // Exponential backoff with jitter
    const exponentialDelay =
      this.baseDelay * Math.pow(this.backoffMultiplier, attempt);
    const jitter = Math.random() * 1000; // Random 0-1000ms
    const delay = Math.min(exponentialDelay + jitter, this.maxDelay);
    return delay;
  }

  sleep(ms) {
    return new Promise((resolve) => setTimeout(resolve, ms));
  }
}

// Usage:
const retry = new RetryHandler({
  maxRetries: 3,
  baseDelay: 1000,
  backoffMultiplier: 2,
});

async function fetchWithRetry(url) {
  return retry.execute(async () => {
    const response = await fetch(url);

    if (!response.ok) {
      const error = new Error(`HTTP ${response.status}`);
      error.status = response.status;
      throw error;
    }

    return response.json();
  });
}

// Will retry up to 3 times with exponential backoff
const data = await fetchWithRetry("/api/users");
```

#### Exercise 5: Compare Error Handling Across Frameworks

Research how frameworks handle errors:

| Feature               | React                   | Vue 3                   | Svelte         | Solid.js            |
| --------------------- | ----------------------- | ----------------------- | -------------- | ------------------- |
| **Error Boundaries**  | Yes (componentDidCatch) | Yes (errorCaptured)     | No (try/catch) | Yes (ErrorBoundary) |
| **Global Handler**    | window.onerror          | app.config.errorHandler | window.onerror | window.onerror      |
| **Dev Mode Errors**   | Overlay                 | Overlay                 | Overlay        | Overlay             |
| **Production Errors** | Silent                  | Silent                  | Silent         | Silent              |
| **Error Recovery**    | Fallback UI             | Fallback UI             | Manual         | Fallback UI         |

**Popular monitoring services:**

- **Sentry** - Error tracking
- **LogRocket** - Session replay
- **Datadog** - Full observability
- **New Relic** - APM
- **Google Analytics** - Basic tracking

**Best practices:**

- Always use error boundaries
- Track errors in production
- Add context to errors
- Monitor performance
- Set up alerts
- Have error recovery strategies

---

### Reflection Questions

After building:

1. **Error Handling:**

   - When should errors crash vs be caught?
   - How do you balance safety vs resilience?
   - What makes a good error message?

2. **Production Monitoring:**

   - What metrics matter most?
   - How much should you track?
   - What's the performance cost?

3. **Framework Support:**

   - Do frameworks make error handling easier?
   - What's still your responsibility?
   - How do you integrate monitoring?

4. **Best Practices:**
   - When do you retry vs fail?
   - How do you alert on critical errors?
   - What's acceptable downtime?

---

## Section 17: Framework Evaluation & Selection

### The Problem

There are 50+ JavaScript frameworks. How do you choose?

```
React, Vue, Svelte, Angular, Solid, Preact, Qwik, Lit, Alpine,
Ember, Backbone, Knockout, Meteor, Mithril, Riot, Marko, Inferno,
Hyperapp, Stimulus, Aurelia, Polymer...

Which one should you learn?
Which one should you use for your project?
How do you decide?
```

**Choosing the wrong framework can cost months of work!**

---

### Exploration Questions

#### Framework Evaluation Criteria

**Scenario 1: Project Requirements**

```javascript
// Project A: Marketing Website
// - Static content
// - Good SEO critical
// - Simple interactions
// - Fast load time
// → Astro? Svelte? Next.js?

// Project B: Complex Dashboard
// - Real-time updates
// - Lots of state
// - Heavy interactions
// - SEO not important
// → React? Vue? Solid?

// Project C: Mobile-First App
// - Small bundle size critical
// - Works offline
// - Native-like feel
// → Preact? Svelte? Solid?

// Different projects need different frameworks!
```

**Explore:**

- How do you match framework to project?
- What questions should you ask?
- What are dealbreakers?
- Build evaluation framework

**Scenario 2: Team Considerations**

```javascript
// Team factors:
// - Current skills (JavaScript? TypeScript? React?)
// - Learning curve acceptable?
// - Long-term maintenance who?
// - Hiring: Will we find developers?
// - Documentation quality?
// - Community support?

// Technical debt:
// - Existing codebase to integrate with?
// - Migration path from old framework?
// - Vendor lock-in concerns?
```

**Explore:**

- How do team skills affect choice?
- When is learning curve acceptable?
- How do you evaluate community?
- Build team evaluation checklist

**Scenario 3: Performance vs Developer Experience**

```
Svelte: Best performance, smaller community
React: Good performance, huge community

Solid: Fastest, newer/smaller community
Vue: Balanced, growing community

Which matters more for your project?
```

**Explore:**

- How do you balance tradeoffs?
- When does performance matter most?
- When does DX matter most?
- Build tradeoff matrix

#### Framework Benchmarking

**Scenario 4: Real-World Testing**

```javascript
// Build same app in 3 frameworks:
// - Todo app with 1000 items
// - Real-time filtering
// - Sorting
// - CRUD operations

// Measure:
// - Initial load time
// - Time to interactive
// - Memory usage
// - Bundle size
// - Update performance
// - Developer time to build
// - Lines of code
```

**Explore:**

- What metrics matter?
- How do you test fairly?
- What's "good enough" performance?
- Build benchmarking suite

---

### Build It: Framework Evaluation System

#### Exercise 1: Build Evaluation Scorecard

Create systematic evaluation:

```javascript
const evaluationCriteria = {
  technical: {
    performance: {
      weight: 8,
      questions: [
        "What is the bundle size?",
        "How fast is initial render?",
        "How fast are updates?",
        "What is memory usage?",
      ],
    },

    scalability: {
      weight: 7,
      questions: [
        "How does it handle large apps?",
        "What is code splitting support?",
        "How is lazy loading?",
      ],
    },

    features: {
      weight: 6,
      questions: [
        "Does it support SSR?",
        "Does it support SSG?",
        "What is TypeScript support?",
        "What are built-in features?",
      ],
    },

    modernApproach: {
      weight: 5,
      questions: [
        "How modern is the approach?",
        "What is the architecture?",
        "How does reactivity work?",
      ],
    },
  },

  ecosystem: {
    community: {
      weight: 8,
      questions: [
        "How large is the community?",
        "How active is development?",
        "What are GitHub stars/forks?",
        "What is npm download trend?",
      ],
    },

    documentation: {
      weight: 9,
      questions: [
        "How good is the documentation?",
        "Are there tutorials?",
        "Are there examples?",
        "Is documentation up to date?",
      ],
    },

    tooling: {
      weight: 7,
      questions: [
        "What are CLI tools?",
        "What is DevTools support?",
        "What are IDE plugins?",
        "What is testing support?",
      ],
    },

    libraries: {
      weight: 6,
      questions: [
        "What routing libraries exist?",
        "What state management options?",
        "What UI component libraries?",
        "What is third-party support?",
      ],
    },
  },

  projectFit: {
    learningCurve: {
      weight: 7,
      questions: [
        "How easy to learn?",
        "What are prerequisites?",
        "How long to productivity?",
      ],
    },

    team: {
      weight: 8,
      questions: [
        "Does team know this framework?",
        "Can we hire developers?",
        "What is onboarding time?",
      ],
    },

    requirements: {
      weight: 10,
      questions: [
        "Does it meet our requirements?",
        "What are technical constraints?",
        "What are business needs?",
      ],
    },

    longevity: {
      weight: 7,
      questions: [
        "Is framework actively maintained?",
        "What is backward compatibility?",
        "What is migration path?",
        "What is corporate backing?",
      ],
    },
  },
};

function evaluateFramework(frameworkName, scores) {
  let totalScore = 0;
  let maxScore = 0;
  const categoryScores = {};

  Object.entries(evaluationCriteria).forEach(([categoryName, category]) => {
    let categoryScore = 0;
    let categoryMax = 0;

    Object.entries(category).forEach(([criterionName, criterion]) => {
      const score = scores[categoryName]?.[criterionName] || 0;
      const weighted = score * criterion.weight;

      categoryScore += weighted;
      categoryMax += 10 * criterion.weight;
    });

    categoryScores[categoryName] = {
      score: categoryScore,
      max: categoryMax,
      percentage: ((categoryScore / categoryMax) * 100).toFixed(1),
    };

    totalScore += categoryScore;
    maxScore += categoryMax;
  });

  return {
    framework: frameworkName,
    totalScore,
    maxScore,
    percentage: ((totalScore / maxScore) * 100).toFixed(1),
    categoryScores,
    grade: getGrade((totalScore / maxScore) * 100),
  };
}

function getGrade(percentage) {
  if (percentage >= 90) return "A";
  if (percentage >= 80) return "B";
  if (percentage >= 70) return "C";
  if (percentage >= 60) return "D";
  return "F";
}

// Usage:
const reactEvaluation = evaluateFramework("React", {
  technical: {
    performance: 7,
    scalability: 9,
    features: 8,
    modernApproach: 7,
  },
  ecosystem: {
    community: 10,
    documentation: 9,
    tooling: 10,
    libraries: 10,
  },
  projectFit: {
    learningCurve: 6,
    team: 9,
    requirements: 8,
    longevity: 10,
  },
});

console.log(reactEvaluation);
// {
//   framework: 'React',
//   totalScore: 723,
//   maxScore: 820,
//   percentage: '88.2',
//   grade: 'B',
//   categoryScores: { ... }
// }
```

#### Exercise 2: Build Framework Comparison Tool

Create side-by-side comparison:

```javascript
const frameworks = {
  react: {
    name: "React",
    version: "18.2",
    releaseDate: "2013",

    metrics: {
      bundleSize: 44, // KB (gzipped)
      npmWeekly: 18000000,
      githubStars: 220000,
      githubForks: 45000,
      stackOverflowQuestions: 450000,
    },

    pros: [
      "Huge ecosystem",
      "Large community",
      "Tons of jobs",
      "Great tooling",
      "Corporate backing (Meta)",
    ],

    cons: [
      "Larger bundle size",
      "Need to learn many libraries",
      "JSX learning curve",
      "Frequent changes",
    ],

    bestFor: [
      "Large applications",
      "Teams with React experience",
      "Projects needing many libraries",
      "Career opportunities",
    ],
  },

  vue: {
    name: "Vue",
    version: "3.3",
    releaseDate: "2014",

    metrics: {
      bundleSize: 34,
      npmWeekly: 4000000,
      githubStars: 210000,
      githubForks: 33000,
      stackOverflowQuestions: 100000,
    },

    pros: [
      "Gentle learning curve",
      "Great documentation",
      "Good performance",
      "Flexible architecture",
      "Single-file components",
    ],

    cons: [
      "Smaller than React ecosystem",
      "Fewer jobs than React",
      "Less corporate backing",
      "Some China-centric resources",
    ],

    bestFor: [
      "Balanced complexity",
      "Good documentation needed",
      "Teams wanting flexibility",
      "Progressive enhancement",
    ],
  },

  svelte: {
    name: "Svelte",
    version: "4.0",
    releaseDate: "2016",

    metrics: {
      bundleSize: 3,
      npmWeekly: 600000,
      githubStars: 75000,
      githubForks: 4000,
      stackOverflowQuestions: 8000,
    },

    pros: [
      "Smallest bundle size",
      "Best performance",
      "Less boilerplate",
      "Easy to learn",
      "No virtual DOM",
    ],

    cons: [
      "Smaller ecosystem",
      "Fewer jobs",
      "Smaller community",
      "Less tooling",
      "Compiler magic",
    ],

    bestFor: [
      "Performance critical",
      "Small team projects",
      "Quick prototypes",
      "Mobile-first apps",
    ],
  },

  solid: {
    name: "Solid",
    version: "1.7",
    releaseDate: "2018",

    metrics: {
      bundleSize: 7,
      npmWeekly: 150000,
      githubStars: 30000,
      githubForks: 900,
      stackOverflowQuestions: 500,
    },

    pros: [
      "Fastest performance",
      "Small bundle",
      "Fine-grained reactivity",
      "React-like syntax",
      "No virtual DOM",
    ],

    cons: [
      "Newest/smallest community",
      "Fewest jobs",
      "Limited ecosystem",
      "Still maturing",
      "Different mental model",
    ],

    bestFor: [
      "Maximum performance",
      "React developers wanting speed",
      "Learning fine-grained reactivity",
      "Experimental projects",
    ],
  },
};

function compareFrameworks(frameworkKeys) {
  const comparison = {
    frameworks: frameworkKeys.map((key) => frameworks[key]),

    winner: {
      bundleSize: null,
      performance: null,
      ecosystem: null,
      jobs: null,
      learning: null,
    },
  };

  // Determine winners
  comparison.winner.bundleSize = frameworkKeys.reduce((winner, key) => {
    const current = frameworks[key];
    const winnerFw = frameworks[winner];
    return current.metrics.bundleSize < winnerFw.metrics.bundleSize
      ? key
      : winner;
  });

  comparison.winner.ecosystem = frameworkKeys.reduce((winner, key) => {
    const current = frameworks[key];
    const winnerFw = frameworks[winner];
    return current.metrics.githubStars > winnerFw.metrics.githubStars
      ? key
      : winner;
  });

  return comparison;
}

// Usage:
const comparison = compareFrameworks(["react", "vue", "svelte", "solid"]);
console.log("Bundle Size Winner:", comparison.winner.bundleSize); // svelte
console.log("Ecosystem Winner:", comparison.winner.ecosystem); // react
```

#### Exercise 3: Build Decision Tree

Create framework selector:

```javascript
function selectFramework(projectRequirements) {
  const {
    projectType,
    teamSize,
    performanceCritical,
    seoRequired,
    teamExperience,
  } = projectRequirements;

  // Decision tree
  if (performanceCritical && projectType === "mobile") {
    return {
      recommended: "svelte",
      reason: "Smallest bundle size, best for mobile performance",
      alternatives: ["preact", "solid"],
    };
  }

  if (seoRequired && projectType === "marketing") {
    return {
      recommended: "next",
      reason: "Best SSR/SSG support, great for SEO",
      alternatives: ["nuxt", "astro"],
    };
  }

  if (teamExperience === "react" && teamSize > 5) {
    return {
      recommended: "react",
      reason: "Team already knows it, large ecosystem for big teams",
      alternatives: ["vue"],
    };
  }

  if (teamSize <= 3 && !teamExperience) {
    return {
      recommended: "vue",
      reason: "Best learning curve, good documentation, productive quickly",
      alternatives: ["svelte"],
    };
  }

  if (performanceCritical && projectType === "dashboard") {
    return {
      recommended: "solid",
      reason: "Fastest reactivity, perfect for data-heavy dashboards",
      alternatives: ["svelte", "react"],
    };
  }

  // Default recommendation
  return {
    recommended: "react",
    reason: "Most versatile, largest ecosystem, most jobs",
    alternatives: ["vue", "svelte"],
  };
}

// Usage:
const recommendation = selectFramework({
  projectType: "dashboard",
  teamSize: 10,
  performanceCritical: true,
  seoRequired: false,
  teamExperience: "react",
});

console.log(recommendation);
// {
//   recommended: 'react',
//   reason: 'Team already knows it, large ecosystem for big teams',
//   alternatives: ['vue']
// }
```

#### Exercise 4: Create Your Own Evaluation

Evaluate 3-4 frameworks for YOUR specific use case:

**Step 1: Define Your Requirements**

```javascript
const myProject = {
  type: '?', // marketing, dashboard, mobile, etc.
  seoRequired: ?,
  performanceCritical: ?,
  teamSize: ?,
  teamExperience: ?,
  timeline: ?,
  budget: ?,
  longevity: ? // years
};
```

**Step 2: Score Each Framework**

- Use the evaluation scorecard
- Research each framework thoroughly
- Build small prototype in each
- Measure real metrics

**Step 3: Make Decision**

- Weight scores by project needs
- Consider team preferences
- Factor in long-term maintenance
- Document decision rationale

---

### Reflection Questions

After building:

1. **Decision Making:**

   - What factors matter most?
   - How do you balance tradeoffs?
   - When is "good enough" good enough?

2. **Team Dynamics:**

   - How much should team preference matter?
   - When do you choose learning over familiarity?
   - How do you get buy-in?

3. **Future-Proofing:**

   - How do you evaluate longevity?
   - What are migration risks?
   - How do you avoid regret?

4. **Reality Check:**
   - Can you really go wrong?
   - Are differences overstated?
   - What matters in 5 years?

---

## Section 18: Building Your Own Framework

### The Problem

You understand how frameworks work. Now build one!

**Why build your own framework?**

- Deep understanding of framework internals
- Appreciation for framework complexity
- Custom solution for specific needs
- Learning experience
- Fun challenge!

**You'll build a complete mini-framework with:**

- Reactivity system
- Component system
- Virtual DOM
- Router
- State management

---

### Build It: Complete Framework

#### Exercise 1: Design Your Framework

Define your framework's philosophy:

```javascript
// My Framework: "Minimal"
// Philosophy: Simplicity over features
// Target: Small apps, learning, prototypes
//
// Features:
// - Reactive state with signals
// - Components with lifecycle
// - Virtual DOM for efficient updates
// - Simple router
// - Global state store
// - < 10KB gzipped
//
// Non-goals:
// - Not for large apps
// - No SSR (for simplicity)
// - No build step required
// - No TypeScript (keep it simple)
```

#### Exercise 2: Build Core Reactivity

```javascript
// signals.js
let context = [];

export function createSignal(value) {
  const subscriptions = new Set();

  const read = () => {
    const running = context[context.length - 1];
    if (running) subscriptions.add(running);
    return value;
  };

  const write = (nextValue) => {
    value = nextValue;
    subscriptions.forEach((sub) => sub.execute());
  };

  return [read, write];
}

export function createEffect(fn) {
  const execute = () => {
    context.push(execute);
    try {
      fn();
    } finally {
      context.pop();
    }
  };

  execute.execute = execute;
  execute();
}

export function createMemo(fn) {
  const [read, write] = createSignal();
  createEffect(() => write(fn()));
  return read;
}
```

#### Exercise 3: Build Component System

```javascript
// component.js
import {createEffect} from "./signals.js";

export function createComponent(definition) {
  let isMounted = false;
  let element = null;
  const cleanups = [];

  const component = {
    mount(container, props = {}) {
      if (isMounted) return;

      // Setup reactive rendering
      createEffect(() => {
        const newElement = definition.render(props);

        if (!element) {
          container.appendChild(newElement);
          element = newElement;
          isMounted = true;

          // Call mounted hook
          if (definition.mounted) {
            const cleanup = definition.mounted.call(component, props);
            if (cleanup) cleanups.push(cleanup);
          }
        } else {
          // Update existing element
          element.replaceWith(newElement);
          element = newElement;
        }
      });
    },

    unmount() {
      if (!isMounted) return;

      // Run cleanups
      cleanups.forEach((cleanup) => cleanup());
      cleanups.length = 0;

      // Remove from DOM
      if (element && element.parentNode) {
        element.parentNode.removeChild(element);
      }

      isMounted = false;
      element = null;

      // Call unmounted hook
      if (definition.unmounted) {
        definition.unmounted.call(component);
      }
    },
  };

  return component;
}
```

#### Exercise 4: Build Virtual DOM

```javascript
// vdom.js
export function h(type, props, ...children) {
  return {
    type,
    props: props || {},
    children: children.flat(),
  };
}

export function render(vnode) {
  if (typeof vnode === "string" || typeof vnode === "number") {
    return document.createTextNode(String(vnode));
  }

  if (typeof vnode.type === "function") {
    return render(vnode.type(vnode.props));
  }

  const element = document.createElement(vnode.type);

  // Set props
  Object.entries(vnode.props).forEach(([key, value]) => {
    if (key.startsWith("on")) {
      const event = key.substring(2).toLowerCase();
      element.addEventListener(event, value);
    } else if (key === "className") {
      element.className = value;
    } else {
      element.setAttribute(key, value);
    }
  });

  // Render children
  vnode.children.forEach((child) => {
    element.appendChild(render(child));
  });

  return element;
}

// Simplified diff (no keys)
export function diff(oldVNode, newVNode) {
  // For simplicity, just replace if different
  if (oldVNode.type !== newVNode.type) {
    return {type: "REPLACE", vnode: newVNode};
  }

  // Check if props or children changed
  // (Simplified - real implementation would be more complex)

  return {type: "UPDATE"};
}
```

#### Exercise 5: Build Router

```javascript
// router.js
export function createRouter(routes) {
  let currentRoute = null;
  const listeners = [];

  function matchRoute(path) {
    for (const route of routes) {
      if (route.path === path) {
        return route;
      }

      // Simple param matching
      const pattern = route.path.replace(/:\w+/g, '([^/]+)');
      const regex = new RegExp(`^${pattern}# JavaScript Framework Foundations Self-Mastery Workbook
## Part 2: Advanced Patterns & Mastery (Sections 11-19)

---

## Section 11: Build Tools & Module Bundling

### The Problem

Your app has grown to 50+ files:

```

src/
├── components/
│ ├── Header.js
│ ├── Footer.js
│ ├── Button.js
│ └── ... 20 more
├── utils/
│ ├── api.js
│ ├── format.js
│ └── ... 10 more
├── styles/
│ ├── main.css
│ ├── components.css
│ └── ... 5 more
└── index.js

````

**Problems:**
- How do you load 50+ files in the browser?
- Each file is a separate HTTP request (slow!)
- Files have dependencies on each other
- Need to load in correct order
- CSS needs processing (vendor prefixes, minification)
- Modern JS features not supported in old browsers

**You need a build tool!**

---

### Exploration Questions

#### Module Systems

**Scenario 1: The Module Problem**

```javascript
// utils.js
function formatDate(date) { ... }

// app.js
// How do you use formatDate here?

// Option 1: Global variable (bad!)
window.formatDate = formatDate;

// Option 2: Module system
export function formatDate(date) { ... }
import { formatDate } from './utils.js';
````

**Explore:**

- What is a module system?
- What are CommonJS, ESM, AMD, UMD?
- How do imports/exports work?
- Why do we need bundlers?
- Build a simple module loader

**Scenario 2: Dependency Resolution**

```javascript
// a.js
import {b} from "./b.js";
import {c} from "./c.js";

// b.js
import {c} from "./c.js";

// c.js
export const c = "value";

// What order should files load?
// How do you prevent loading c.js twice?
// How do you detect circular dependencies?
```

**Explore:**

- How do you resolve dependencies?
- What is a dependency graph?
- How do you detect circular dependencies?
- Build a dependency resolver

#### Bundling Concepts

**Scenario 3: Code Splitting**

```javascript
// app.js (100 KB)
import "./home.js"; // 20 KB
import "./dashboard.js"; // 80 KB (rarely used!)

// User visits home page
// Downloads 100 KB but only needs 20 KB!

// Better: Code splitting
const home = import("./home.js"); // 20 KB
const dashboard = import("./dashboard.js"); // Lazy load when needed
```

**Explore:**

- What is code splitting?
- How do dynamic imports work?
- How do you split by route?
- Build code splitting system

**Scenario 4: Tree Shaking**

```javascript
// utils.js
export function used() { ... }
export function unused() { ... }

// app.js
import { used } from './utils.js';

// Bundle should only include used()!
// How does bundler know unused() is never called?
```

**Explore:**

- What is tree shaking?
- How do bundlers eliminate dead code?
- What prevents tree shaking?
- How do you enable tree shaking?

#### Transpilation & Polyfills

**Scenario 5: Modern JS in Old Browsers**

```javascript
// You write modern JS
const greet = (name = 'World') => `Hello ${name}`;
class User { ... }
const data = await fetch('/api');

// Old browsers don't support:
// - Arrow functions
// - Default parameters
// - Classes
// - Async/await

// Transpiler converts to ES5:
var greet = function(name) {
  if (name === undefined) name = 'World';
  return 'Hello ' + name;
};
```

**Explore:**

- What is transpilation?
- How does Babel work?
- What are polyfills?
- When do you need transpilation?
- Build a simple transpiler

---

### Build It: Module Bundler

#### Exercise 1: Build Basic Module Bundler

Create a simple bundler:

```javascript
const fs = require("fs");
const path = require("path");
const babel = require("@babel/core");

function createBundler(entry) {
  // Store modules by filepath
  const modules = new Map();
  let moduleId = 0;

  // Parse a module and its dependencies
  function parseModule(filepath) {
    if (modules.has(filepath)) {
      return modules.get(filepath);
    }

    const id = moduleId++;
    const dirname = path.dirname(filepath);
    const code = fs.readFileSync(filepath, "utf8");

    // Parse with Babel
    const ast = babel.parseSync(code, {
      sourceType: "module",
    });

    const dependencies = [];

    // Find all imports
    babel.traverse(ast, {
      ImportDeclaration({node}) {
        const importPath = node.source.value;
        const absolutePath = path.resolve(dirname, importPath);
        dependencies.push(absolutePath);
      },
    });

    // Transform to regular JS
    const {code: transformedCode} = babel.transformFromAstSync(ast, code, {
      presets: ["@babel/preset-env"],
    });

    const module = {
      id,
      filepath,
      dependencies,
      code: transformedCode,
    };

    modules.set(filepath, module);

    // Recursively parse dependencies
    dependencies.forEach((dep) => {
      parseModule(dep);
    });

    return module;
  }

  // Build dependency graph
  const entryModule = parseModule(entry);

  // Generate bundle
  function generateBundle() {
    const modulesArray = Array.from(modules.values());

    // Create module map
    const moduleMap = modulesArray
      .map((mod) => {
        return `
        ${mod.id}: {
          code: function(require, module, exports) {
            ${mod.code}
          },
          dependencies: ${JSON.stringify(
            mod.dependencies.map((dep) => modules.get(dep).id)
          )}
        }
      `;
      })
      .join(",\n");

    // Bundle template
    return `
      (function(modules) {
        const installedModules = {};
        
        function require(moduleId) {
          if (installedModules[moduleId]) {
            return installedModules[moduleId].exports;
          }
          
          const module = {
            exports: {}
          };
          
          installedModules[moduleId] = module;
          
          modules[moduleId].code(require, module, module.exports);
          
          return module.exports;
        }
        
        require(${entryModule.id});
      })({
        ${moduleMap}
      });
    `;
  }

  return {
    modules,
    bundle: generateBundle(),
  };
}

// Usage:
const bundler = createBundler("./src/index.js");
fs.writeFileSync("./dist/bundle.js", bundler.bundle);
```

**Requirements:**

- Parse entry file
- Find all imports
- Recursively parse dependencies
- Build dependency graph
- Generate single bundle file
- Handle circular dependencies

#### Exercise 2: Add Code Splitting

Implement dynamic imports:

```javascript
function handleDynamicImports(ast) {
  const dynamicImports = [];

  babel.traverse(ast, {
    CallExpression({node}) {
      if (
        node.callee.type === "Import" &&
        node.arguments.length === 1 &&
        node.arguments[0].type === "StringLiteral"
      ) {
        dynamicImports.push(node.arguments[0].value);
      }
    },
  });

  return dynamicImports;
}

function createChunks(modules, entryId) {
  const chunks = new Map();

  // Main chunk (entry + dependencies)
  const mainChunk = {
    id: "main",
    modules: new Set(),
  };

  function addToChunk(moduleId, chunk) {
    if (chunk.modules.has(moduleId)) return;

    chunk.modules.add(moduleId);
    const module = modules.get(moduleId);

    // Add sync dependencies
    module.dependencies.forEach((depId) => {
      if (!module.dynamicDependencies.includes(depId)) {
        addToChunk(depId, chunk);
      }
    });
  }

  addToChunk(entryId, mainChunk);
  chunks.set("main", mainChunk);

  // Create chunk for each dynamic import
  modules.forEach((module) => {
    module.dynamicDependencies.forEach((depId) => {
      const chunkId = `chunk-${depId}`;

      if (!chunks.has(chunkId)) {
        const chunk = {
          id: chunkId,
          modules: new Set(),
        };

        addToChunk(depId, chunk);
        chunks.set(chunkId, chunk);
      }
    });
  });

  return chunks;
}

// Generate multiple bundle files
function generateChunks(chunks) {
  return Array.from(chunks.values()).map((chunk) => {
    return {
      filename: `${chunk.id}.js`,
      code: generateChunkCode(chunk),
    };
  });
}
```

#### Exercise 3: Add Tree Shaking

Eliminate unused exports:

```javascript
function analyzeExports(ast) {
  const exports = new Set();

  babel.traverse(ast, {
    ExportNamedDeclaration({node}) {
      if (node.declaration) {
        if (node.declaration.declarations) {
          node.declaration.declarations.forEach((decl) => {
            exports.add(decl.id.name);
          });
        } else if (node.declaration.id) {
          exports.add(node.declaration.id.name);
        }
      }

      if (node.specifiers) {
        node.specifiers.forEach((spec) => {
          exports.add(spec.exported.name);
        });
      }
    },

    ExportDefaultDeclaration({node}) {
      exports.add("default");
    },
  });

  return exports;
}

function analyzeImports(ast) {
  const imports = new Map();

  babel.traverse(ast, {
    ImportDeclaration({node}) {
      const source = node.source.value;
      const imported = new Set();

      node.specifiers.forEach((spec) => {
        if (spec.type === "ImportSpecifier") {
          imported.add(spec.imported.name);
        } else if (spec.type === "ImportDefaultSpecifier") {
          imported.add("default");
        } else if (spec.type === "ImportNamespaceSpecifier") {
          imported.add("*");
        }
      });

      imports.set(source, imported);
    },
  });

  return imports;
}

function eliminateDeadCode(modules) {
  // Build usage graph
  const used = new Set();

  // Start from entry
  function markUsed(moduleId) {
    if (used.has(moduleId)) return;
    used.add(moduleId);

    const module = modules.get(moduleId);
    const imports = analyzeImports(module.ast);

    imports.forEach((importedNames, source) => {
      const depModule = modules.get(source);
      const exports = analyzeExports(depModule.ast);

      // Mark imported names as used
      importedNames.forEach((name) => {
        if (name === "*") {
          // Import everything
          markUsed(depModule.id);
        } else if (exports.has(name)) {
          // Mark this export as used
          depModule.usedExports.add(name);
          markUsed(depModule.id);
        }
      });
    });
  }

  markUsed(entryModule.id);

  // Remove unused modules
  modules.forEach((module, id) => {
    if (!used.has(id)) {
      modules.delete(id);
    }
  });

  // Remove unused exports
  modules.forEach((module) => {
    if (module.usedExports.size > 0) {
      removeUnusedExports(module.ast, module.usedExports);
    }
  });
}
```

#### Exercise 4: Compare Build Tools

Research popular build tools:

| Feature            | Your Bundler | Webpack    | Rollup    | Vite        | esbuild        | Parcel    |
| ------------------ | ------------ | ---------- | --------- | ----------- | -------------- | --------- |
| **Speed**          | Slow         | Medium     | Fast      | Very Fast   | Fastest        | Fast      |
| **Config**         | Code         | Complex    | Simple    | Minimal     | Minimal        | Zero      |
| **Code Splitting** | Basic        | Advanced   | Advanced  | Advanced    | Advanced       | Advanced  |
| **Tree Shaking**   | Basic        | Yes        | Best      | Yes         | Yes            | Yes       |
| **HMR**            | No           | Yes        | Plugin    | Built-in    | No             | Yes       |
| **Use Case**       | Learning     | Production | Libraries | Development | Speed critical | Beginners |

**Study their approaches:**

**Webpack:**

- Most configurable
- Loader system
- Plugin ecosystem
- Code splitting built-in

**Vite:**

- ESM in development
- No bundling in dev
- Lightning fast
- Rollup in production

**esbuild:**

- Written in Go
- Fastest bundler
- Limited plugins
- Growing ecosystem

#### Exercise 5: Build Development Server with HMR

Create dev server with Hot Module Replacement:

```javascript
const express = require("express");
const WebSocket = require("ws");
const chokidar = require("chokidar");

function createDevServer(bundler, options = {}) {
  const app = express();
  const wss = new WebSocket.Server({port: options.wsPort || 3001});

  // Serve bundle
  app.get("/bundle.js", (req, res) => {
    const bundle = bundler.bundle();
    res.type("application/javascript");
    res.send(bundle);
  });

  // Inject HMR client
  const hmrClient = `
    const ws = new WebSocket('ws://localhost:${options.wsPort || 3001}');
    
    ws.onmessage = (event) => {
      const data = JSON.parse(event.data);
      
      if (data.type === 'reload') {
        window.location.reload();
      } else if (data.type === 'update') {
        // Hot update
        const script = document.createElement('script');
        script.src = '/bundle.js?' + Date.now();
        document.body.appendChild(script);
      }
    };
  `;

  app.get("/hmr-client.js", (req, res) => {
    res.type("application/javascript");
    res.send(hmrClient);
  });

  // Watch files
  const watcher = chokidar.watch("./src", {
    ignored: /node_modules/,
  });

  watcher.on("change", (filepath) => {
    console.log(`File changed: ${filepath}`);

    // Rebuild
    bundler.rebuild();

    // Notify clients
    wss.clients.forEach((client) => {
      if (client.readyState === WebSocket.OPEN) {
        client.send(
          JSON.stringify({
            type: "update",
            file: filepath,
          })
        );
      }
    });
  });

  app.listen(options.port || 3000, () => {
    console.log(
      `Dev server running on http://localhost:${options.port || 3000}`
    );
  });
}

// Usage:
const bundler = createBundler("./src/index.js");
createDevServer(bundler, {port: 3000, wsPort: 3001});
```

---

### Reflection Questions

After building:

1. **Bundling Basics:**

   - Why do we need bundlers?
   - What problems do they solve?
   - What complexity do they add?

2. **Performance:**

   - How does code splitting help?
   - When is tree shaking important?
   - What are the tradeoffs?

3. **Tool Comparison:**

   - When would you use Webpack vs Vite?
   - When is zero-config better?
   - How do you choose?

4. **Future:**
   - Will we always need bundlers?
   - What is ESM native?
   - What's the trend?

---

## Section 12: Security & XSS Prevention

### The Problem

Your app accepts user input and displays it:

```javascript
const comment = getUserComment(); // "<script>alert('hacked')</script>"
container.innerHTML = comment; // XSS vulnerability!
// Script executes! User can steal data, cookies, etc.
```

**Security threats:**

- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- SQL Injection (backend)
- Sensitive data exposure
- Dependency vulnerabilities

**How do you build secure apps?**

---

### Exploration Questions

#### XSS Attacks

**Scenario 1: The innerHTML Trap**

```javascript
// User submits: <img src=x onerror="alert('XSS')">
const userInput = "<img src=x onerror=\"alert('XSS')\">";

// Vulnerable:
container.innerHTML = userInput; // XSS!

// Safe:
container.textContent = userInput; // Just text

// But what if you need HTML?
const safeName = escapeHtml(userInput);
container.innerHTML = `<div>${safeName}</div>`;
```

**Explore:**

- What is XSS?
- How do XSS attacks work?
- What's the difference between innerHTML and textContent?
- How do you sanitize HTML?
- Build HTML sanitizer

**Scenario 2: Different XSS Types**

```javascript
// Stored XSS (saved in database)
saveComment("<script>steal()</script>");
// Later displayed to all users

// Reflected XSS (in URL)
https://site.com/search?q=<script>steal()</script>
// Displayed back to user

// DOM-based XSS
const hash = location.hash;
element.innerHTML = hash; // Vulnerable!
```

**Explore:**

- What are XSS types?
- How do you prevent each?
- What is CSP (Content Security Policy)?
- Build XSS protection

**Scenario 3: URL Injection**

```javascript
// User input: javascript:alert('XSS')
const url = getUserInput();

// Vulnerable:
<a href="${url}">Click</a>;
// Clicking executes JavaScript!

// Safe:
const safeUrl = sanitizeUrl(url);
```

**Explore:**

- What protocols are dangerous?
- How do you validate URLs?
- What is allowlist vs denylist?
- Build URL validator

#### Framework Protection

**Scenario 4: How Frameworks Prevent XSS**

```javascript
// React (safe by default)
const name = "<script>alert('xss')</script>";
<div>{name}</div>
// Renders as text, not script!

// Vue (safe by default)
<div>{{ userInput }}</div>
// Automatically escaped

// Svelte (safe by default)
<div>{userInput}</div>
// Automatically escaped

// BUT: Can be bypassed!
// React:
<div dangerouslySetInnerHTML={{__html: userInput}} />
// Vue:
<div v-html="userInput"></div>
// Svelte:
<div>{@html userInput}</div>
```

**Explore:**

- How do frameworks escape by default?
- When do you need to bypass escaping?
- How do you do it safely?
- Build auto-escaping template system

#### CSRF Protection

**Scenario 5: Cross-Site Request Forgery**

```javascript
// User is logged into bank.com
// Visits evil.com which has:
<img src="https://bank.com/transfer?to=hacker&amount=1000" />;
// Transfers money using user's cookies!

// Protection: CSRF tokens
// Server sends token
const csrfToken = generateToken();

// Client includes token in requests
fetch("/transfer", {
  method: "POST",
  headers: {
    "X-CSRF-Token": csrfToken,
  },
  body: {to: "recipient", amount: 100},
});
```

**Explore:**

- What is CSRF?
- How does CSRF token work?
- What is SameSite cookie attribute?
- Build CSRF protection

---

### Build It: Security Layer

#### Exercise 1: Build HTML Sanitizer

Create safe HTML renderer:

```javascript
function sanitizeHtml(html) {
  // Parse HTML
  const doc = new DOMParser().parseFromString(html, "text/html");

  // Allowlist of safe tags
  const allowedTags = [
    "p",
    "br",
    "strong",
    "em",
    "u",
    "a",
    "ul",
    "ol",
    "li",
    "h1",
    "h2",
    "h3",
    "h4",
    "h5",
    "h6",
    "blockquote",
    "code",
    "pre",
  ];

  // Allowlist of safe attributes
  const allowedAttrs = {
    a: ["href", "title"],
    img: ["src", "alt"],
    "*": ["class"], // All tags can have class
  };

  function sanitizeNode(node) {
    // Remove if not allowed tag
    if (node.nodeType === Node.ELEMENT_NODE) {
      const tagName = node.tagName.toLowerCase();

      if (!allowedTags.includes(tagName)) {
        node.remove();
        return;
      }

      // Remove disallowed attributes
      Array.from(node.attributes).forEach((attr) => {
        const attrName = attr.name.toLowerCase();
        const allowed = allowedAttrs[tagName] || [];
        const globalAllowed = allowedAttrs["*"] || [];

        if (!allowed.includes(attrName) && !globalAllowed.includes(attrName)) {
          node.removeAttribute(attrName);
        }

        // Special handling for href
        if (attrName === "href") {
          const href = attr.value;
          if (!isUrlSafe(href)) {
            node.removeAttribute("href");
          }
        }
      });

      // Remove event handlers
      Array.from(node.attributes).forEach((attr) => {
        if (attr.name.toLowerCase().startsWith("on")) {
          node.removeAttribute(attr.name);
        }
      });

      // Recursively sanitize children
      Array.from(node.childNodes).forEach(sanitizeNode);
    }
  }

  function isUrlSafe(url) {
    try {
      const parsed = new URL(url, window.location.origin);
      const protocol = parsed.protocol;

      // Only allow safe protocols
      return ["http:", "https:", "mailto:"].includes(protocol);
    } catch {
      return false;
    }
  }

  Array.from(doc.body.childNodes).forEach(sanitizeNode);

  return doc.body.innerHTML;
}

// Usage:
const userHtml = `
  <p>Hello <strong>world</strong></p>
  <script>alert('xss')</script>
  <img src=x onerror="alert('xss')">
  <a href="javascript:alert('xss')">Click</a>
  <a href="https://safe.com">Safe link</a>
`;

const safeHtml = sanitizeHtml(userHtml);
// Result:
// <p>Hello <strong>world</strong></p>
// <a href="https://safe.com">Safe link</a>
```

**Requirements:**

- Parse HTML safely
- Allowlist safe tags only
- Remove dangerous attributes
- Remove event handlers
- Validate URLs
- Handle nested elements

#### Exercise 2: Build Auto-Escaping Template System

Create templates that escape by default:

```javascript
function createTemplate(strings, ...values) {
  return {
    toString() {
      return strings.reduce((result, string, i) => {
        const value = values[i - 1];
        const escaped = escapeHtml(value);
        return result + escaped + string;
      });
    },

    toHtmlString() {
      return this.toString();
    },
  };
}

function escapeHtml(unsafe) {
  if (unsafe == null) return "";

  return String(unsafe)
    .replace(/&/g, "&amp;")
    .replace(/</g, "&lt;")
    .replace(/>/g, "&gt;")
    .replace(/"/g, "&quot;")
    .replace(/'/g, "&#039;");
}

function html(strings, ...values) {
  return createTemplate(strings, ...values);
}

// Mark as safe (already sanitized)
function safe(htmlString) {
  return {
    __safe: true,
    toString() {
      return htmlString;
    },
  };
}

function render(template) {
  return template.toString();
}

// Usage:
const name = "<script>alert('xss')</script>";
const greeting = html`<div>Hello ${name}</div>`;

console.log(render(greeting));
// <div>Hello &lt;script&gt;alert('xss')&lt;/script&gt;</div>

// Explicitly mark as safe
const safeHtml = safe("<strong>Bold</strong>");
const content = html`<div>${safeHtml}</div>`;

console.log(render(content));
// <div><strong>Bold</strong></div>
```

#### Exercise 3: Build CSP Helper

Create Content Security Policy generator:

```javascript
function createCspPolicy(options = {}) {
  const directives = [];

  // default-src
  if (options.defaultSrc) {
    directives.push(`default-src ${options.defaultSrc.join(" ")}`);
  } else {
    directives.push("default-src 'self'");
  }

  // script-src
  if (options.scriptSrc) {
    const sources = options.scriptSrc;

    if (options.allowInlineScripts) {
      sources.push("'unsafe-inline'");
    }
    if (options.allowEval) {
      sources.push("'unsafe-eval'");
    }
    if (options.scriptNonce) {
      sources.push(`'nonce-${options.scriptNonce}'`);
    }

    directives.push(`script-src ${sources.join(" ")}`);
  }

  // style-src
  if (options.styleSrc) {
    const sources = options.styleSrc;

    if (options.allowInlineStyles) {
      sources.push("'unsafe-inline'");
    }

    directives.push(`style-src ${sources.join(" ")}`);
  }

  // img-src
  if (options.imgSrc) {
    directives.push(`img-src ${options.imgSrc.join(" ")}`);
  }

  // connect-src (APIs)
  if (options.connectSrc) {
    directives.push(`connect-src ${options.connectSrc.join(" ")}`);
  }

  // font-src
  if (options.fontSrc) {
    directives.push(`font-src ${options.fontSrc.join(" ")}`);
  }

  // frame-src
  if (options.frameSrc) {
    directives.push(`frame-src ${options.frameSrc.join(" ")}`);
  }

  return directives.join("; ");
}

// Usage:
const csp = createCspPolicy({
  defaultSrc: ["'self'"],
  scriptSrc: ["'self'", "https://cdn.example.com"],
  styleSrc: ["'self'", "https://fonts.googleapis.com"],
  imgSrc: ["'self'", "data:", "https:"],
  connectSrc: ["'self'", "https://api.example.com"],
  fontSrc: ["'self'", "https://fonts.gstatic.com"],
  frameSrc: ["'none'"],
});

// Set in HTTP header:
// Content-Security-Policy: default-src 'self'; script-src 'self' https://cdn.example.com; ...

// Or in HTML:
// <meta http-equiv="Content-Security-Policy" content="...">
```

#### Exercise 4: Build Security Checklist Tool

Create security audit tool:

```javascript
function auditSecurity(code) {
  const issues = [];

  // Check for innerHTML usage
  if (code.includes("innerHTML")) {
    issues.push({
      severity: "high",
      type: "xss",
      message: "innerHTML usage detected - potential XSS",
      line: findLine(code, "innerHTML"),
    });
  }

  // Check for eval usage
  if (code.includes("eval(")) {
    issues.push({
      severity: "critical",
      type: "code-injection",
      message: "eval() usage detected - avoid eval",
      line: findLine(code, "eval("),
    });
  }

  // Check for dangerouslySetInnerHTML
  if (code.includes("dangerouslySetInnerHTML")) {
    issues.push({
      severity: "high",
      type: "xss",
      message: "dangerouslySetInnerHTML usage - ensure input is sanitized",
      line: findLine(code, "dangerouslySetInnerHTML"),
    });
  }

  // Check for document.write
  if (code.includes("document.write")) {
    issues.push({
      severity: "medium",
      type: "xss",
      message: "document.write usage - prefer safe DOM methods",
      line: findLine(code, "document.write"),
    });
  }

  // Check for window.location usage
  if (code.includes("window.location.hash") || code.includes("location.hash")) {
    issues.push({
      severity: "medium",
      type: "xss",
      message: "Using location.hash - ensure proper sanitization",
      line: findLine(code, "location.hash"),
    });
  }

  return {
    issues,
    score: calculateScore(issues),
    recommendations: generateRecommendations(issues),
  };
}

function calculateScore(issues) {
  const weights = {
    critical: 25,
    high: 10,
    medium: 5,
    low: 2,
  };

  const deductions = issues.reduce((total, issue) => {
    return total + weights[issue.severity];
  }, 0);

  return Math.max(0, 100 - deductions);
}

// Usage:
const code = fs.readFileSync("./app.js", "utf8");
const audit = auditSecurity(code);

console.log(`Security Score: ${audit.score}/100`);
console.log("\nIssues found:");
audit.issues.forEach((issue) => {
  console.log(`  [${issue.severity}] ${issue.message} (line ${issue.line})`);
});
```

#### Exercise 5: Compare Framework Security

Research how frameworks handle security:

| Feature                   | React                     | Vue 3    | Svelte    | Solid.js    |
| ------------------------- | ------------------------- | -------- | --------- | ----------- |
| **Default Escaping**      | Yes                       | Yes      | Yes       | Yes         |
| **Bypass Escaping**       | `dangerouslySetInnerHTML` | `v-html` | `{@html}` | `innerHTML` |
| **URL Sanitization**      | Manual                    | Manual   | Manual    | Manual      |
| **CSP Support**           | Yes                       | Yes      | Yes       | Yes         |
| **Built-in Sanitization** | No                        | No       | No        | No          |
| **XSS Protection**        | Good                      | Good     | Good      | Good        |

**Best practices across frameworks:**

- Always escape user input
- Use CSP headers
- Validate URLs
- Sanitize HTML if needed
- Avoid eval, Function constructor
- Use HTTPS only
- Validate on server too
- Keep dependencies updated

---

### Reflection Questions

After building:

1. **XSS Prevention:**

   - Why is XSS so common?
   - How do frameworks help?
   - What can still go wrong?

2. **Security Layers:**

   - What is defense in depth?
   - Where should validation happen?
   - Client-side vs server-side?

3. **Framework Comparison:**

   - Do frameworks make security easier?
   - What are common pitfalls?
   - What's the developer's responsibility?

4. **Best Practices:**
   - What should ALWAYS be done?
   - What are acceptable risks?
   - How do you stay secure?

---

## Section 13: Testing Framework Applications

### The Problem

You built a complex app. How do you know it works?

```javascript
// Manual testing:
// 1. Open browser
// 2. Click button
// 3. Check if it works
// 4. Repeat for every feature
// 5. Repeat after every change
// Time-consuming! Error-prone!

// Better: Automated tests
test("button increments count", () => {
  const button = render(<Counter />);
  button.click();
  expect(count).toBe(1);
});
```

**Types of tests:**

- Unit tests (test functions)
- Component tests (test components)
- Integration tests (test features)
- E2E tests (test full user flows)

**How do you test framework applications?**

---

### Exploration Questions

#### Testing Fundamentals

**Scenario 1: What Makes Code Testable?**

```javascript
// Hard to test (side effects)
function saveUser() {
  const name = document.querySelector("#name").value;
  fetch("/api/users", {
    method: "POST",
    body: JSON.stringify({name}),
  });
}

// Easy to test (pure function)
function createUser(name) {
  return {name, createdAt: Date.now()};
}

test("createUser creates user object", () => {
  const user = createUser("Alice");
  expect(user.name).toBe("Alice");
  expect(user.createdAt).toBeDefined();
});
```

**Explore:**

- What makes code testable?
- What are pure functions?
- How do you test side effects?
- How do you mock dependencies?
- Build a test framework

**Scenario 2: Component Testing**

```javascript
// Component
function Counter() {
  let count = 0;

  return {
    increment() {
      count++;
    },
    decrement() {
      count--;
    },
    getCount() {
      return count;
    },
  };
}

// How do you test this?
test("counter increments", () => {
  const counter = Counter();
  counter.increment();
  expect(counter.getCount()).toBe(1);
});

// But what about DOM rendering?
// What about user interactions?
```

**Explore:**

- How do you test components?
- How do you simulate user interactions?
- How do you check DOM output?
- Build component testing utilities

#### Test Types

**Scenario 3: The Testing Pyramid**

```
       /\
      /E2E\      ← Few, slow, high confidence
     /------\
    /  INT   \   ← Some, medium speed
   /----------\
  /   UNIT     \ ← Many, fast, low confidence
 /--------------\
```

**Explore:**

- What is the testing pyramid?
- When do you use each test type?
- How do you balance tests?
- Build all three types

**Scenario 4: Mocking**

```javascript
// Code that fetches data
async function loadUser(id) {
  const response = await fetch(`/api/users/${id}`);
  return response.json();
}

// How do you test without making real API calls?
test("loadUser fetches user", async () => {
  // Mock fetch
  global.fetch = jest.fn(() =>
    Promise.resolve({
      json: () => Promise.resolve({id: 1, name: "Alice"}),
    })
  );

  const user = await loadUser(1);
  expect(user.name).toBe("Alice");
});
```

**Explore:**

- What is mocking?
- When should you mock?
- When should you NOT mock?
- Build a mocking system

---

### Build It: Testing Framework

#### Exercise 1: Build Simple Test Framework

Create a test runner:

```javascript
class TestFramework {
  constructor() {
    this.tests = [];
    this.beforeEachFns = [];
    this.afterEachFns = [];
  }

  test(description, fn) {
    this.tests.push({description, fn});
  }

  beforeEach(fn) {
    this.beforeEachFns.push(fn);
  }

  afterEach(fn) {
    this.afterEachFns.push(fn);
  }

  async run() {
    console.log("\n🧪 Running tests...\n");

    let passed = 0;
    let failed = 0;

    for (const test of this.tests) {
      // Run beforeEach hooks
      for (const fn of this.beforeEachFns) {
        await fn();
      }

      try {
        await test.fn();
        console.log(`✅ ${test.description}`);
        passed++;
      } catch (error) {
        console.log(`❌ ${test.description}`);
        console.log(`   ${error.message}`);
        failed++;
      }

      // Run afterEach hooks
      for (const fn of this.afterEachFns) {
        await fn();
      }
    }

    console.log(`\n📊 Results: ${passed} passed, ${failed} failed`);

    return {passed, failed, total: this.tests.length};
  }
}

// Assertion library
class Expect {
  constructor(actual) {
    this.actual = actual;
  }

  toBe(expected) {
    if (this.actual !== expected) {
      throw new Error(
        `Expected ${JSON.stringify(expected)} but got ${JSON.stringify(
          this.actual
        )}`
      );
    }
  }

  toEqual(expected) {
    if (JSON.stringify(this.actual) !== JSON.stringify(expected)) {
      throw new Error(
        `Expected ${JSON.stringify(expected)} but got ${JSON.stringify(
          this.actual
        )}`
      );
    }
  }

  toBeTruthy() {
    if (!this.actual) {
      throw new Error(`Expected truthy but got ${this.actual}`);
    }
  }

  toContain(item) {
    if (!this.actual.includes(item)) {
      throw new Error(`Expected array to contain ${item}`);
    }
  }

  toThrow() {
    try {
      this.actual();
      throw new Error("Expected function to throw");
    } catch (error) {
      // Expected
    }
  }
}

function expect(actual) {
  return new Expect(actual);
}

// Usage:
const framework = new TestFramework();

framework.beforeEach(() => {
  console.log("  Setting up test...");
});

framework.test("addition works", () => {
  expect(1 + 1).toBe(2);
});

framework.test("arrays are equal", () => {
  expect([1, 2, 3]).toEqual([1, 2, 3]);
});

framework.test("string contains substring", () => {
  expect("hello world").toContain("world");
});

framework.run();
```

#### Exercise 2: Build Component Testing Utilities

Create DOM testing helpers:

```javascript
function createTestEnvironment() {
  // Create clean DOM for each test
  const container = document.createElement("div");
  document.body.appendChild(container);

  function cleanup() {
    document.body.removeChild(container);
  }

  function render(component) {
    const element = component.render();
    container.appendChild(element);

    return {
      container,
      element,

      // Query helpers
      getByText(text) {
        return Array.from(container.querySelectorAll("*")).find(
          (el) => el.textContent === text
        );
      },

      getByTestId(testId) {
        return container.querySelector(`[data-testid="${testId}"]`);
      },

      getByRole(role) {
        return container.querySelector(`[role="${role}"]`);
      },

      // Event helpers
      async click(element) {
        element.click();
        await waitForUpdate();
      },

      async type(element, text) {
        element.value = text;
        element.dispatchEvent(new Event("input", {bubbles: true}));
        await waitForUpdate();
      },

      // Wait helpers
      async waitForUpdate() {
        return new Promise((resolve) => setTimeout(resolve, 0));
      },

      async waitFor(callback, {timeout = 1000} = {}) {
        const startTime = Date.now();

        while (Date.now() - startTime < timeout) {
          try {
            const result = callback();
            if (result) return result;
          } catch (e) {
            // Keep waiting
          }

          await new Promise((resolve) => setTimeout(resolve, 50));
        }

        throw new Error("Timeout waiting for condition");
      },
    };
  }

  return {render, cleanup};
}

// Usage:
test("Counter component increments", async () => {
  const {render, cleanup, click, getByText} = createTestEnvironment();

  try {
    const counter = createCounter();
    const {element} = render(counter);

    const button = getByText("Increment");
    await click(button);

    const count = getByText("Count: 1");
    expect(count).toBeTruthy();
  } finally {
    cleanup();
  }
});
```

#### Exercise 3: Build Mock System

Create mocking utilities:

```javascript
class Mock {
  constructor() {
    this.calls = [];
    this.returnValue = undefined;
    this.implementation = null;
  }

  mockReturnValue(value) {
    this.returnValue = value;
    return this;
  }

  mockImplementation(fn) {
    this.implementation = fn;
    return this;
  }

  mockResolvedValue(value) {
    this.implementation = () => Promise.resolve(value);
    return this;
  }

  mockRejectedValue(error) {
    this.implementation = () => Promise.reject(error);
    return this;
  }

  call(...args) {
    this.calls.push(args);

    if (this.implementation) {
      return this.implementation(...args);
    }

    return this.returnValue;
  }

  toHaveBeenCalled() {
    return this.calls.length > 0;
  }

  toHaveBeenCalledTimes(times) {
    return this.calls.length === times;
  }

  toHaveBeenCalledWith(...args) {
    return this.calls.some(
      (call) => JSON.stringify(call) === JSON.stringify(args)
    );
  }
}

function createMock() {
  const mock = new Mock();
  const fn = (...args) => mock.call(...args);

  // Copy methods to function
  fn.mockReturnValue = mock.mockReturnValue.bind(mock);
  fn.mockImplementation = mock.mockImplementation.bind(mock);
  fn.mockResolvedValue = mock.mockResolvedValue.bind(mock);
  fn.mockRejectedValue = mock.mockRejectedValue.bind(mock);
  fn.toHaveBeenCalled = mock.toHaveBeenCalled.bind(mock);
  fn.toHaveBeenCalledTimes = mock.toHaveBeenCalledTimes.bind(mock);
  fn.toHaveBeenCalledWith = mock.toHaveBeenCalledWith.bind(mock);

  return fn;
}

// Usage:
test("API call is made correctly", async () => {
  const mockFetch = createMock();
  mockFetch.mockResolvedValue({
    json: () => Promise.resolve({id: 1, name: "Alice"}),
  });

  global.fetch = mockFetch;

  const user = await loadUser(1);

  expect(user.name).toBe("Alice");
  expect(mockFetch.toHaveBeenCalledTimes(1));
  expect(mockFetch.toHaveBeenCalledWith("/api/users/1"));
});
```

#### Exercise 4: Compare Testing Libraries

Research popular testing tools:

| Tool                | Type             | Framework        | Features                    |
| ------------------- | ---------------- | ---------------- | --------------------------- |
| **Jest**            | Unit/Integration | Any              | Snapshot, mocking, coverage |
| **Vitest**          | Unit/Integration | Vite             | Fast, ESM native            |
| **Testing Library** | Component        | React/Vue/Svelte | User-centric queries        |
| **Cypress**         | E2E              | Any              | Browser automation          |
| **Playwright**      | E2E              | Any              | Multi-browser               |
| **Puppeteer**       | E2E              | Any              | Chrome automation           |

**Study their approaches:**

**React Testing Library:**

```javascript
import {render, screen, fireEvent} from "@testing-library/react";

test("button increments count", () => {
  render(<Counter />);

  const button = screen.getByRole("button", {name: /increment/i});
  fireEvent.click(button);

  expect(screen.getByText("Count: 1")).toBeInTheDocument();
});
```

**Cypress:**

```javascript
describe("Counter", () => {
  it("increments count", () => {
    cy.visit("/counter");
    cy.contains("Increment").click();
    cy.contains("Count: 1");
  });
});
```

#### Exercise 5: Write Complete Test Suite

Test a todo app thoroughly:

```javascript
describe("Todo App", () => {
  describe("Unit Tests", () => {
    test("createTodo creates todo object", () => {
      const todo = createTodo("Buy milk");
      expect(todo).toEqual({
        id: expect.any(String),
        text: "Buy milk",
        done: false,
      });
    });

    test("toggleTodo toggles done status", () => {
      const todo = {id: "1", text: "Task", done: false};
      const toggled = toggleTodo(todo);
      expect(toggled.done).toBe(true);
    });
  });

  describe("Component Tests", () => {
    test("renders todo list", () => {
      const todos = [
        {id: "1", text: "Task 1", done: false},
        {id: "2", text: "Task 2", done: true},
      ];

      const {getByText} = render(TodoList, {todos});

      expect(getByText("Task 1")).toBeTruthy();
      expect(getByText("Task 2")).toBeTruthy();
    });

    test("adds new todo", async () => {
      const {getByTestId, getByText, type, click} = render(TodoApp);

      await type(getByTestId("todo-input"), "New task");
      await click(getByText("Add"));

      expect(getByText("New task")).toBeTruthy();
    });

    test("toggles todo", async () => {
      const todos = [{id: "1", text: "Task", done: false}];
      const {getByTestId, click} = render(TodoList, {todos});

      await click(getByTestId("todo-checkbox-1"));

      expect(getByTestId("todo-checkbox-1").checked).toBe(true);
    });
  });

  describe("Integration Tests", () => {
    test("todo persists to localStorage", async () => {
      const {getByTestId, type, click} = render(TodoApp);

      await type(getByTestId("todo-input"), "Persistent task");
      await click(getByText("Add"));

      const saved = JSON.parse(localStorage.getItem("todos"));
      expect(saved).toContainEqual(
        expect.objectContaining({text: "Persistent task"})
      );
    });

    test("filter buttons work", async () => {
      const todos = [
        {id: "1", text: "Active", done: false},
        {id: "2", text: "Done", done: true},
      ];

      const {getByText, click} = render(TodoApp, {todos});

      // Show active
      await click(getByText("Active"));
      expect(getByText("Active")).toBeTruthy();
      expect(() => getByText("Done")).toThrow();

      // Show completed
      await click(getByText("Completed"));
      expect(() => getByText("Active")).toThrow();
      expect(getByText("Done")).toBeTruthy();
    });
  });

  describe("E2E Tests", () => {
    test("complete user flow", async () => {
      await page.goto("http://localhost:3000");

      // Add todo
      await page.fill('[data-testid="todo-input"]', "E2E task");
      await page.click("text=Add");

      // Verify added
      await page.waitForSelector("text=E2E task");

      // Toggle todo
      await page.click('[data-testid="todo-checkbox-1"]');

      // Verify toggled
      const checkbox = await page.$('[data-testid="todo-checkbox-1"]');
      expect(await checkbox.isChecked()).toBe(true);

      // Delete todo
      await page.click('[data-testid="todo-delete-1"]');

      // Verify deleted
      expect(await page.$("text=E2E task")).toBeNull();
    });
  });
});
```

---

### Reflection Questions

After building:

1. **Testing Strategy:**

   - How many tests of each type?
   - When is each type appropriate?
   - What's the right balance?

2. **Test Quality:**

   - What makes a good test?
   - What makes a bad test?
   - How do you avoid brittle tests?

3. **Mocking:**

   - When should you mock?
   - When should you NOT mock?
   - What are integration tests for?

4. **Framework Testing:**
   - How do frameworks make testing easier?
   - What's still hard to test?
   - What are best practices?

---

## Section 14: Accessibility & Internationalization

### The Problem

Your app works great for you, but:

- Screen reader users can't navigate it
- Keyboard users can't use it
- Users in other countries can't read it
- Right-to-left language users see broken layouts

**Accessibility (a11y) and Internationalization (i18n) are essential for inclusive apps.**

---

### Exploration Questions

#### Accessibility Basics

**Scenario 1: Keyboard Navigation**

```javascript
// Bad: Only works with mouse
<div onClick={handleClick}>Click me</div>
// Can't be focused or activated with keyboard!

// Good: Semantic HTML
<button onClick={handleClick}>Click me</button>
// Focusable, keyboard accessible, screen reader friendly

// Custom element that needs keyboard support
<div
  role="button"
  tabIndex={0}
  onClick={handleClick}
  onKeyPress={(e) => {
    if (e.key === 'Enter' || e.key === ' ') {
      handleClick();
    }
  }}
>
  Click me
</div>
```

**Explore:**

- Why is keyboard navigation important?
- What is focus management?
- How do you make custom elements accessible?
- Build keyboard navigation system

**Scenario 2: Screen Readers**

```javascript
// Bad: No context
<button>Submit</button>
// Screen reader: "Button, Submit" - submit what?

// Good: Descriptive
<button aria-label="Submit registration form">Submit</button>
// Screen reader: "Button, Submit registration form"

// Images need alt text
<img src="graph.png" alt="Sales graph showing 30% increase" />

// Loading states
<div aria-live="polite" aria-busy={loading}>
  {loading ? 'Loading...' : content}
</div>
// Screen reader announces when content changes
```

**Explore:**

- How do screen readers work?
- What are ARIA attributes?
- When do you need ARIA?
- Build accessible components

#### Internationalization

**Scenario 3: Text Translation**

```javascript
// Bad: Hardcoded text
<button>Submit</button>

// Good: Translatable
<button>{t('form.submit')}</button>

// Translation files:
// en.json
{
  "form": {
    "submit": "Submit",
    "cancel": "Cancel"
  }
}

// es.json
{
  "form": {
    "submit": "Enviar",
    "cancel": "Cancelar"
  }
}
```

**Explore:**

- How do you structure translations?
- How do you handle plurals?
- How do you handle variables?
- Build i18n system

**Scenario 4: Date/Number Formatting**

```javascript
// Bad: US-centric
const date = "12/31/2024"; // Ambiguous!
const price = "$" + amount;

// Good: Locale-aware
const date = new Intl.DateTimeFormat("en-US").format(new Date());
// en-US: "12/31/2024"
// en-GB: "31/12/2024"

const price = new Intl.NumberFormat("en-US", {
  style: "currency",
  currency: "USD",
}).format(amount);
// en-US: "$1,234.56"
// de-DE: "1.234,56 $"
```

**Explore:**

- How do you format dates/numbers by locale?
- What is the Intl API?
- How do you detect user locale?
- Build formatting utilities

---

### Build It: Accessible & International App

#### Exercise 1: Build Accessible Component Library

Create accessible components:

```javascript
// Accessible Button
function AccessibleButton({
  children,
  onClick,
  disabled = false,
  ariaLabel,
  ariaDescribedBy,
  type = "button",
}) {
  return {
    render() {
      const button = document.createElement("button");
      button.type = type;
      button.textContent = children;
      button.disabled = disabled;

      if (ariaLabel) {
        button.setAttribute("aria-label", ariaLabel);
      }

      if (ariaDescribedBy) {
        button.setAttribute("aria-describedby", ariaDescribedBy);
      }

      button.addEventListener("click", onClick);

      return button;
    },
  };
}

// Accessible Modal
function AccessibleModal({title, content, onClose}) {
  let previousFocus = null;

  return {
    render() {
      const overlay = document.createElement("div");
      overlay.setAttribute("role", "dialog");
      overlay.setAttribute("aria-modal", "true");
      overlay.setAttribute("aria-labelledby", "modal-title");

      const modal = document.createElement("div");

      // Title
      const titleEl = document.createElement("h2");
      titleEl.id = "modal-title";
      titleEl.textContent = title;
      modal.appendChild(titleEl);

      // Content
      const contentEl = document.createElement("div");
      contentEl.textContent = content;
      modal.appendChild(contentEl);

      // Close button
      const closeBtn = document.createElement("button");
      closeBtn.textContent = "Close";
      closeBtn.setAttribute("aria-label", "Close dialog");
      closeBtn.addEventListener("click", () => {
        this.close();
        onClose();
      });
      modal.appendChild(closeBtn);

      overlay.appendChild(modal);

      return overlay;
    },

    open() {
      // Save current focus
      previousFocus = document.activeElement;

      // Focus first focusable element
      const focusable = this.element.querySelectorAll(
        'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
      );
      focusable[0]?.focus();

      // Trap focus within modal
      this.trapFocus();
    },

    close() {
      // Restore focus
      previousFocus?.focus();
    },

    trapFocus() {
      const focusable = Array.from(
        this.element.querySelectorAll(
          'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
        )
      );

      const firstFocusable = focusable[0];
      const lastFocusable = focusable[focusable.length - 1];

      this.element.addEventListener("keydown", (e) => {
        if (e.key !== "Tab") return;

        if (e.shiftKey) {
          // Shift + Tab
          if (document.activeElement === firstFocusable) {
            e.preventDefault();
            lastFocusable.focus();
          }
        } else {
          // Tab
          if (document.activeElement === lastFocusable) {
            e.preventDefault();
            firstFocusable.focus();
          }
        }
      });
    },
  };
}

// Accessible Form Field
function AccessibleFormField({
  label,
  type = "text",
  id,
  required = false,
  error,
  helpText,
}) {
  return {
    render() {
      const container = document.createElement("div");

      // Label
      const labelEl = document.createElement("label");
      labelEl.htmlFor = id;
      labelEl.textContent = label + (required ? " *" : "");
      container.appendChild(labelEl);

      // Input
      const input = document.createElement("input");
      input.type = type;
      input.id = id;
      input.required = required;

      if (error) {
        input.setAttribute("aria-invalid", "true");
        input.setAttribute("aria-describedby", `${id}-error`);
      } else if (helpText) {
        input.setAttribute("aria-describedby", `${id}-help`);
      }

      container.appendChild(input);

      // Help text
      if (helpText) {
        const help = document.createElement("div");
        help.id = `${id}-help`;
        help.textContent = helpText;
        container.appendChild(help);
      }

      // Error message
      if (error) {
        const errorEl = document.createElement("div");
        errorEl.id = `${id}-error`;
        errorEl.setAttribute("role", "alert");
        errorEl.textContent = error;
        container.appendChild(errorEl);
      }

      return container;
    },
  };
}
```

#### Exercise 2: Build i18n System

Create translation system:

```javascript
class I18n {
  constructor(defaultLocale = "en") {
    this.locale = defaultLocale;
    this.translations = {};
    this.fallbackLocale = defaultLocale;
  }

  setLocale(locale) {
    this.locale = locale;
    this.notifyListeners();
  }

  loadTranslations(locale, translations) {
    this.translations[locale] = translations;
  }

  t(key, params = {}) {
    const translation =
      this.getTranslation(key, this.locale) ||
      this.getTranslation(key, this.fallbackLocale) ||
      key;

    return this.interpolate(translation, params);
  }

  getTranslation(key, locale) {
    const keys = key.split(".");
    let value = this.translations[locale];

    for (const k of keys) {
      if (value && typeof value === "object") {
        value = value[k];
      } else {
        return null;
      }
    }

    return value;
  }

  interpolate(text, params) {
    if (typeof text !== "string") return text;

    return text.replace(/\{\{(\w+)\}\}/g, (match, key) => {
      return params[key] !== undefined ? params[key] : match;
    });
  }

  // Pluralization
  plural(key, count, params = {}) {
    const pluralKey = count === 1 ? `${key}.one` : `${key}.other`;
    return this.t(pluralKey, {...params, count});
  }

  // Date formatting
  formatDate(date, options = {}) {
    return new Intl.DateTimeFormat(this.locale, options).format(date);
  }

  // Number formatting
  formatNumber(number, options = {}) {
    return new Intl.NumberFormat(this.locale, options).format(number);
  }

  // Currency formatting
  formatCurrency(amount, currency) {
    return new Intl.NumberFormat(this.locale, {
      style: "currency",
      currency,
    }).format(amount);
  }

  // Listeners for reactive updates
  listeners = new Set();

  subscribe(callback) {
    this.listeners.add(callback);
    return () => this.listeners.delete(callback);
  }

  notifyListeners() {
    this.listeners.forEach((callback) => callback(this.locale));
  }
}

// Usage:
const i18n = new I18n("en");

i18n.loadTranslations("en", {
  greeting: "Hello, {{name}}!",
  items: {
    one: "{{count}} item",
    other: "{{count}} items",
  },
  cart: {
    total: "Total: {{amount}}",
  },
});

i18n.loadTranslations("es", {
  greeting: "¡Hola, {{name}}!",
  items: {
    one: "{{count}} artículo",
    other: "{{count}} artículos",
  },
  cart: {
    total: "Total: {{amount}}",
  },
});

console.log(i18n.t("greeting", {name: "Alice"}));
// "Hello, Alice!"

i18n.setLocale("es");
console.log(i18n.t("greeting", {name: "Alice"}));
// "¡Hola, Alice!"

console.log(i18n.plural("items", 1)); // "1 item"
console.log(i18n.plural("items", 5)); // "5 items"

console.log(i18n.formatCurrency(1234.56, "USD"));
// en: "$1,234.56"
// es: "1234,56 US$"
```

#### Exercise 3: Build Accessibility Testing Tool

Create a11y auditor:

```javascript
function auditAccessibility(element) {
  const issues = [];

  // Check for missing alt text
  element.querySelectorAll("img").forEach((img) => {
    if (!img.hasAttribute("alt")) {
      issues.push({
        severity: "error",
        element: img,
        message: "Image missing alt attribute",
      });
    }
  });

  // Check for empty links
  element.querySelectorAll("a").forEach((link) => {
    if (!link.textContent.trim() && !link.getAttribute("aria-label")) {
      issues.push({
        severity: "error",
        element: link,
        message: "Link has no accessible text",
      });
    }
  });

  // Check for button accessibility
  element.querySelectorAll('[role="button"]').forEach((btn) => {
    if (!btn.hasAttribute("tabindex")) {
      issues.push({
        severity: "error",
        element: btn,
        message: "Button role without tabindex",
      });
    }
  });

  // Check heading hierarchy
  const headings = Array.from(
    element.querySelectorAll("h1, h2, h3, h4, h5, h6")
  );
  headings.forEach((heading, i) => {
    const level = parseInt(heading.tagName[1]);
    const prevLevel = i > 0 ? parseInt(headings[i - 1].tagName[1]) : 0;

    if (level - prevLevel > 1) {
      issues.push({
        severity: "warning",
        element: heading,
        message: `Heading levels skipped (h${prevLevel} to h${level})`,
      });
    }
  });

  // Check form labels
  element.querySelectorAll("input, select, textarea").forEach((input) => {
    const id = input.id;
    const label = id && element.querySelector(`label[for="${id}"]`);
    const ariaLabel = input.getAttribute("aria-label");
    const ariaLabelledBy = input.getAttribute("aria-labelledby");

    if (!label && !ariaLabel && !ariaLabelledBy) {
      issues.push({
        severity: "error",
        element: input,
        message: "Form control has no label",
      });
    }
  });

  // Check color contrast
  // (This is complex - would need computed styles)

  // Check for keyboard traps
  const focusable = element.querySelectorAll(
    'a[href], button, input, select, textarea, [tabindex]:not([tabindex="-1"])'
  );

  if (focusable.length === 0) {
    issues.push({
      severity: "warning",
      element,
      message: "No focusable elements found",
    });
  }

  return {
    issues,
    score: calculateA11yScore(issues),
  };
}

function calculateA11yScore(issues) {
  const weights = {error: 10, warning: 5};
  const deductions = issues.reduce((total, issue) => {
    return total + weights[issue.severity];
  }, 0);

  return Math.max(0, 100 - deductions);
}

// Usage:
const audit = auditAccessibility(document.body);
console.log(`Accessibility Score: ${audit.score}/100`);
console.log("Issues:", audit.issues);
```

#### Exercise 4: Compare Framework a11y/i18n

Research framework support:

| Feature               | React                  | Vue 3                             | Svelte           | Solid.js                 |
| --------------------- | ---------------------- | --------------------------------- | ---------------- | ------------------------ |
| **ARIA Support**      | Yes                    | Yes                               | Yes              | Yes                      |
| **Built-in i18n**     | No                     | No                                | No               | No                       |
| **Popular i18n Libs** | react-i18next          | vue-i18n                          | svelte-i18n      | @solid-primitives/i18n   |
| **a11y Linting**      | eslint-plugin-jsx-a11y | eslint-plugin-vuejs-accessibility | -                | -                        |
| **Testing Tools**     | @testing-library       | @testing-library                  | @testing-library | @solidjs/testing-library |

**Best practices across frameworks:**

- Use semantic HTML
- Add ARIA when needed
- Manage focus properly
- Support keyboard navigation
- Use i18n library for translations
- Test with screen readers
- Run accessibility audits

---

### Reflection Questions

After building:

1. **Accessibility:**

   - Why is a11y important?
   - What are common mistakes?
   - How do you test accessibility?

2. **Internationalization:**

   - What are i18n challenges?
   - How do you handle RTL languages?
   - What about date/number formats?

3. **Framework Support:**

   - Do frameworks make a11y easier?
   - What's still the developer's responsibility?
   - What tools help?

4. **Best Practices:**
   - When do you add a11y?
   - How do you prioritize?
   - What's the minimum required?

---

## Section 15: Middleware & Interceptors

### The Problem

You need to run code at specific points:

- Before every API request (add auth token)
- After every response (handle errors globally)
- Before navigation (check if user is logged in)
- After state changes (log analytics)

**Middleware/interceptors let you inject behavior without modifying every function.**

---

### Exploration Questions

**Scenario 1: Request Interceptors**

```javascript
// Without middleware: Repeat everywhere
fetch("/api/users", {
  headers: {
    Authorization: `Bearer ${token}`,
    "Content-Type": "application/json",
  },
});

// With middleware: Once
api.use((config) => {
  config.headers["Authorization"] = `Bearer ${token}`;
  return config;
});

api.get("/users"); // Auth header added automatically
```

**Explore:**

- What is middleware?
- How do you chain middleware?
- How do you pass data between middleware?
- Build middleware system

**Scenario 2: Navigation Guards**

```javascript
router.beforeEach((to, from, next) => {
  if (to.requires Auth && !isLoggedIn()) {
    next('/login');
  } else {
    next();
  }
});
```

**Explore:**

- What are navigation guards?
- When do they run?
- How do you implement them?
- Build route middleware

---

### Build It: Middleware Systems

#### Exercise 1: Build HTTP Interceptors

```javascript
class HttpClient {
  constructor() {
    this.requestInterceptors = [];
    this.responseInterceptors = [];
  }

  useRequest(interceptor) {
    this.requestInterceptors.push(interceptor);
  }

  useResponse(interceptor) {
    this.responseInterceptors.push(interceptor);
  }

  async request(config) {
    // Run request interceptors
    let finalConfig = config;
    for (const interceptor of this.requestInterceptors) {
      finalConfig = await interceptor(finalConfig);
    }

    // Make request
    let response = await fetch(finalConfig.url, finalConfig);

    // Run response interceptors
    for (const interceptor of this.responseInterceptors) {
      response = await interceptor(response);
    }

    return response;
  }
}

// Usage:
const api = new HttpClient();

api.useRequest((config) => {
  config.headers = {
    ...config.headers,
    Authorization: `Bearer ${getToken()}`,
  };
  return config;
});

api.useResponse(async (response) => {
  if (response.status === 401) {
    // Redirect to login
    window.location.href = "/login";
  }
  return response;
});
```

#### Exercise 2: Build State Change Middleware

```javascript
function createStore(reducer, initialState, middleware = []) {
  let state = initialState;
  const listeners = [];

  function dispatch(action) {
    // Build middleware chain
    const chain = middleware.map((mw) => mw({getState, dispatch}));
    const enhancedDispatch = chain.reduceRight(
      (next, mw) => mw(next),
      (action) => {
        state = reducer(state, action);
        listeners.forEach((fn) => fn());
        return action;
      }
    );

    return enhancedDispatch(action);
  }

  function getState() {
    return state;
  }

  function subscribe(listener) {
    listeners.push(listener);
    return () => {
      const index = listeners.indexOf(listener);
      listeners.splice(index, 1);
    };
  }

  return {dispatch, getState, subscribe};
}

// Logger middleware
const logger = (store) => (next) => (action) => {
  console.log("Dispatching:", action);
  const result = next(action);
  console.log("New state:", store.getState());
  return result;
};

// Thunk middleware
const thunk = (store) => (next) => (action) => {
  if (typeof action === "function") {
    return action(store.dispatch, store.getState);
  }
  return next(action);
};
```

);
const match = path.match(regex);

      if (match) {
        return { ...route, params: match.slice(1) };
      }
    }

    return routes.find(r => r.path === '*');

}

function navigate(path) {
const route = matchRoute(path);

    if (route) {
      history.pushState(null, '', path);
      currentRoute = route;
      listeners.forEach(fn => fn(route));
    }

}

function onRoute(callback) {
listeners.push(callback);
}

// Handle browser back/forward
window.addEventListener('popstate', () => {
navigate(window.location.pathname);
});

// Initial route
navigate(window.location.pathname);

return { navigate, onRoute, get currentRoute() { return currentRoute; } };
}

````

#### Exercise 6: Build State Store

```javascript
// store.js
import { createSignal } from './signals.js';

export function createStore(initialState) {
  const [getState, setState] = createSignal(initialState);
  const listeners = new Set();

  function update(updater) {
    const current = getState();
    const next = typeof updater === 'function' ? updater(current) : updater;
    setState({ ...current, ...next });
    listeners.forEach(fn => fn(getState()));
  }

  function subscribe(listener) {
    listeners.add(listener);
    return () => listeners.delete(listener);
  }

  return { getState, update, subscribe };
}
````

#### Exercise 7: Put It All Together

Create a complete example app:

```javascript
// app.js
import {createSignal, createEffect} from "./signals.js";
import {h, render} from "./vdom.js";
import {createRouter} from "./router.js";
import {createStore} from "./store.js";

// Global store
const store = createStore({
  todos: [],
  filter: "all",
});

// Router
const router = createRouter([
  {path: "/", component: Home},
  {path: "/about", component: About},
  {path: "*", component: NotFound},
]);

// Components
function Home() {
  const [text, setText] = createSignal("");
  const state = store.getState();

  const addTodo = () => {
    store.update((s) => ({
      todos: [...s.todos, {id: Date.now(), text: text(), done: false}],
    }));
    setText("");
  };

  return h(
    "div",
    {},
    h("h1", {}, "My Framework Todo App"),
    h("input", {
      value: text(),
      onInput: (e) => setText(e.target.value),
    }),
    h("button", {onClick: addTodo}, "Add"),
    h("ul", {}, ...state.todos.map((todo) => h("li", {}, todo.text)))
  );
}

function About() {
  return h(
    "div",
    {},
    h("h1", {}, "About"),
    h("p", {}, "Built with my custom framework!")
  );
}

function NotFound() {
  return h("div", {}, h("h1", {}, "404 Not Found"));
}

// App
function App() {
  const route = router.currentRoute;

  return h(
    "div",
    {},
    h(
      "nav",
      {},
      h(
        "a",
        {
          href: "/",
          onClick: (e) => {
            e.preventDefault();
            router.navigate("/");
          },
        },
        "Home"
      ),
      " | ",
      h(
        "a",
        {
          href: "/about",
          onClick: (e) => {
            e.preventDefault();
            router.navigate("/about");
          },
        },
        "About"
      )
    ),
    h("main", {}, route ? route.component() : null)
  );
}

// Mount
const root = document.getElementById("app");
createEffect(() => {
  root.innerHTML = "";
  root.appendChild(render(App()));
});
```

#### Exercise 8: Package Your Framework

```javascript
// index.js - Main export
export { createSignal, createEffect, createMemo } from './signals.js';
export { createComponent } from './component.js';
export { h, render } from './vdom.js';
export { createRouter } from './router.js';
export { createStore } from './store.js';

// package.json
{
  "name": "my-framework",
  "version": "1.0.0",
  "description": "A minimal reactive framework",
  "main": "index.js",
  "type": "module",
  "keywords": ["framework", "reactive", "signals"],
  "author": "Your Name",
  "license": "MIT"
}
```

---

### Reflection Questions

After building:

1. **Framework Design:**

   - What tradeoffs did you make?
   - What was hardest to implement?
   - What would you change?

2. **Appreciation:**

   - How complex are real frameworks?
   - What optimizations are you missing?
   - What features would you add?

3. **Learning:**

   - What did you learn?
   - What surprised you?
   - What will you do differently?

4. **Reality:**
   - Would you use your framework?
   - When is building your own worth it?
   - When should you use existing frameworks?

---

## Section 19: Building & Publishing Packages

### The Problem

You built useful utilities. How do you share them?

**Package development includes:**

- Project structure
- Build configuration
- TypeScript types
- Documentation
- Testing
- Publishing to npm
- Versioning
- Maintenance

---

### Build It: Publishable Package

#### Exercise 1: Set Up Package Structure

```
my-package/
├── src/
│   ├── index.js
│   └── utils.js
├── dist/
│   ├── index.js (ESM)
│   ├── index.cjs (CommonJS)
│   └── index.d.ts (Types)
├── tests/
│   └── index.test.js
├── package.json
├── README.md
├── LICENSE
└── .npmignore
```

#### Exercise 2: Configure Build

```javascript
// rollup.config.js
export default {
  input: 'src/index.js',
  output: [
    {
      file: 'dist/index.js',
      format: 'esm'
    },
    {
      file: 'dist/index.cjs',
      format: 'cjs'
    }
  ]
};

// package.json
{
  "name": "@your-name/my-package",
  "version": "1.0.0",
  "description": "Useful utilities",
  "main": "./dist/index.cjs",
  "module": "./dist/index.js",
  "types": "./dist/index.d.ts",
  "exports": {
    ".": {
      "import": "./dist/index.js",
      "require": "./dist/index.cjs",
      "types": "./dist/index.d.ts"
    }
  },
  "scripts": {
    "build": "rollup -c",
    "test": "vitest",
    "prepublishOnly": "npm run build && npm test"
  },
  "keywords": ["utility", "helper"],
  "author": "Your Name",
  "license": "MIT",
  "repository": {
    "type": "git",
    "url": "https://github.com/your-name/my-package"
  }
}
```

#### Exercise 3: Write Documentation

````markdown
# My Package

Useful utilities for JavaScript developers.

## Installation

```bash
npm install @your-name/my-package
```
````

## Usage

```javascript
import {formatDate, debounce} from "@your-name/my-package";

// Format dates
const formatted = formatDate(new Date(), "YYYY-MM-DD");

// Debounce functions
const debouncedFn = debounce(() => {
  console.log("Called after 300ms");
}, 300);
```

## API

### `formatDate(date, format)`

Formats a date according to the specified format.

**Parameters:**

- `date` (Date): The date to format
- `format` (string): Format string

**Returns:** string

**Example:**

```javascript
formatDate(new Date(), "YYYY-MM-DD"); // '2024-01-15'
```

### `debounce(fn, delay)`

Creates a debounced function.

**Parameters:**

- `fn` (Function): Function to debounce
- `delay` (number): Delay in milliseconds

**Returns:** Function

**Example:**

```javascript
const debouncedSearch = debounce(search, 300);
```

## License

MIT

````

#### Exercise 4: Publish to npm

```bash
# Login to npm
npm login

# Publish
npm publish --access public

# Update version
npm version patch # 1.0.0 -> 1.0.1
npm version minor # 1.0.0 -> 1.1.0
npm version major # 1.0.0 -> 2.0.0

npm publish
````

---

## Next Steps: Choosing and Mastering Your Framework

**🎉 Congratulations! You've completed the Framework Foundations journey.**

### What You've Mastered

You've built from scratch:

- ✅ Reactivity systems (signals, proxies, observables)
- ✅ Component lifecycle management
- ✅ Client-side routing
- ✅ State management (Redux-like)
- ✅ Virtual DOM with reconciliation
- ✅ Form handling with validation
- ✅ Data fetching with caching
- ✅ Server-side rendering & hydration
- ✅ Build tools & bundlers
- ✅ Security (XSS prevention)
- ✅ Testing frameworks
- ✅ Accessibility & i18n
- ✅ Error handling & monitoring
- ✅ Your own complete framework!

### You Now Understand

- **How frameworks work internally**
- **Why frameworks make different tradeoffs**
- **What patterns are universal**
- **What patterns are framework-specific**
- **How to evaluate frameworks**
- **How to choose the right framework**

### Choosing Your Framework

Now that you understand the patterns, choose based on:

**React** - Choose if:

- ✅ You want the largest ecosystem
- ✅ You want the most job opportunities
- ✅ Your team already knows React
- ✅ You need many third-party libraries
- ✅ You value community size over everything

**Vue** - Choose if:

- ✅ You want balance (performance + DX + ecosystem)
- ✅ You value great documentation
- ✅ You want a gentler learning curve
- ✅ You want official libraries (router, state)
- ✅ You prefer template syntax over JSX

**Svelte** - Choose if:

- ✅ Performance is critical
- ✅ You want the smallest bundle size
- ✅ You want less boilerplate
- ✅ You're building mobile-first apps
- ✅ You value simplicity

**Solid** - Choose if:

- ✅ You want maximum performance
- ✅ You understand fine-grained reactivity
- ✅ You come from React
- ✅ You're building data-heavy apps
- ✅ You want to learn cutting-edge patterns

### Your Learning Path

**Week 1-2: Official Tutorial**

- Complete your chosen framework's tutorial
- Notice the patterns you built in this workbook
- See how the framework implements them

**Week 3-4: Build Real Project**

- Build a complete app (not a todo app!)
- Use the framework's ecosystem
- Follow best practices
- Deploy to production

**Week 5-6: Deep Dive**

- Read the framework's source code
- Understand how it implements patterns you built
- Contribute to discussions
- Help others learn

**Week 7-8: Master It**

- Build advanced features
- Optimize performance
- Write tests
- Share your knowledge

### Beyond Frameworks

You're now equipped to:

- **Evaluate any new framework** that comes out
- **Build framework plugins and libraries**
- **Contribute to framework development**
- **Make informed technical decisions**
- **Mentor other developers**
- **Stay current as frameworks evolve**

### Keep Learning

- 📚 Read framework source code regularly
- 👥 Join framework communities (Discord, Reddit, Twitter)
- 🛠️ Build and share your projects
- ✍️ Write about what you learn
- 🤝 Help others on their journey
- 🚀 Push the boundaries of what's possible

### Final Thoughts

**You've learned framework patterns, not just a specific framework.**

This means:

- New frameworks will make sense immediately
- You can switch frameworks easily
- You understand the "why" not just the "how"
- You can make informed technical decisions
- You're framework-independent

**The patterns you learned are timeless. Specific frameworks come and go, but the underlying patterns remain.**

---

## 🎓 You're Now a Framework Master

**You understand:**

- Why frameworks exist
- How they work internally
- What tradeoffs they make
- How to choose between them
- How to build your own

**Go build amazing things! 🚀**

Whether you choose React, Vue, Svelte, Solid, or something else entirely, you now have the deep understanding to use it effectively, debug it confidently, and master it quickly.

**The framework doesn't make you a great developer. Understanding the patterns does.**

Happy coding! 🎉
