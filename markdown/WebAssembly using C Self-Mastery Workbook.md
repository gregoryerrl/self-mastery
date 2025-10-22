# WebAssembly using C Self-Mastery Workbook

---

## Table of Contents

- [💻 Prerequisites](#-prerequisites)
- [How to Use This Workbook](#how-to-use-this-workbook)
- [🌱 Philosophy Behind This Workbook](#-philosophy-behind-this-workbook)

### 🟢 PART 1: WEBASSEMBLY FUNDAMENTALS

- [Section 1: What is WebAssembly? Understanding the Platform](#section-1-what-is-webassembly-understanding-the-platform)
- [Section 2: The WebAssembly Stack Machine](#section-2-the-webassembly-stack-machine)
- [Section 3: Text Format (WAT) vs Binary Format](#section-3-text-format-wat-vs-binary-format)

### 🟡 PART 2: COMPILING C TO WEBASSEMBLY

- [Section 4: Setting Up Emscripten](#section-4-setting-up-emscripten)
- [Section 5: Your First C to WASM Compilation](#section-5-your-first-c-to-wasm-compilation)
- [Section 6: Understanding the Compilation Output](#section-6-understanding-the-compilation-output)
- [Section 7: WASM Memory Model](#section-7-wasm-memory-model)

### 🔵 PART 3: JAVASCRIPT-WASM INTEROP

- [Section 8: Loading and Instantiating WASM Modules](#section-8-loading-and-instantiating-wasm-modules)
- [Section 9: Calling WASM from JavaScript](#section-9-calling-wasm-from-javascript)
- [Section 10: Calling JavaScript from WASM](#section-10-calling-javascript-from-wasm)
- [Section 11: Passing Complex Data Between JS and WASM](#section-11-passing-complex-data-between-js-and-wasm)

### 🟣 PART 4: MEMORY MANAGEMENT IN WASM

- [Section 12: Linear Memory and Growth](#section-12-linear-memory-and-growth)
- [Section 13: Strings in WASM](#section-13-strings-in-wasm)
- [Section 14: Arrays and Pointers Across the Boundary](#section-14-arrays-and-pointers-across-the-boundary)
- [Section 15: Debugging Memory Issues](#section-15-debugging-memory-issues)

### 🟠 PART 5: BUILDING REAL APPLICATIONS

- [Section 16: Image Processing with WASM](#section-16-image-processing-with-wasm)
- [Section 17: Mathematical Libraries](#section-17-mathematical-libraries)
- [Section 18: Cryptography Functions](#section-18-cryptography-functions)
- [Section 19: Game Logic and Physics](#section-19-game-logic-and-physics)

### 🔴 PART 6: PERFORMANCE OPTIMIZATION

- [Section 20: Measuring WASM Performance](#section-20-measuring-wasm-performance)
- [Section 21: When WASM is Faster (and When It's Not)](#section-21-when-wasm-is-faster-and-when-its-not)
- [Section 22: Optimizing C Code for WASM](#section-22-optimizing-c-code-for-wasm)
- [Section 23: Understanding the Compilation Pipeline](#section-23-understanding-the-compilation-pipeline)

### ⚫ PART 7: ADVANCED FEATURES

- [Section 24: Working with Multiple WASM Modules](#section-24-working-with-multiple-wasm-modules)
- [Section 25: WebAssembly Tables and Function Pointers](#section-25-webassembly-tables-and-function-pointers)
- [Section 26: SIMD in WebAssembly](#section-26-simd-in-webassembly)
- [Section 27: Threading with WebAssembly](#section-27-threading-with-webassembly)

### ⚪ PART 8: PRODUCTION DEPLOYMENT

- [Section 28: Building for Production](#section-28-building-for-production)
- [Section 29: Debugging WASM Applications](#section-29-debugging-wasm-applications)
- [Section 30: Error Handling Patterns](#section-30-error-handling-patterns)
- [Section 31: Browser Compatibility and Polyfills](#section-31-browser-compatibility-and-polyfills)

---

## 💻 Prerequisites

Before starting this workbook, you **must have completed**:

### ✅ Required Workbook

- **"C Programming Self-Mastery Workbook"** ← ESSENTIAL!

You should deeply understand:

- C programming fundamentals
- Pointers and memory management
- Manual memory allocation (malloc/free)
- Structs and data structures
- File I/O
- Compilation process
- Debugging with GDB and Valgrind

### ✅ Required Web Knowledge

- **Basic HTML/JavaScript** - You need to know how to:
  - Create HTML files
  - Write basic JavaScript
  - Use browser DevTools
  - Understand async/await
  - Work with Promises

### ✅ What You Need Installed

- **Emscripten SDK** - For compiling C to WebAssembly
- **Node.js** - For running WASM outside the browser
- **Modern Web Browser** - Chrome, Firefox, or Edge
- **Text Editor/IDE** - VSCode recommended
- **Basic HTTP Server** - `python -m http.server` or `npx serve`

### ✅ Helpful Knowledge (Not Required)

- Understanding of assembly language concepts
- Experience with build systems (Make, CMake)
- Familiarity with browser APIs

---

## How to Use This Workbook

This document is **not a tutorial**. It will not hand you the answers.

Instead, it gives you the **right questions to ask yourself** — questions every WebAssembly developer must be able to answer to bridge C programming to the web at a professional level.

### Here's how to use it effectively:

#### 1. Ask Yourself First

- Before looking things up, try to explain the answer in your own words
- If you can't, that's fine — it means you found a gap in your knowledge
- Your C knowledge will help — think about how concepts map from C to WASM

#### 2. Leverage All Resources

- Use Google, Stack Overflow, and ChatGPT to research
- Read the Emscripten documentation
- Experiment with code — compile and test in the browser
- Use browser DevTools to debug

#### 3. Learn by Doing

- Each section has "Build It" exercises
- These exercises force you to discover answers naturally
- Don't skip them — hands-on work is essential
- Test in both browser and Node.js when possible

#### 4. Reflect and Explain

- After finding an answer, teach it back:
  - Explain to a friend or colleague
  - Write notes comparing C and WASM
  - Draw memory diagrams
- If you can explain clearly, you've truly learned it

#### 5. Iterate and Improve

- Revisit sections as you grow
- Your understanding will deepen each time
- Build increasingly complex projects

---

## 🌱 Philosophy Behind This Workbook

### This is a "find the answer within yourself" approach to WebAssembly mastery.

Traditional WASM courses say: "Here's how to compile C to WASM. Run this command."

This workbook says: "Your C function returns a pointer. How does JavaScript access it? What happens when you free it? How do you debug when it goes wrong?"

### Core Beliefs

- **Understanding > Following Steps** - You'll learn WHY WASM works this way, not just HOW to use tools
- **Discovery > Tutorial** - Questions guide you to discover through experimentation
- **Building > Reading** - You'll port C programs to WASM and solve real problems
- **C Knowledge is Your Superpower** - Everything you learned about memory, pointers, and performance applies here
- **Tool-agnostic** - Use whatever helps you learn: docs, ChatGPT, Stack Overflow

### Questions Grow With You

This workbook starts with fundamentals and progressively deepens:

- **Foundational questions** - What is WASM? How is it different from JavaScript?
- **How-to questions** - How do I compile this C code?
- **Deep questions** - Why does WASM use a linear memory model?
- **Scenario questions** - Your WASM module crashes. How do you debug it?

By the time you've asked and answered everything here — and built all the exercises — you won't just "know how to use WASM." **You'll understand how to bring C's power to the web, optimize for performance, debug complex issues, and build production applications that leverage both C and JavaScript.**

### What This Workbook Prepares You For

After completing this workbook, you'll be ready to:

- **Port existing C libraries to the web** - Make C code run in browsers
- **Build high-performance web applications** - Games, image processors, physics engines
- **Optimize web performance** - Know when to use WASM vs JavaScript
- **Debug cross-language issues** - Understand the boundary between C and JS
- **Architect hybrid applications** - Design systems using both WASM and JavaScript

---

# 🟢 PART 1: WEBASSEMBLY FUNDAMENTALS

---

## Section 1: What is WebAssembly? Understanding the Platform

### The Problem

You built a C program that processes images 10x faster than JavaScript. But it only runs on desktop. Users want it in their browser. You could rewrite it in JavaScript, but:

- You'd lose all that C code
- JavaScript is slow for heavy computation
- You'd have to maintain two codebases

**WebAssembly lets you compile C to run in the browser at near-native speed.** It's a new type of code that browsers can run alongside JavaScript.

### Understanding WebAssembly

- What is WebAssembly?
- Why was it created? What problem does it solve?
- JavaScript is already fast. Why do we need WASM?
- How is WASM different from JavaScript?
- What makes WASM "portable"?

### The Compilation Target

- What does "compilation target" mean?
- C compiles to machine code. What does it compile to for WASM?
- Is WASM a programming language?
- Can you write WASM directly, or do you always compile to it?
- What languages can compile to WASM?

### Where WASM Runs

- WASM runs in browsers. What else can run it?
- Does WASM run on the CPU directly?
- What's the relationship between WASM and the browser?
- Can WASM access the DOM?
- Can WASM make HTTP requests?

### WASM vs JavaScript

- You have a heavy computation. When should you use WASM vs JavaScript?
- What can JavaScript do that WASM can't?
- What can WASM do that JavaScript can't?
- Can they work together?
- Which is faster: WASM or JavaScript? Always?

### The WebAssembly Ecosystem

- What is Emscripten?
- What is WASI?
- What's the difference between browser WASM and server-side WASM?
- What tools exist for working with WASM?
- What's the future of WebAssembly?

### Build It: Understanding Through Comparison

Compare JavaScript and WASM performance:

**Requirements:**

**Part 1: JavaScript Version**

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
  <head>
    <title>JS vs WASM Comparison</title>
  </head>
  <body>
    <h1>Fibonacci Calculator</h1>
    <input type="number" id="input" value="40" />
    <button id="jsBtn">Calculate (JavaScript)</button>
    <button id="wasmBtn">Calculate (WASM)</button>
    <div id="result"></div>

    <script>
      // JavaScript implementation
      function fibonacciJS(n) {
        if (n <= 1) return n;
        return fibonacciJS(n - 1) + fibonacciJS(n - 2);
      }

      document.getElementById("jsBtn").onclick = function () {
        const n = parseInt(document.getElementById("input").value);
        const start = performance.now();
        const result = fibonacciJS(n);
        const end = performance.now();

        document.getElementById(
          "result"
        ).innerHTML = `Result: ${result}<br>Time: ${(end - start).toFixed(
          2
        )}ms`;
      };

      // WASM will be added later
      document.getElementById("wasmBtn").onclick = function () {
        alert("WASM not loaded yet - we will add this!");
      };
    </script>
  </body>
</html>
```

**Part 2: Research Tasks**

- Run the JavaScript version
- Measure performance with different input values
- Try to optimize the JavaScript (hint: memoization)
- Think about what makes this slow
- Consider: would C be faster? Why?

**Experiments:**

- What happens with n=30? n=40? n=45?
- Does browser matter? Test in Chrome vs Firefox
- Open DevTools → Performance tab → Profile the execution
- Where does time get spent?
- Can you make the JavaScript faster?

### Reflection Questions

1. **Understanding WASM:**

   - Why does the web need WebAssembly?
   - What problems does it solve?
   - What are its limitations?

2. **C Knowledge Connection:**

   - How does your C knowledge help with WASM?
   - What C concepts are relevant?
   - What's different in the browser environment?

3. **Real-World Applications:**
   - What types of applications benefit from WASM?
   - When should you NOT use WASM?
   - What are good first projects?

---

## Section 2: The WebAssembly Stack Machine

### The Problem

JavaScript uses variables and scopes. C uses registers and memory. **WebAssembly uses a stack machine.** Understanding this is crucial for reading WASM code and understanding how your C code translates.

### Understanding Stack Machines

- What is a stack machine?
- How is it different from a register machine?
- You write `int x = 5; int y = x + 3;` in C. How does this work on a stack machine?
- What gets pushed and popped on the stack?
- Why did WebAssembly choose a stack-based design?

### Stack Operations

- What's the difference between pushing and popping?
- You want to add two numbers. How do you do it on a stack?
- What happens to stack values after an operation?
- How does the stack grow and shrink?
- What's the stack limit?

### Instructions and Opcodes

- What's an instruction in WASM?
- What's an opcode?
- How many instructions does WASM have?
- How do instructions consume and produce stack values?
- What types can be on the stack?

### Control Flow on a Stack

- How do if statements work on a stack machine?
- How do loops work?
- How do function calls work?
- What happens to the stack when you return?
- How are local variables represented?

### Build It: Stack Machine Simulator

Build a simple stack machine to understand WASM:

**Requirements:**

```javascript
class StackMachine {
  constructor() {
    this.stack = [];
    this.locals = [];
  }

  // Stack operations
  push(value) {
    this.stack.push(value);
  }

  pop() {
    if (this.stack.length === 0) {
      throw new Error("Stack underflow");
    }
    return this.stack.pop();
  }

  // Arithmetic operations
  add() {
    const b = this.pop();
    const a = this.pop();
    this.push(a + b);
  }

  subtract() {
    const b = this.pop();
    const a = this.pop();
    this.push(a - b);
  }

  multiply() {
    const b = this.pop();
    const a = this.pop();
    this.push(a * b);
  }

  divide() {
    const b = this.pop();
    const a = this.pop();
    if (b === 0) throw new Error("Division by zero");
    this.push(Math.floor(a / b));
  }

  // Local variables
  setLocal(index, value) {
    this.locals[index] = value;
  }

  getLocal(index) {
    return this.locals[index];
  }

  // Execute a program
  execute(program) {
    for (const instruction of program) {
      const [op, ...args] = instruction;

      switch (op) {
        case "push":
          this.push(args[0]);
          break;
        case "add":
          this.add();
          break;
        case "sub":
          this.subtract();
          break;
        case "mul":
          this.multiply();
          break;
        case "div":
          this.divide();
          break;
        case "set_local":
          this.setLocal(args[0], this.pop());
          break;
        case "get_local":
          this.push(this.getLocal(args[0]));
          break;
        default:
          throw new Error(`Unknown instruction: ${op}`);
      }
    }

    return this.pop();
  }

  printStack() {
    console.log("Stack:", this.stack);
  }
}

// Test: (5 + 3) * 2
const machine = new StackMachine();
const result = machine.execute([
  ["push", 5], // Stack: [5]
  ["push", 3], // Stack: [5, 3]
  ["add"], // Stack: [8]
  ["push", 2], // Stack: [8, 2]
  ["mul"], // Stack: [16]
]);

console.log("Result:", result); // 16

// Test with locals: x = 5; y = 3; result = x + y
const machine2 = new StackMachine();
const result2 = machine2.execute([
  ["push", 5],
  ["set_local", 0], // x = 5
  ["push", 3],
  ["set_local", 1], // y = 3
  ["get_local", 0], // push x
  ["get_local", 1], // push y
  ["add"], // x + y
]);

console.log("Result:", result2); // 8
```

**Experiments:**

- Implement comparison operations (equal, less than, greater than)
- Add if/else control flow
- Implement loops
- Add function calls with a call stack
- Try to implement factorial recursively
- Measure stack depth during execution

### Reflection Questions

1. **Stack Machine Model:**

   - Why is this model good for WASM?
   - How does it relate to C's execution model?
   - What are the advantages?

2. **Understanding Compilation:**

   - How would `x = a + b * c` compile to stack instructions?
   - How would a function call compile?
   - What about control flow?

3. **Performance:**
   - Is a stack machine fast?
   - How does it compare to registers?
   - What optimizations are possible?

---

## Section 3: Text Format (WAT) vs Binary Format

### The Problem

WebAssembly exists in two forms:

- **Binary format (.wasm)** - What browsers execute
- **Text format (.wat)** - Human-readable representation

You need to understand both to read, write, and debug WASM.

### Understanding WAT

- What is WAT (WebAssembly Text Format)?
- Why have a text format if WASM is binary?
- Can you write WAT by hand?
- How do you convert WAT to WASM?
- How do you convert WASM back to WAT?

### Basic WAT Syntax

- What's an S-expression?
- What do all the parentheses mean?
- How do you define a function in WAT?
- How do you export a function?
- What's the module structure?

### Types in WAT

- What types does WASM support?
- What's `i32`, `i64`, `f32`, `f64`?
- Are there strings in WASM?
- Are there arrays or structs?
- How do you represent complex data?

### Binary Format

- What's in a `.wasm` file?
- How is it structured?
- What are sections?
- How is it different from an executable?
- Can you modify a `.wasm` file?

### Build It: Your First WAT Program

Write WebAssembly by hand:

**Requirements:**

**Part 1: Simple Addition (add.wat)**

```wat
(module
  (func $add (param $a i32) (param $b i32) (result i32)
    local.get $a
    local.get $b
    i32.add
  )
  (export "add" (func $add))
)
```

**Part 2: Compile and Use**

```bash
# Install wat2wasm (part of WABT - WebAssembly Binary Toolkit)
# On macOS: brew install wabt
# On Linux: apt-get install wabt

# Compile WAT to WASM
wat2wasm add.wat -o add.wasm

# Disassemble back to WAT to see the result
wasm2wat add.wasm
```

**Part 3: Load in JavaScript (test.html)**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>WAT Test</title>
  </head>
  <body>
    <h1>WAT Function Test</h1>
    <div id="result"></div>

    <script>
      async function loadWasm() {
        const response = await fetch("add.wasm");
        const buffer = await response.arrayBuffer();
        const module = await WebAssembly.instantiate(buffer);

        const add = module.instance.exports.add;
        const result = add(5, 3);

        document.getElementById("result").textContent = `5 + 3 = ${result}`;
      }

      loadWasm();
    </script>
  </body>
</html>
```

**Part 4: More Complex Functions**

Write these functions in WAT:

```wat
(module
  ;; Multiply function
  (func $multiply (param $a i32) (param $b i32) (result i32)
    local.get $a
    local.get $b
    i32.mul
  )

  ;; Factorial function (recursive)
  (func $factorial (param $n i32) (result i32)
    (if (result i32)
      (i32.le_s (local.get $n) (i32.const 1))
      (then (i32.const 1))
      (else
        (i32.mul
          (local.get $n)
          (call $factorial
            (i32.sub (local.get $n) (i32.const 1))
          )
        )
      )
    )
  )

  ;; Max of two numbers
  (func $max (param $a i32) (param $b i32) (result i32)
    (if (result i32)
      (i32.gt_s (local.get $a) (local.get $b))
      (then (local.get $a))
      (else (local.get $b))
    )
  )

  (export "multiply" (func $multiply))
  (export "factorial" (func $factorial))
  (export "max" (func $max))
)
```

**Experiments:**

- Write a function that returns the absolute value
- Write a function that calculates power (x^n)
- Write a function with local variables
- Try writing a loop instead of recursion
- Use `wasm2wat` on real WASM files from websites
- Compare hand-written WAT to Emscripten output

### Reflection Questions

1. **Text Format:**

   - When would you write WAT by hand?
   - How does it compare to C?
   - Is it readable?

2. **Binary Format:**

   - Why is WASM binary?
   - How does it compare to native executables?
   - What are the benefits?

3. **Tooling:**
   - What tools exist for working with WASM?
   - How do you debug WAT?
   - When do you need to read WASM output?

---

# 🟡 PART 2: COMPILING C TO WEBASSEMBLY

---

## Section 4: Setting Up Emscripten

### The Problem

You have C code. You want it to run in a browser. **Emscripten is the compiler toolchain that makes this possible.** It's like GCC, but for the web.

### Understanding Emscripten

- What is Emscripten?
- How is it different from GCC?
- What does Emscripten produce?
- Can you use other compilers for WASM?
- What's LLVM's role in this?

### Installation and Setup

- How do you install Emscripten?
- What's the `emsdk`?
- What does `emcc` do?
- What environment variables need to be set?
- How do you verify installation?

### Emscripten vs Native Compilation

- You compile with `gcc file.c -o program`. What's the Emscripten equivalent?
- What files does Emscripten produce?
- What's the `.js` file it generates?
- What's the `.wasm` file?
- Do you need both files?

### Build It: Setting Up Your Environment

Get Emscripten working:

**Requirements:**

**Part 1: Install Emscripten**

```bash
# Clone the emsdk repository
git clone https://github.com/emscripten-core/emsdk.git
cd emsdk

# Download and install the latest SDK tools
./emsdk install latest

# Activate the latest SDK
./emsdk activate latest

# Set up environment variables
source ./emsdk_env.sh

# Verify installation
emcc --version
```

**Part 2: Hello World in C**

```c
// hello.c
#include <stdio.h>

int main() {
    printf("Hello from WebAssembly!\n");
    return 0;
}
```

**Part 3: Compile and Run**

```bash
# Compile to WASM
emcc hello.c -o hello.html

# This creates three files:
# - hello.html (test page)
# - hello.js (JavaScript glue code)
# - hello.wasm (WebAssembly binary)

# Start a local server
python3 -m http.server 8000

# Open browser to http://localhost:8000/hello.html
```

**Part 4: Compile Without HTML**

```bash
# Just get JS and WASM
emcc hello.c -o hello.js

# Use in Node.js
node hello.js
```

**Experiments:**

- Try different optimization levels: `-O0`, `-O1`, `-O2`, `-O3`
- Compare file sizes at different optimization levels
- Add `-s WASM=1` flag (it's default now but good to know)
- Try `--no-entry` for library compilation
- Use `-s EXPORTED_FUNCTIONS='["_main"]'` to control exports
- Generate only WASM: `emcc hello.c -o hello.wasm`

### Reflection Questions

1. **Toolchain:**

   - How is Emscripten like and unlike GCC?
   - What does the compilation process look like?
   - What role does LLVM play?

2. **Output Files:**

   - Why does Emscripten produce JavaScript?
   - What's in the glue code?
   - When can you skip the JS file?

3. **Development Workflow:**
   - How do you set up a project?
   - What's the edit-compile-test cycle?
   - How does this compare to native C development?

---

## Section 5: Your First C to WASM Compilation

### The Problem

You have a C function that does actual work. Not just `printf`, but computation. **How do you compile it and call it from JavaScript?**

### Exporting Functions

- How do you export a C function to JavaScript?
- What's `EMSCRIPTEN_KEEPALIVE`?
- What's `EXPORTED_FUNCTIONS`?
- What's `EXPORTED_RUNTIME_METHODS`?
- Which method should you use?

### Function Signatures

- You have `int add(int a, int b)`. What JavaScript sees this as?
- What C types are supported?
- Can you return structs?
- Can you pass pointers?
- What about strings?

### Calling Conventions

- How do you call a WASM function from JavaScript?
- How do you pass arguments?
- How do you get the return value?
- What about multiple return values?
- What if the function has side effects?

### Build It: Math Library in WASM

Create useful math functions:

**Requirements:**

**Part 1: C Math Library (mathlib.c)**

```c
#include <emscripten/emscripten.h>
#include <math.h>

// Simple arithmetic
EMSCRIPTEN_KEEPALIVE
int add(int a, int b) {
    return a + b;
}

EMSCRIPTEN_KEEPALIVE
int multiply(int a, int b) {
    return a * b;
}

// Power function
EMSCRIPTEN_KEEPALIVE
double power(double base, double exponent) {
    return pow(base, exponent);
}

// Factorial (recursive)
EMSCRIPTEN_KEEPALIVE
int factorial(int n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}

// Fibonacci (iterative)
EMSCRIPTEN_KEEPALIVE
int fibonacci(int n) {
    if (n <= 1) return n;

    int prev = 0, curr = 1;
    for (int i = 2; i <= n; i++) {
        int next = prev + curr;
        prev = curr;
        curr = next;
    }
    return curr;
}

// Prime check
EMSCRIPTEN_KEEPALIVE
int isPrime(int n) {
    if (n <= 1) return 0;
    if (n <= 3) return 1;
    if (n % 2 == 0 || n % 3 == 0) return 0;

    for (int i = 5; i * i <= n; i += 6) {
        if (n % i == 0 || n % (i + 2) == 0)
            return 0;
    }
    return 1;
}

// GCD (greatest common divisor)
EMSCRIPTEN_KEEPALIVE
int gcd(int a, int b) {
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}
```

**Part 2: Compile**

```bash
emcc mathlib.c -o mathlib.js \
    -s EXPORTED_RUNTIME_METHODS='["ccall","cwrap"]' \
    -s EXPORTED_FUNCTIONS='["_add","_multiply","_power","_factorial","_fibonacci","_isPrime","_gcd"]' \
    -O3
```

**Part 3: Use in HTML (mathtest.html)**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>WASM Math Library</title>
    <style>
      body {
        font-family: Arial;
        margin: 20px;
      }
      .test {
        margin: 10px 0;
        padding: 10px;
        background: #f0f0f0;
      }
      button {
        margin: 5px;
        padding: 5px 10px;
      }
    </style>
  </head>
  <body>
    <h1>WebAssembly Math Library</h1>

    <div class="test">
      <h3>Addition</h3>
      <input type="number" id="add1" value="5" />
      +
      <input type="number" id="add2" value="3" />
      <button onclick="testAdd()">Calculate</button>
      <span id="addResult"></span>
    </div>

    <div class="test">
      <h3>Fibonacci</h3>
      <input type="number" id="fibInput" value="10" />
      <button onclick="testFib()">Calculate</button>
      <span id="fibResult"></span>
      <span id="fibTime"></span>
    </div>

    <div class="test">
      <h3>Prime Check</h3>
      <input type="number" id="primeInput" value="17" />
      <button onclick="testPrime()">Check</button>
      <span id="primeResult"></span>
    </div>

    <div class="test">
      <h3>Factorial</h3>
      <input type="number" id="factInput" value="10" />
      <button onclick="testFactorial()">Calculate</button>
      <span id="factResult"></span>
    </div>

    <script src="mathlib.js"></script>
    <script>
      Module.onRuntimeInitialized = function () {
        console.log("WASM module loaded!");

        // Create wrapped functions for easier calling
        window.wasmAdd = Module.cwrap("add", "number", ["number", "number"]);
        window.wasmMultiply = Module.cwrap("multiply", "number", [
          "number",
          "number",
        ]);
        window.wasmPower = Module.cwrap("power", "number", [
          "number",
          "number",
        ]);
        window.wasmFactorial = Module.cwrap("factorial", "number", ["number"]);
        window.wasmFibonacci = Module.cwrap("fibonacci", "number", ["number"]);
        window.wasmIsPrime = Module.cwrap("isPrime", "number", ["number"]);
        window.wasmGcd = Module.cwrap("gcd", "number", ["number", "number"]);
      };

      function testAdd() {
        const a = parseInt(document.getElementById("add1").value);
        const b = parseInt(document.getElementById("add2").value);
        const result = wasmAdd(a, b);
        document.getElementById("addResult").textContent = `= ${result}`;
      }

      function testFib() {
        const n = parseInt(document.getElementById("fibInput").value);
        const start = performance.now();
        const result = wasmFibonacci(n);
        const end = performance.now();

        document.getElementById("fibResult").textContent = `Result: ${result}`;
        document.getElementById("fibTime").textContent = `(${(
          end - start
        ).toFixed(2)}ms)`;
      }

      function testPrime() {
        const n = parseInt(document.getElementById("primeInput").value);
        const result = wasmIsPrime(n);
        document.getElementById("primeResult").textContent = result
          ? `${n} is PRIME`
          : `${n} is NOT prime`;
      }

      function testFactorial() {
        const n = parseInt(document.getElementById("factInput").value);
        const result = wasmFactorial(n);
        document.getElementById("factResult").textContent = `${n}! = ${result}`;
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Compare WASM Fibonacci with JavaScript version
- Test with large numbers - see when it's faster
- Add more complex functions (matrix operations?)
- Try different optimization flags (-O0 vs -O3)
- Use `ccall` instead of `cwrap` - what's the difference?
- Measure memory usage in DevTools

### Reflection Questions

1. **Exporting:**

   - Why use `EMSCRIPTEN_KEEPALIVE`?
   - What happens without it?
   - What's the underscore prefix in exports?

2. **Performance:**

   - When is WASM faster than JavaScript?
   - What's the overhead of calling WASM?
   - How do you minimize that overhead?

3. **Integration:**
   - How do you design APIs for WASM?
   - What makes a good WASM function?
   - When should you NOT use WASM?

---

## Section 6: Understanding the Compilation Output

### The Problem

Emscripten produces multiple files. **What's in them? Why do you need JavaScript glue code? What's actually happening?**

### The Glue Code

- What's in the `.js` file Emscripten generates?
- Why can't you just load the `.wasm` file directly?
- What does the glue code do?
- Can you write your own glue code?
- When can you skip the glue code?

### Module Loading

- How does `Module` get created?
- What's `Module.onRuntimeInitialized`?
- What's in `Module.asm`?
- What are the exported functions?
- How do you customize Module behavior?

### Memory Management Setup

- How is memory allocated for WASM?
- What's the initial memory size?
- What's `TOTAL_MEMORY` (now `INITIAL_MEMORY`)?
- How does memory growth work?
- What's in `Module.HEAP8`, `HEAP16`, `HEAP32`?

### The WASM Binary

- What's the structure of a `.wasm` file?
- What sections does it have?
- How do you inspect a `.wasm` file?
- What's in the code section?
- What's in the data section?

### Build It: Analyze Compilation Output

Examine what Emscripten produces:

**Requirements:**

**Part 1: Simple Program**

```c
// analyze.c
#include <emscripten/emscripten.h>
#include <stdlib.h>

EMSCRIPTEN_KEEPALIVE
int* createArray(int size) {
    return (int*)malloc(size * sizeof(int));
}

EMSCRIPTEN_KEEPALIVE
void fillArray(int* arr, int size) {
    for (int i = 0; i < size; i++) {
        arr[i] = i * i;
    }
}

EMSCRIPTEN_KEEPALIVE
void freeArray(int* arr) {
    free(arr);
}
```

**Part 2: Compile with Different Settings**

```bash
# Minimal output
emcc analyze.c -o analyze_minimal.js

# With source maps
emcc analyze.c -o analyze_debug.js -g

# With memory profiling
emcc analyze.c -o analyze_profile.js --profiling

# Standalone WASM (no JS glue)
emcc analyze.c -o analyze_standalone.wasm --no-entry

# With specific features
emcc analyze.c -o analyze_features.js \
    -s ALLOW_MEMORY_GROWTH=1 \
    -s EXPORTED_RUNTIME_METHODS='["ccall","cwrap","setValue","getValue"]'
```

**Part 3: Inspection Tools**

```bash
# View WASM as WAT
wasm2wat analyze_minimal.wasm -o analyze.wat

# View file structure
wasm-objdump -h analyze_minimal.wasm

# View exports
wasm-objdump -x analyze_minimal.wasm | grep "export"

# View imports
wasm-objdump -x analyze_minimal.wasm | grep "import"
```

**Part 4: Custom Module Loading**

```javascript
// custom_loader.js
async function loadWasmModule(wasmPath) {
  // Fetch the WASM binary
  const response = await fetch(wasmPath);
  const bytes = await response.arrayBuffer();

  // Define imports (what WASM needs from JS)
  const imports = {
    env: {
      memory: new WebAssembly.Memory({
        initial: 256, // 256 pages = 16MB
        maximum: 512, // Can grow to 32MB
      }),
      __memory_base: 0,
      table: new WebAssembly.Table({
        initial: 0,
        element: "anyfunc",
      }),
      __table_base: 0,
      abort: () => {
        throw new Error("WASM aborted");
      },
      // Add other imports as needed
    },
  };

  // Instantiate
  const module = await WebAssembly.instantiate(bytes, imports);

  // Wrap exports
  return {
    instance: module.instance,
    memory: imports.env.memory,
    exports: module.instance.exports,
  };
}

// Use it
loadWasmModule("analyze_standalone.wasm").then((wasm) => {
  console.log("Exports:", Object.keys(wasm.exports));
  console.log("Memory:", wasm.memory.buffer.byteLength);
});
```

**Experiments:**

- Compare file sizes with different optimization levels
- Look at the generated JavaScript - what does it do?
- Try loading WASM without Emscripten glue code
- Use browser DevTools to inspect the WASM module
- Add `console.log` to see Module initialization
- Profile memory usage during module load

### Reflection Questions

1. **Glue Code:**

   - What does it actually do?
   - Could you write it yourself?
   - When do you need it?

2. **WASM Structure:**

   - How is a WASM file organized?
   - What gets imported/exported?
   - How does it compare to native executables?

3. **Module System:**
   - How does WASM module loading work?
   - What's the browser's role?
   - What about security?

---

## Section 7: WASM Memory Model

### The Problem

C uses pointers. JavaScript doesn't (not directly). **WASM bridges this with linear memory** - a big array of bytes that both C and JavaScript can access.

### Understanding Linear Memory

- What is linear memory?
- How is it different from C's memory model?
- How is it represented in JavaScript?
- Can you have multiple memories?
- What's the memory size limit?

### Memory Pages

- What's a memory page?
- How big is a page?
- What's initial vs maximum memory?
- How does memory growth work?
- What happens if you run out?

### Accessing Memory from JavaScript

- What's `Module.HEAP8`?
- What's the difference between `HEAP8`, `HEAP16`, `HEAP32`?
- How do you read memory from JavaScript?
- How do you write memory from JavaScript?
- What about alignment?

### Pointers in WASM

- A C function returns a pointer. What does JavaScript see?
- How do you dereference a pointer in JavaScript?
- What if the pointer is freed?
- How do you pass a pointer to WASM?
- What about null pointers?

### Memory Layout

- Where do global variables go?
- Where does the heap start?
- Where does the stack start?
- How do they grow?
- What about stack overflow?

### Build It: Memory Exploration Tool

Understand WASM memory:

**Requirements:**

**Part 1: C Memory Functions (memory.c)**

```c
#include <emscripten/emscripten.h>
#include <stdlib.h>
#include <string.h>

// Global variable
int globalVar = 42;

// Return address of global
EMSCRIPTEN_KEEPALIVE
int* getGlobalAddress() {
    return &globalVar;
}

// Allocate memory and return pointer
EMSCRIPTEN_KEEPALIVE
int* allocateInts(int count) {
    return (int*)malloc(count * sizeof(int));
}

// Write to allocated memory
EMSCRIPTEN_KEEPALIVE
void writeInt(int* ptr, int index, int value) {
    ptr[index] = value;
}

// Read from allocated memory
EMSCRIPTEN_KEEPALIVE
int readInt(int* ptr, int index) {
    return ptr[index];
}

// Free allocated memory
EMSCRIPTEN_KEEPALIVE
void freeInts(int* ptr) {
    free(ptr);
}

// Get stack variable address
EMSCRIPTEN_KEEPALIVE
int* getStackAddress() {
    int localVar = 123;
    return &localVar; // Dangerous! Just for demonstration
}

// Fill array with pattern
EMSCRIPTEN_KEEPALIVE
void fillPattern(int* arr, int size, int pattern) {
    for (int i = 0; i < size; i++) {
        arr[i] = pattern + i;
    }
}
```

**Part 2: JavaScript Memory Inspector**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>WASM Memory Explorer</title>
    <style>
      body {
        font-family: monospace;
        margin: 20px;
      }
      .section {
        margin: 20px 0;
        padding: 10px;
        background: #f5f5f5;
      }
      .memory-view {
        font-family: monospace;
        background: #fff;
        padding: 10px;
        overflow-x: auto;
      }
      button {
        margin: 5px;
      }
    </style>
  </head>
  <body>
    <h1>WASM Memory Explorer</h1>

    <div class="section">
      <h3>Memory Info</h3>
      <div id="memoryInfo"></div>
    </div>

    <div class="section">
      <h3>Pointer Demonstration</h3>
      <button onclick="testPointers()">Test Pointers</button>
      <div id="pointerResults"></div>
    </div>

    <div class="section">
      <h3>Memory View (First 256 bytes)</h3>
      <button onclick="showMemory()">Show Memory</button>
      <div id="memoryView" class="memory-view"></div>
    </div>

    <div class="section">
      <h3>Custom Memory Operations</h3>
      <button onclick="testCustomOps()">Run Tests</button>
      <div id="customResults"></div>
    </div>

    <script src="memory.js"></script>
    <script>
      let wasmModule;

      Module.onRuntimeInitialized = function () {
        wasmModule = Module;
        displayMemoryInfo();
      };

      function displayMemoryInfo() {
        const memory = wasmModule.HEAP8.buffer;
        const info = `
                Total Memory: ${memory.byteLength} bytes (${
          memory.byteLength / 1024 / 1024
        } MB)
                Pages: ${memory.byteLength / 65536}
                HEAP8 length: ${wasmModule.HEAP8.length}
                HEAP32 length: ${wasmModule.HEAP32.length}
            `;
        document.getElementById("memoryInfo").innerHTML =
          "<pre>" + info + "</pre>";
      }

      function testPointers() {
        const results = [];

        // Get global variable address
        const globalPtr = wasmModule._getGlobalAddress();
        results.push(`Global variable pointer: ${globalPtr}`);
        results.push(`Value at pointer: ${wasmModule.HEAP32[globalPtr >> 2]}`);

        // Allocate memory
        const arraySize = 10;
        const arrayPtr = wasmModule._allocateInts(arraySize);
        results.push(`\nAllocated array pointer: ${arrayPtr}`);

        // Write to memory from WASM
        wasmModule._fillPattern(arrayPtr, arraySize, 100);

        // Read from memory in JavaScript
        results.push("\nArray contents (read from JS):");
        for (let i = 0; i < arraySize; i++) {
          const offset = (arrayPtr >> 2) + i;
          const value = wasmModule.HEAP32[offset];
          results.push(`  [${i}] = ${value}`);
        }

        // Write from JavaScript
        results.push("\nWriting from JavaScript...");
        wasmModule.HEAP32[(arrayPtr >> 2) + 5] = 999;

        // Read back in WASM
        const readValue = wasmModule._readInt(arrayPtr, 5);
        results.push(`Value read back in WASM: ${readValue}`);

        // Free memory
        wasmModule._freeInts(arrayPtr);
        results.push("\nMemory freed");

        document.getElementById("pointerResults").innerHTML =
          "<pre>" + results.join("\n") + "</pre>";
      }

      function showMemory() {
        const bytes = new Uint8Array(wasmModule.HEAP8.buffer, 0, 256);
        let output =
          "Offset  00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F\n";
        output += "------  -----------------------------------------------\n";

        for (let i = 0; i < bytes.length; i += 16) {
          let line = i.toString(16).padStart(6, "0") + "  ";
          for (let j = 0; j < 16 && i + j < bytes.length; j++) {
            line += bytes[i + j].toString(16).padStart(2, "0") + " ";
          }
          output += line + "\n";
        }

        document.getElementById("memoryView").innerHTML =
          "<pre>" + output + "</pre>";
      }

      function testCustomOps() {
        const results = [];

        // Test 1: Write and read different types
        const ptr = wasmModule._allocateInts(4);

        // Write as int32
        wasmModule.HEAP32[ptr >> 2] = 0x12345678;

        // Read as bytes
        const byte0 = wasmModule.HEAP8[ptr];
        const byte1 = wasmModule.HEAP8[ptr + 1];
        const byte2 = wasmModule.HEAP8[ptr + 2];
        const byte3 = wasmModule.HEAP8[ptr + 3];

        results.push("Wrote 0x12345678 as int32");
        results.push(
          `Read as bytes: ${byte0.toString(16)} ${byte1.toString(
            16
          )} ${byte2.toString(16)} ${byte3.toString(16)}`
        );

        // Test 2: Memory growth
        results.push(
          `\nCurrent memory: ${
            wasmModule.HEAP8.buffer.byteLength / 1024 / 1024
          } MB`
        );

        wasmModule._freeInts(ptr);

        document.getElementById("customResults").innerHTML =
          "<pre>" + results.join("\n") + "</pre>";
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Allocate large amounts of memory - watch it grow
- Try to access freed memory - what happens?
- Write past array bounds - see the corruption
- Compare pointer addresses between calls
- Test with different data types (int8, int16, int32, float, double)
- Monitor memory in browser DevTools

### Reflection Questions

1. **Memory Model:**

   - How does linear memory work?
   - How is it different from native memory?
   - What are the restrictions?

2. **JavaScript Interaction:**

   - How do you safely pass data?
   - What about pointer lifetime?
   - How do you prevent use-after-free?

3. **Performance:**
   - What's the cost of memory access?
   - When should you copy vs share memory?
   - How does memory growth affect performance?

---

# 🔵 PART 3: JAVASCRIPT-WASM INTEROP

---

## Section 8: Loading and Instantiating WASM Modules

### The Problem

You have a `.wasm` file. **How do you load it? How do you call its functions? What if loading fails?**

### Loading Methods

- What's `WebAssembly.instantiate()`?
- What's `WebAssembly.instantiateStreaming()`?
- What's the difference between them?
- When should you use each?
- What about `WebAssembly.compile()`?

### Module and Instance

- What's a WebAssembly.Module?
- What's a WebAssembly.Instance?
- What's the difference?
- Can you create multiple instances?
- Why would you want multiple instances?

### Imports and Exports

- What are imports?
- What are exports?
- How do you provide imports?
- How do you access exports?
- What can be imported/exported?

### Error Handling

- What if the WASM file is invalid?
- What if imports are missing?
- What if instantiation fails?
- How do you handle errors gracefully?
- What about runtime errors?

### Build It: WASM Module Loader

Create a robust loading system:

**Requirements:**

```javascript
// wasm-loader.js
class WasmLoader {
  constructor() {
    this.modules = new Map();
  }

  async load(name, url, imports = {}) {
    try {
      console.log(`Loading WASM module: ${name}`);

      // Check if already loaded
      if (this.modules.has(name)) {
        console.log(`Module ${name} already loaded`);
        return this.modules.get(name);
      }

      // Fetch and instantiate
      const response = await fetch(url);

      if (!response.ok) {
        throw new Error(`Failed to fetch: ${response.status}`);
      }

      // Use streaming if available
      let result;
      if (WebAssembly.instantiateStreaming) {
        result = await WebAssembly.instantiateStreaming(response, imports);
      } else {
        const buffer = await response.arrayBuffer();
        result = await WebAssembly.instantiate(buffer, imports);
      }

      // Store module info
      const moduleInfo = {
        name,
        url,
        module: result.module,
        instance: result.instance,
        exports: result.instance.exports,
        loadedAt: new Date(),
      };

      this.modules.set(name, moduleInfo);

      console.log(`Module ${name} loaded successfully`);
      console.log(`Exports:`, Object.keys(moduleInfo.exports));

      return moduleInfo;
    } catch (error) {
      console.error(`Error loading module ${name}:`, error);
      throw error;
    }
  }

  get(name) {
    return this.modules.get(name);
  }

  has(name) {
    return this.modules.has(name);
  }

  getExports(name) {
    const module = this.modules.get(name);
    return module ? module.exports : null;
  }

  async loadMultiple(modules) {
    const promises = modules.map(({name, url, imports}) =>
      this.load(name, url, imports)
    );
    return Promise.all(promises);
  }

  listModules() {
    return Array.from(this.modules.keys());
  }
}

// Usage example
const loader = new WasmLoader();

async function example() {
  try {
    // Load single module
    const math = await loader.load("math", "math.wasm");
    const result = math.exports.add(5, 3);
    console.log("5 + 3 =", result);

    // Load multiple modules
    await loader.loadMultiple([
      {name: "image", url: "image.wasm"},
      {name: "crypto", url: "crypto.wasm"},
    ]);

    // Use loaded module
    if (loader.has("image")) {
      const imageExports = loader.getExports("image");
      // Use imageExports...
    }
  } catch (error) {
    console.error("Failed to load modules:", error);
  }
}
```

**Part 2: Create Test Modules**

Simple C code to test:

```c
// test.c
#include <emscripten/emscripten.h>

EMSCRIPTEN_KEEPALIVE
int add(int a, int b) { return a + b; }

EMSCRIPTEN_KEEPALIVE
int multiply(int a, int b) { return a * b; }

EMSCRIPTEN_KEEPALIVE
double divide(double a, double b) {
    return b != 0 ? a / b : 0;
}
```

Compile:

```bash
emcc test.c -o test.wasm \
    --no-entry \
    -s EXPORTED_FUNCTIONS='["_add","_multiply","_divide"]'
```

**Part 3: Test Page**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>WASM Loader Test</title>
  </head>
  <body>
    <h1>WASM Module Loader</h1>
    <button onclick="testLoader()">Test Loader</button>
    <div id="results"></div>

    <script src="wasm-loader.js"></script>
    <script>
      const loader = new WasmLoader();

      async function testLoader() {
        const results = [];

        try {
          // Load module
          results.push("Loading module...");
          const module = await loader.load("test", "test.wasm");
          results.push("✓ Module loaded");

          // Test functions
          const add = module.exports.add;
          results.push(`5 + 3 = ${add(5, 3)}`);

          const multiply = module.exports.multiply;
          results.push(`5 * 3 = ${multiply(5, 3)}`);

          const divide = module.exports.divide;
          results.push(`15 / 3 = ${divide(15, 3)}`);

          // List all modules
          results.push(`\nLoaded modules: ${loader.listModules().join(", ")}`);
        } catch (error) {
          results.push(`✗ Error: ${error.message}`);
        }

        document.getElementById("results").innerHTML =
          "<pre>" + results.join("\n") + "</pre>";
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Load a non-existent module - handle error
- Load same module twice - check caching
- Create module with imports - provide them
- Test with large WASM files
- Measure loading time
- Test in different browsers

### Reflection Questions

1. **Loading:**

   - What's the best way to load WASM?
   - When does streaming help?
   - How do you handle errors?

2. **Module vs Instance:**

   - When do you need multiple instances?
   - What gets shared, what doesn't?
   - How does this affect performance?

3. **Production:**
   - How do you manage multiple modules?
   - What about versioning?
   - How do you handle updates?

---

## Section 9: Calling WASM from JavaScript

### The Problem

You have WASM functions. JavaScript needs to call them. **But types don't match perfectly. Numbers are easy, but what about complex data?**

### Basic Function Calls

- How do you call a WASM function from JavaScript?
- You have `int add(int a, int b)` in C. How do you call it in JS?
- What about return values?
- Can you call functions immediately after loading?
- What's the performance of calling WASM from JS?

### Type Conversions

- C has `int`, `float`, `double`. What does JavaScript see?
- JavaScript has 64-bit floats. What about C's 32-bit integers?
- What happens with overflow?
- What about signed vs unsigned?
- How do you pass booleans?

### Using cwrap and ccall

- What's `Module.cwrap`?
- What's `Module.ccall`?
- What's the difference?
- When should you use each?
- What's the performance difference?

### Performance Considerations

- What's the overhead of calling WASM?
- Should you call WASM in a loop?
- What about batching operations?
- When is the boundary crossing expensive?
- How do you minimize calls?

### Build It: Function Call Benchmark

Measure the cost of JavaScript-WASM interaction:

**Requirements:**

**Part 1: C Functions (benchmark.c)**

```c
#include <emscripten/emscripten.h>

// Simple addition
EMSCRIPTEN_KEEPALIVE
int add(int a, int b) {
    return a + b;
}

// Heavy computation
EMSCRIPTEN_KEEPALIVE
int heavyComputation(int n) {
    int sum = 0;
    for (int i = 0; i < n; i++) {
        sum += i * i;
    }
    return sum;
}

// Batch operation (many ops in one call)
EMSCRIPTEN_KEEPALIVE
void batchAdd(int* arr, int size, int value) {
    for (int i = 0; i < size; i++) {
        arr[i] += value;
    }
}

// Multiple return values via pointer
EMSCRIPTEN_KEEPALIVE
void divmod(int a, int b, int* quotient, int* remainder) {
    *quotient = a / b;
    *remainder = a % b;
}
```

**Part 2: Compile**

```bash
emcc benchmark.c -o benchmark.js \
    -s EXPORTED_RUNTIME_METHODS='["ccall","cwrap"]' \
    -O3
```

**Part 3: Benchmark Test**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>WASM Call Benchmark</title>
    <style>
      body {
        font-family: monospace;
        margin: 20px;
      }
      .test {
        margin: 20px 0;
        padding: 10px;
        background: #f0f0f0;
      }
      .result {
        color: #006600;
        font-weight: bold;
      }
      .slower {
        color: #cc0000;
      }
    </style>
  </head>
  <body>
    <h1>JavaScript vs WASM Call Overhead</h1>

    <div class="test">
      <h3>Test 1: Simple Operation (1 million calls)</h3>
      <button onclick="test1()">Run Test</button>
      <div id="test1Result"></div>
    </div>

    <div class="test">
      <h3>Test 2: Heavy Computation (1000 calls)</h3>
      <button onclick="test2()">Run Test</button>
      <div id="test2Result"></div>
    </div>

    <div class="test">
      <h3>Test 3: Batch vs Individual Calls</h3>
      <button onclick="test3()">Run Test</button>
      <div id="test3Result"></div>
    </div>

    <script src="benchmark.js"></script>
    <script>
      let wasmAdd, wasmHeavy, wasmBatchAdd;

      Module.onRuntimeInitialized = function () {
        wasmAdd = Module.cwrap("add", "number", ["number", "number"]);
        wasmHeavy = Module.cwrap("heavyComputation", "number", ["number"]);
        wasmBatchAdd = Module.cwrap("batchAdd", null, [
          "number",
          "number",
          "number",
        ]);
      };

      // JavaScript equivalent
      function jsAdd(a, b) {
        return a + b;
      }

      function jsHeavyComputation(n) {
        let sum = 0;
        for (let i = 0; i < n; i++) {
          sum += i * i;
        }
        return sum;
      }

      function test1() {
        const iterations = 1000000;

        // JavaScript
        let start = performance.now();
        for (let i = 0; i < iterations; i++) {
          jsAdd(5, 3);
        }
        let jsTime = performance.now() - start;

        // WASM
        start = performance.now();
        for (let i = 0; i < iterations; i++) {
          wasmAdd(5, 3);
        }
        let wasmTime = performance.now() - start;

        const result = `
                JavaScript: ${jsTime.toFixed(2)}ms
                WASM: ${wasmTime.toFixed(2)}ms
                ${
                  wasmTime < jsTime
                    ? `WASM is ${(jsTime / wasmTime).toFixed(2)}x faster`
                    : `JavaScript is ${(wasmTime / jsTime).toFixed(2)}x faster`
                }
                
                Note: For simple operations with many boundary crossings,
                JavaScript may be faster due to call overhead.
            `;

        document.getElementById("test1Result").innerHTML =
          '<pre class="result">' + result + "</pre>";
      }

      function test2() {
        const iterations = 1000;
        const n = 10000;

        // JavaScript
        let start = performance.now();
        for (let i = 0; i < iterations; i++) {
          jsHeavyComputation(n);
        }
        let jsTime = performance.now() - start;

        // WASM
        start = performance.now();
        for (let i = 0; i < iterations; i++) {
          wasmHeavy(n);
        }
        let wasmTime = performance.now() - start;

        const result = `
                JavaScript: ${jsTime.toFixed(2)}ms
                WASM: ${wasmTime.toFixed(2)}ms
                WASM is ${(jsTime / wasmTime).toFixed(2)}x faster
                
                Note: For heavy computation, WASM shines even with
                the overhead of boundary crossings.
            `;

        document.getElementById("test2Result").innerHTML =
          '<pre class="result">' + result + "</pre>";
      }

      function test3() {
        const arraySize = 10000;
        const value = 5;

        // Individual calls
        const arr1Ptr = Module._malloc(arraySize * 4);
        let start = performance.now();
        for (let i = 0; i < arraySize; i++) {
          Module.HEAP32[(arr1Ptr >> 2) + i] += value;
        }
        let individualTime = performance.now() - start;
        Module._free(arr1Ptr);

        // Batch call
        const arr2Ptr = Module._malloc(arraySize * 4);
        start = performance.now();
        wasmBatchAdd(arr2Ptr, arraySize, value);
        let batchTime = performance.now() - start;
        Module._free(arr2Ptr);

        const result = `
                Individual JS operations: ${individualTime.toFixed(2)}ms
                Batch WASM call: ${batchTime.toFixed(2)}ms
                Batch is ${(individualTime / batchTime).toFixed(2)}x faster
                
                Lesson: Minimize boundary crossings by batching operations!
            `;

        document.getElementById("test3Result").innerHTML =
          '<pre class="result">' + result + "</pre>";
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Test with different operation complexities
- Vary the number of calls
- Test calling WASM in tight loops vs batching
- Measure with browser profiler
- Try different browsers - does overhead vary?
- Test on mobile devices

### Reflection Questions

1. **Performance:**

   - When is calling WASM worth it?
   - What's the break-even point?
   - How do you minimize overhead?

2. **Design:**

   - How do you design WASM APIs?
   - Should functions be fine-grained or coarse?
   - What about batching?

3. **Best Practices:**
   - When should you call WASM?
   - When should you stay in JavaScript?
   - How do you profile the boundary?

---

## Section 10: Calling JavaScript from WASM

### The Problem

Your C code needs to call JavaScript. Log to console. Access the DOM. Make HTTP requests. **WASM can call JavaScript through imported functions.**

### Importing JavaScript Functions

- How do you call JavaScript from C?
- What's `EM_JS`?
- What's `EM_ASM`?
- What's an import object?
- How do you provide imports when loading?

### Function Signatures

- You import a JavaScript function. What types can it use?
- Can you pass pointers to JavaScript?
- Can you return pointers from JavaScript?
- What about strings?
- What about objects?

### Using EM_JS

- How do you define a JavaScript function in C?
- What's the syntax?
- How do you call it?
- What are the limitations?
- When should you use this?

### Using EM_ASM

- How do you inline JavaScript in C?
- What's the difference from EM_JS?
- How do you pass arguments?
- How do you get return values?
- When should you use this?

### Build It: WASM with JS Callbacks

Create C code that calls JavaScript:

**Requirements:**

**Part 1: C Code with JS Callbacks (callbacks.c)**

```c
#include <emscripten/emscripten.h>
#include <stdio.h>

// Define a JavaScript function to be called from C
EM_JS(void, js_log, (const char* message), {
    console.log("From WASM: " + UTF8ToString(message));
});

EM_JS(void, js_alert, (const char* message), {
    alert(UTF8ToString(message));
});

EM_JS(int, js_confirm, (const char* message), {
    return confirm(UTF8ToString(message)) ? 1 : 0;
});

EM_JS(double, js_get_timestamp, (), {
    return Date.now();
});

EM_JS(void, js_update_dom, (int value), {
    const element = document.getElementById('wasmOutput');
    if (element) {
        element.textContent = 'Value from WASM: ' + value;
    }
});

// Use inline JavaScript
EMSCRIPTEN_KEEPALIVE
void inlineJavaScript() {
    EM_ASM({
        console.log('This is inline JavaScript!');
        console.log('You can access C variables too');
    });
}

// Pass data to inline JavaScript
EMSCRIPTEN_KEEPALIVE
void passToInlineJS(int x, int y) {
    EM_ASM({
        console.log('Received from C: x=' + $0 + ', y=' + $1);
        console.log('Sum:', $0 + $1);
    }, x, y);
}

// Get return value from inline JavaScript
EMSCRIPTEN_KEEPALIVE
int getFromInlineJS() {
    int result = EM_ASM_INT({
        return Math.floor(Math.random() * 100);
    });
    return result;
}

// Example: Progress callback
EMSCRIPTEN_KEEPALIVE
void processWithProgress(int total) {
    js_log("Starting processing...");

    for (int i = 0; i <= total; i++) {
        // Do some work
        int sum = 0;
        for (int j = 0; j < 1000; j++) {
            sum += j;
        }

        // Update progress
        if (i % 10 == 0) {
            js_update_dom(i * 100 / total);
        }
    }

    js_log("Processing complete!");
}

// Example: User confirmation
EMSCRIPTEN_KEEPALIVE
int deleteWithConfirmation() {
    int confirmed = js_confirm("Are you sure you want to delete?");

    if (confirmed) {
        js_log("User confirmed deletion");
        return 1;
    } else {
        js_log("User cancelled");
        return 0;
    }
}

// Example: Timing
EMSCRIPTEN_KEEPALIVE
void measureJSCall() {
    double start = js_get_timestamp();

    // Do some work
    int sum = 0;
    for (int i = 0; i < 1000000; i++) {
        sum += i;
    }

    double end = js_get_timestamp();
    double elapsed = end - start;

    char buffer[100];
    sprintf(buffer, "Elapsed: %.2fms", elapsed);
    js_log(buffer);
}
```

**Part 2: Compile**

```bash
emcc callbacks.c -o callbacks.js -O3
```

**Part 3: Test Page**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>WASM Calling JavaScript</title>
    <style>
      body {
        font-family: Arial;
        margin: 20px;
      }
      .test {
        margin: 20px 0;
        padding: 10px;
        background: #f0f0f0;
      }
      button {
        margin: 5px;
        padding: 8px 15px;
      }
      #wasmOutput {
        font-size: 24px;
        color: #006600;
        margin: 10px 0;
        font-weight: bold;
      }
    </style>
  </head>
  <body>
    <h1>WASM Calling JavaScript</h1>

    <div class="test">
      <h3>Console Logging</h3>
      <button onclick="testLogging()">Test Logging</button>
      <p>Check browser console (F12)</p>
    </div>

    <div class="test">
      <h3>Alert Dialog</h3>
      <button onclick="testAlert()">Test Alert</button>
    </div>

    <div class="test">
      <h3>Confirm Dialog</h3>
      <button onclick="testConfirm()">Test Confirm</button>
      <div id="confirmResult"></div>
    </div>

    <div class="test">
      <h3>DOM Manipulation</h3>
      <button onclick="testDOMUpdate()">Process with Progress</button>
      <div id="wasmOutput">Ready</div>
    </div>

    <div class="test">
      <h3>Inline JavaScript</h3>
      <button onclick="testInline()">Test Inline JS</button>
    </div>

    <div class="test">
      <h3>Timing</h3>
      <button onclick="testTiming()">Measure Performance</button>
    </div>

    <script src="callbacks.js"></script>
    <script>
      let wasmModule;

      Module.onRuntimeInitialized = function() {
          wasmModule = Module;
          console.log("WASM module loaded and ready");
      };

      function testLogging() {
          wasmModule._inlineJavaScript();
          wasmModule._passToInlineJS(42, 58);
      }

      function testAlert() {
          // This calls EM_JS js_alert which shows an alert
          // We'll trigger it through a C function
          EM_ASM({
              _js_alert("Hello from WASM via EM_ASM!");
          });
      }

      function testConfirm() {
          const result = wasmModule._deleteWithConfirmation();
          document.getElementById('confirmResult').textContent =
              result ? '✓ Confirmed' : '✗ Cancelled';
      }

      function testDOMUpdate() {
          wasmModule._processWithProgress(100);
      }

      function testInline() {
          const random = wasmModule._getFromInlineJS();
          console.log('Random number from inline JS:', random);
      }

      function testTiming() {
          wasmModule._measureJSCall();
      }
    </script>
  </body>
</html>
```

**Part 4: Custom Import Object**

Advanced: Provide JavaScript functions as imports:

```c
// custom_imports.c
#include <emscripten/emscripten.h>

// Declare external function (provided by JS)
extern void external_log(const char* msg);
extern int external_add(int a, int b);

EMSCRIPTEN_KEEPALIVE
void useExternalFunctions() {
    external_log("Calling external function!");
    int result = external_add(10, 20);
    // result = 30
}
```

```javascript
// Provide the imports
const imports = {
  env: {
    external_log: (msgPtr) => {
      const msg = UTF8ToString(msgPtr);
      console.log("JS received:", msg);
    },
    external_add: (a, b) => {
      return a + b;
    },
  },
};

// Load with imports
WebAssembly.instantiateStreaming(fetch("custom_imports.wasm"), imports).then(
  (result) => {
    result.instance.exports.useExternalFunctions();
  }
);
```

**Experiments:**

- Call expensive JavaScript functions from C - measure overhead
- Try passing different data types
- Create a progress callback system
- Implement event handlers in C that call JS
- Try calling DOM APIs directly
- Measure the cost of crossing boundaries

### Reflection Questions

1. **Calling JS:**

   - When should C call JavaScript?
   - What's the performance cost?
   - How do you design the interface?

2. **EM_JS vs EM_ASM:**

   - What's the difference?
   - When should you use each?
   - What are the trade-offs?

3. **Architecture:**
   - How do you structure hybrid apps?
   - What logic goes in WASM vs JS?
   - How do you minimize calls?

---

## Section 11: Passing Complex Data Between JS and WASM

### The Problem

Numbers are easy. **But what about strings? Arrays? Objects? Structs?** You need to understand memory layout and serialization.

### Strings

- C uses null-terminated char arrays. How do you pass them to JavaScript?
- How do you get strings from JavaScript into C?
- What's `UTF8ToString`?
- What's `stringToUTF8`?
- Who owns the string memory?

### Arrays

- How do you pass an array from C to JavaScript?
- How do you pass an array from JavaScript to C?
- Who allocates memory?
- What about ownership and lifetime?
- How do you handle cleanup?

### Structs

- Can you pass a struct to JavaScript?
- How does JavaScript access struct fields?
- What about nested structs?
- What about arrays of structs?
- How do you serialize/deserialize?

### Memory Ownership

- Who allocates memory - C or JavaScript?
- Who frees memory?
- What happens if you forget to free?
- How do you prevent use-after-free?
- What about shared ownership?

### Build It: Complex Data Transfer

Handle all data types:

**Requirements:**

**Part 1: C Data Handling (data_transfer.c)**

```c
#include <emscripten/emscripten.h>
#include <stdlib.h>
#include <string.h>
#include <stdio.h>

// === String Handling ===

EMSCRIPTEN_KEEPALIVE
char* createString(const char* input) {
    size_t len = strlen(input);
    char* result = (char*)malloc(len + 20);
    sprintf(result, "Processed: %s", input);
    return result;
}

EMSCRIPTEN_KEEPALIVE
void freeString(char* str) {
    free(str);
}

EMSCRIPTEN_KEEPALIVE
int getStringLength(const char* str) {
    return strlen(str);
}

EMSCRIPTEN_KEEPALIVE
void modifyString(char* str) {
    // Convert to uppercase
    for (int i = 0; str[i]; i++) {
        if (str[i] >= 'a' && str[i] <= 'z') {
            str[i] -= 32;
        }
    }
}

// === Array Handling ===

EMSCRIPTEN_KEEPALIVE
int* createArray(int size) {
    return (int*)malloc(size * sizeof(int));
}

EMSCRIPTEN_KEEPALIVE
void fillArray(int* arr, int size, int start) {
    for (int i = 0; i < size; i++) {
        arr[i] = start + i;
    }
}

EMSCRIPTEN_KEEPALIVE
int sumArray(int* arr, int size) {
    int sum = 0;
    for (int i = 0; i < size; i++) {
        sum += arr[i];
    }
    return sum;
}

EMSCRIPTEN_KEEPALIVE
void freeArray(int* arr) {
    free(arr);
}

// === Struct Handling ===

typedef struct {
    int id;
    char name[50];
    float value;
    int active;
} Record;

EMSCRIPTEN_KEEPALIVE
Record* createRecord(int id, const char* name, float value) {
    Record* rec = (Record*)malloc(sizeof(Record));
    rec->id = id;
    strncpy(rec->name, name, 49);
    rec->name[49] = '\0';
    rec->value = value;
    rec->active = 1;
    return rec;
}

EMSCRIPTEN_KEEPALIVE
void printRecord(Record* rec) {
    printf("Record { id: %d, name: %s, value: %.2f, active: %d }\n",
           rec->id, rec->name, rec->value, rec->active);
}

EMSCRIPTEN_KEEPALIVE
void freeRecord(Record* rec) {
    free(rec);
}

// Get struct field offsets (for JavaScript access)
EMSCRIPTEN_KEEPALIVE
int getRecordIdOffset() { return offsetof(Record, id); }

EMSCRIPTEN_KEEPALIVE
int getRecordNameOffset() { return offsetof(Record, name); }

EMSCRIPTEN_KEEPALIVE
int getRecordValueOffset() { return offsetof(Record, value); }

EMSCRIPTEN_KEEPALIVE
int getRecordActiveOffset() { return offsetof(Record, active); }

EMSCRIPTEN_KEEPALIVE
int getRecordSize() { return sizeof(Record); }

// === Array of Structs ===

EMSCRIPTEN_KEEPALIVE
Record* createRecordArray(int count) {
    return (Record*)malloc(count * sizeof(Record));
}

EMSCRIPTEN_KEEPALIVE
void fillRecordArray(Record* arr, int count) {
    for (int i = 0; i < count; i++) {
        arr[i].id = i + 1;
        sprintf(arr[i].name, "Item %d", i + 1);
        arr[i].value = (i + 1) * 10.5f;
        arr[i].active = i % 2;
    }
}

EMSCRIPTEN_KEEPALIVE
void freeRecordArray(Record* arr) {
    free(arr);
}
```

**Part 2: JavaScript Wrapper**

```javascript
// data-wrapper.js
class WasmDataHandler {
  constructor(wasmModule) {
    this.Module = wasmModule;
  }

  // === String Methods ===

  createString(input) {
    // Allocate memory for input string
    const inputPtr = this.Module.allocateUTF8(input);

    // Call WASM function
    const resultPtr = this.Module._createString(inputPtr);

    // Convert result to JS string
    const result = this.Module.UTF8ToString(resultPtr);

    // Free memory
    this.Module._free(inputPtr);
    this.Module._freeString(resultPtr);

    return result;
  }

  modifyString(input) {
    // Allocate and copy string
    const ptr = this.Module.allocateUTF8(input);

    // Modify in place
    this.Module._modifyString(ptr);

    // Read back
    const result = this.Module.UTF8ToString(ptr);

    // Free
    this.Module._free(ptr);

    return result;
  }

  // === Array Methods ===

  createAndFillArray(size, start) {
    // Create array in WASM
    const ptr = this.Module._createArray(size);

    // Fill it
    this.Module._fillArray(ptr, size, start);

    // Read to JavaScript
    const array = new Int32Array(this.Module.HEAP32.buffer, ptr, size).slice(); // slice creates a copy

    // Free WASM memory
    this.Module._freeArray(ptr);

    return array;
  }

  sumJSArray(jsArray) {
    // Allocate memory in WASM
    const ptr = this.Module._createArray(jsArray.length);

    // Copy JS array to WASM memory
    this.Module.HEAP32.set(jsArray, ptr >> 2);

    // Call WASM function
    const sum = this.Module._sumArray(ptr, jsArray.length);

    // Free memory
    this.Module._freeArray(ptr);

    return sum;
  }

  // === Struct Methods ===

  createRecord(id, name, value) {
    // Allocate name string
    const namePtr = this.Module.allocateUTF8(name);

    // Create record
    const recordPtr = this.Module._createRecord(id, namePtr, value);

    // Free name
    this.Module._free(namePtr);

    // Read record fields
    const record = this.readRecord(recordPtr);

    // Free record
    this.Module._freeRecord(recordPtr);

    return record;
  }

  readRecord(ptr) {
    const idOffset = this.Module._getRecordIdOffset();
    const nameOffset = this.Module._getRecordNameOffset();
    const valueOffset = this.Module._getRecordValueOffset();
    const activeOffset = this.Module._getRecordActiveOffset();

    return {
      id: this.Module.HEAP32[(ptr + idOffset) >> 2],
      name: this.Module.UTF8ToString(ptr + nameOffset),
      value: this.Module.HEAPF32[(ptr + valueOffset) >> 2],
      active: this.Module.HEAP32[(ptr + activeOffset) >> 2],
    };
  }

  createRecordArray(count) {
    const arrayPtr = this.Module._createRecordArray(count);
    this.Module._fillRecordArray(arrayPtr, count);

    const records = [];
    const recordSize = this.Module._getRecordSize();

    for (let i = 0; i < count; i++) {
      const recordPtr = arrayPtr + i * recordSize;
      records.push(this.readRecord(recordPtr));
    }

    this.Module._freeRecordArray(arrayPtr);

    return records;
  }
}
```

**Part 3: Test Page**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Complex Data Transfer</title>
    <style>
      body {
        font-family: monospace;
        margin: 20px;
      }
      .test {
        margin: 20px 0;
        padding: 10px;
        background: #f0f0f0;
      }
      button {
        margin: 5px;
        padding: 5px 10px;
      }
      pre {
        background: white;
        padding: 10px;
      }
    </style>
  </head>
  <body>
    <h1>Complex Data Transfer: JS ↔ WASM</h1>

    <div class="test">
      <h3>Strings</h3>
      <button onclick="testStrings()">Test Strings</button>
      <pre id="stringResult"></pre>
    </div>

    <div class="test">
      <h3>Arrays</h3>
      <button onclick="testArrays()">Test Arrays</button>
      <pre id="arrayResult"></pre>
    </div>

    <div class="test">
      <h3>Structs</h3>
      <button onclick="testStructs()">Test Structs</button>
      <pre id="structResult"></pre>
    </div>

    <div class="test">
      <h3>Array of Structs</h3>
      <button onclick="testRecordArray()">Test Record Array</button>
      <pre id="recordArrayResult"></pre>
    </div>

    <script src="data_transfer.js"></script>
    <script src="data-wrapper.js"></script>
    <script>
      let handler;

      Module.onRuntimeInitialized = function () {
        handler = new WasmDataHandler(Module);
        console.log("Ready for complex data transfer!");
      };

      function testStrings() {
        const results = [];

        // Test 1: Create string
        const result1 = handler.createString("Hello WASM");
        results.push(`Created: "${result1}"`);

        // Test 2: Modify string
        const result2 = handler.modifyString("hello world");
        results.push(`Modified: "${result2}"`);

        document.getElementById("stringResult").textContent =
          results.join("\n");
      }

      function testArrays() {
        const results = [];

        // Test 1: Create and fill array in WASM
        const array1 = handler.createAndFillArray(10, 100);
        results.push(`WASM array: [${array1.join(", ")}]`);

        // Test 2: Sum JS array in WASM
        const jsArray = [1, 2, 3, 4, 5];
        const sum = handler.sumJSArray(jsArray);
        results.push(`Sum of [${jsArray}] = ${sum}`);

        document.getElementById("arrayResult").textContent = results.join("\n");
      }

      function testStructs() {
        const results = [];

        // Create records
        const record1 = handler.createRecord(1, "Alice", 99.5);
        const record2 = handler.createRecord(2, "Bob", 87.3);

        results.push("Record 1:");
        results.push(JSON.stringify(record1, null, 2));
        results.push("\nRecord 2:");
        results.push(JSON.stringify(record2, null, 2));

        document.getElementById("structResult").textContent =
          results.join("\n");
      }

      function testRecordArray() {
        const records = handler.createRecordArray(5);

        const output = records
          .map((r, i) => `[${i}] ${JSON.stringify(r)}`)
          .join("\n");

        document.getElementById("recordArrayResult").textContent = output;
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Pass very long strings - test limits
- Create large arrays - measure performance
- Try nested structs
- Test with Unicode strings
- Implement a linked list across boundary
- Measure serialization overhead

### Reflection Questions

1. **Data Transfer:**

   - What's the cost of passing data?
   - How do you minimize copies?
   - When should you keep data in WASM?

2. **Memory Management:**

   - Who should own memory?
   - How do you prevent leaks?
   - What about shared buffers?

3. **Design:**
   - How do you design data interfaces?
   - What should be serialized?
   - When should you use binary formats?

---

# 🟣 PART 4: MEMORY MANAGEMENT IN WASM

---

## Section 12: Linear Memory and Growth

### The Problem

Your WASM module starts with limited memory. As your program runs, it might need more. **How do you grow memory? What are the limits? What happens when you run out?**

### Initial and Maximum Memory

- What's initial memory size?
- What's maximum memory size?
- How do you set these at compile time?
- Can you grow memory at runtime?
- What are the browser limits?

### Memory Growth

- What's `Module.wasmMemory.grow()`?
- How do you grow memory from C?
- What happens to pointers when memory grows?
- Can growth fail?
- How do you handle growth failures?

### Memory Pages

- What's a WASM memory page?
- How big is a page? (64KB)
- Why pages instead of bytes?
- What's the maximum number of pages?
- How does this affect design?

### ALLOW_MEMORY_GROWTH

- What's the `-s ALLOW_MEMORY_GROWTH` flag?
- When should you use it?
- What's the performance impact?
- What changes when memory grows?
- What about pointer invalidation?

### Build It: Memory Growth Tester

Explore memory limits:

**Requirements:**

**Part 1: C Code (memory_growth.c)**

```c
#include <emscripten/emscripten.h>
#include <stdlib.h>
#include <stdio.h>

// Global array to track allocations
#define MAX_ALLOCATIONS 1000
static void* allocations[MAX_ALLOCATIONS];
static int allocation_count = 0;

EMSCRIPTEN_KEEPALIVE
void* allocateChunk(int megabytes) {
    size_t size = megabytes * 1024 * 1024;
    void* ptr = malloc(size);

    if (ptr && allocation_count < MAX_ALLOCATIONS) {
        allocations[allocation_count++] = ptr;
        printf("Allocated %d MB at %p\n", megabytes, ptr);

        // Fill with pattern to ensure actual allocation
        char* bytes = (char*)ptr;
        for (size_t i = 0; i < size; i += 4096) {
            bytes[i] = (char)i;
        }
    } else {
        printf("Allocation failed!\n");
    }

    return ptr;
}

EMSCRIPTEN_KEEPALIVE
void freeAllChunks() {
    for (int i = 0; i < allocation_count; i++) {
        free(allocations[i]);
    }
    allocation_count = 0;
    printf("Freed all allocations\n");
}

EMSCRIPTEN_KEEPALIVE
int getAllocationCount() {
    return allocation_count;
}

// Test memory pressure
EMSCRIPTEN_KEEPALIVE
int stressTest(int iterations, int chunkSize) {
    int successCount = 0;

    for (int i = 0; i < iterations; i++) {
        void* ptr = malloc(chunkSize);
        if (ptr) {
            successCount++;
            // Touch memory
            ((char*)ptr)[0] = 1;
            ((char*)ptr)[chunkSize-1] = 1;
            free(ptr);
        } else {
            printf("Stress test failed at iteration %d\n", i);
            break;
        }
    }

    return successCount;
}
```

**Part 2: Compile with Growth Enabled**

```bash
# With memory growth
emcc memory_growth.c -o memory_growth.js \
    -s ALLOW_MEMORY_GROWTH=1 \
    -s INITIAL_MEMORY=16MB \
    -s MAXIMUM_MEMORY=256MB \
    -O3

# Without memory growth (for comparison)
emcc memory_growth.c -o memory_fixed.js \
    -s INITIAL_MEMORY=64MB \
    -O3
```

**Part 3: Memory Monitor**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Memory Growth Test</title>
    <style>
      body {
        font-family: Arial;
        margin: 20px;
      }
      .test {
        margin: 20px 0;
        padding: 15px;
        background: #f0f0f0;
      }
      button {
        margin: 5px;
        padding: 8px 15px;
      }
      .info {
        font-family: monospace;
        background: white;
        padding: 10px;
        margin: 10px 0;
      }
      .warning {
        color: #cc6600;
      }
      .error {
        color: #cc0000;
      }
      .success {
        color: #006600;
      }
    </style>
  </head>
  <body>
    <h1>WASM Memory Growth</h1>

    <div class="test">
      <h3>Current Memory Status</h3>
      <button onclick="updateMemoryInfo()">Refresh</button>
      <div id="memoryInfo" class="info"></div>
    </div>

    <div class="test">
      <h3>Allocate Memory</h3>
      <input type="number" id="allocSize" value="10" min="1" max="100" />
      <span>MB</span>
      <button onclick="allocateMemory()">Allocate</button>
      <button onclick="freeAll()">Free All</button>
      <div id="allocResult" class="info"></div>
    </div>

    <div class="test">
      <h3>Stress Test</h3>
      <button onclick="runStressTest()">Run Stress Test</button>
      <div id="stressResult" class="info"></div>
    </div>

    <div class="test">
      <h3>Memory Growth Test</h3>
      <button onclick="testGrowth()">Test Memory Growth</button>
      <div id="growthResult" class="info"></div>
    </div>

    <script src="memory_growth.js"></script>
    <script>
      let wasmModule;

      Module.onRuntimeInitialized = function () {
        wasmModule = Module;
        updateMemoryInfo();
      };

      function updateMemoryInfo() {
        const buffer = wasmModule.HEAP8.buffer;
        const pages = buffer.byteLength / 65536;
        const mb = buffer.byteLength / (1024 * 1024);
        const allocCount = wasmModule._getAllocationCount();

        const info = `
Memory Buffer: ${buffer.byteLength} bytes
Memory Size: ${mb.toFixed(2)} MB
Memory Pages: ${pages}
Active Allocations: ${allocCount}
Growth Enabled: ${wasmModule.wasmMemory ? "Yes" : "No"}
            `.trim();

        document.getElementById("memoryInfo").textContent = info;
      }

      function allocateMemory() {
        const size = parseInt(document.getElementById("allocSize").value);

        const beforeMB = wasmModule.HEAP8.buffer.byteLength / (1024 * 1024);

        try {
          const ptr = wasmModule._allocateChunk(size);

          const afterMB = wasmModule.HEAP8.buffer.byteLength / (1024 * 1024);
          const grewBy = afterMB - beforeMB;

          let result = ptr ? `✓ Allocated ${size} MB` : `✗ Allocation failed`;

          if (grewBy > 0) {
            result += `\n✓ Memory grew by ${grewBy.toFixed(2)} MB`;
          }

          document.getElementById(
            "allocResult"
          ).innerHTML = `<pre class="success">${result}</pre>`;

          updateMemoryInfo();
        } catch (error) {
          document.getElementById(
            "allocResult"
          ).innerHTML = `<pre class="error">Error: ${error.message}</pre>`;
        }
      }

      function freeAll() {
        wasmModule._freeAllChunks();
        document.getElementById("allocResult").innerHTML =
          '<pre class="success">All memory freed</pre>';
        updateMemoryInfo();
      }

      function runStressTest() {
        const iterations = 1000;
        const chunkSize = 1024 * 1024; // 1 MB chunks

        const start = performance.now();
        const successCount = wasmModule._stressTest(iterations, chunkSize);
        const end = performance.now();

        const result = `
Iterations: ${iterations}
Succeeded: ${successCount}
Failed: ${iterations - successCount}
Time: ${(end - start).toFixed(2)} ms
            `.trim();

        document.getElementById(
          "stressResult"
        ).innerHTML = `<pre>${result}</pre>`;
      }

      function testGrowth() {
        const results = [];
        const startMB = wasmModule.HEAP8.buffer.byteLength / (1024 * 1024);

        results.push(`Starting memory: ${startMB.toFixed(2)} MB`);
        results.push("\nAllocating in 10 MB increments...\n");

        for (let i = 1; i <= 10; i++) {
          try {
            wasmModule._allocateChunk(10);
            const currentMB =
              wasmModule.HEAP8.buffer.byteLength / (1024 * 1024);
            results.push(
              `After ${i * 10} MB: ${currentMB.toFixed(2)} MB total`
            );
          } catch (error) {
            results.push(`Failed at ${i * 10} MB: ${error.message}`);
            break;
          }
        }

        wasmModule._freeAllChunks();
        updateMemoryInfo();

        document.getElementById("growthResult").innerHTML =
          "<pre>" + results.join("\n") + "</pre>";
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Compile with and without `ALLOW_MEMORY_GROWTH` - see the difference
- Try to exceed maximum memory - handle the error
- Allocate and free repeatedly - watch memory behavior
- Test on mobile devices - different limits
- Use browser DevTools memory profiler
- Try very large allocations

### Reflection Questions

1. **Memory Growth:**

   - When should you allow growth?
   - What's the performance impact?
   - How do you handle growth failures?

2. **Memory Limits:**

   - What are practical limits?
   - How do you design for constraints?
   - What about mobile devices?

3. **Pointer Invalidation:**
   - What happens to pointers when memory grows?
   - How do you avoid dangling pointers?
   - What patterns are safe?

---

## Section 13: Strings in WASM

### The Problem

C strings are null-terminated char arrays. JavaScript strings are UTF-16. **How do you convert between them? What about memory management? What about Unicode?**

### C Strings in WASM

- How are C strings stored in linear memory?
- What's the encoding? (UTF-8)
- How do you pass a C string to JavaScript?
- How does JavaScript know where the string ends?
- What about the null terminator?

### String Conversion Functions

- What's `UTF8ToString`?
- What's `stringToUTF8`?
- What's `lengthBytesUTF8`?
- What's `allocateUTF8`?
- When should you use each?

### String Memory Management

- Who allocates memory for strings?
- Who frees them?
- What if you forget to free?
- Can you return stack-allocated strings?
- What about string literals?

### Unicode and Encoding

- How does WASM handle Unicode?
- What about multi-byte characters?
- What's the difference between character count and byte count?
- How do you handle emojis?
- What about different encodings?

### Build It: String Processing Library

Create comprehensive string handling:

**Requirements:**

**Part 1: C String Functions (strings.c)**

```c
#include <emscripten/emscripten.h>
#include <stdlib.h>
#include <string.h>
#include <ctype.h>

// Return a string (caller must free)
EMSCRIPTEN_KEEPALIVE
char* reverseString(const char* input) {
    int len = strlen(input);
    char* result = (char*)malloc(len + 1);

    for (int i = 0; i < len; i++) {
        result[i] = input[len - 1 - i];
    }
    result[len] = '\0';

    return result;
}

// Modify string in place
EMSCRIPTEN_KEEPALIVE
void toUpperCase(char* str) {
    for (int i = 0; str[i]; i++) {
        str[i] = toupper(str[i]);
    }
}

// Count characters (not bytes!)
EMSCRIPTEN_KEEPALIVE
int countChars(const char* str) {
    int count = 0;
    while (*str) {
        // Skip continuation bytes in UTF-8
        if ((*str & 0xC0) != 0x80) {
            count++;
        }
        str++;
    }
    return count;
}

// String concatenation
EMSCRIPTEN_KEEPALIVE
char* concatStrings(const char* str1, const char* str2) {
    int len1 = strlen(str1);
    int len2 = strlen(str2);
    char* result = (char*)malloc(len1 + len2 + 1);

    strcpy(result, str1);
    strcat(result, str2);

    return result;
}

// Find substring
EMSCRIPTEN_KEEPALIVE
int findSubstring(const char* haystack, const char* needle) {
    const char* pos = strstr(haystack, needle);
    return pos ? (pos - haystack) : -1;
}

// Replace all occurrences
EMSCRIPTEN_KEEPALIVE
char* replaceAll(const char* str, const char* find, const char* replace) {
    int count = 0;
    const char* temp = str;
    int findLen = strlen(find);
    int replaceLen = strlen(replace);

    // Count occurrences
    while ((temp = strstr(temp, find))) {
        count++;
        temp += findLen;
    }

    if (count == 0) {
        return strdup(str);
    }

    // Allocate result
    int resultLen = strlen(str) + count * (replaceLen - findLen);
    char* result = (char*)malloc(resultLen + 1);
    char* dest = result;

    // Replace
    temp = str;
    while (*temp) {
        if (strncmp(temp, find, findLen) == 0) {
            strcpy(dest, replace);
            dest += replaceLen;
            temp += findLen;
        } else {
            *dest++ = *temp++;
        }
    }
    *dest = '\0';

    return result;
}

// Split string (returns first part, modifies input)
EMSCRIPTEN_KEEPALIVE
char* splitString(char* str, const char* delimiter) {
    return strtok(str, delimiter);
}

// Get next token (call after splitString)
EMSCRIPTEN_KEEPALIVE
char* nextToken(const char* delimiter) {
    return strtok(NULL, delimiter);
}
```

**Part 2: JavaScript String Handler**

```javascript
// string-handler.js
class WasmStringHandler {
  constructor(module) {
    this.Module = module;
  }

  // Safe string reverse
  reverse(str) {
    // Allocate input
    const inputPtr = this.Module.allocateUTF8(str);

    // Call WASM
    const resultPtr = this.Module._reverseString(inputPtr);

    // Read result
    const result = this.Module.UTF8ToString(resultPtr);

    // Free both
    this.Module._free(inputPtr);
    this.Module._free(resultPtr);

    return result;
  }

  // In-place uppercase
  toUpperCase(str) {
    // Need mutable memory
    const len = this.Module.lengthBytesUTF8(str) + 1;
    const ptr = this.Module._malloc(len);
    this.Module.stringToUTF8(str, ptr, len);

    // Modify
    this.Module._toUpperCase(ptr);

    // Read back
    const result = this.Module.UTF8ToString(ptr);

    // Free
    this.Module._free(ptr);

    return result;
  }

  // Count characters (handles Unicode)
  countChars(str) {
    const ptr = this.Module.allocateUTF8(str);
    const count = this.Module._countChars(ptr);
    this.Module._free(ptr);
    return count;
  }

  // Concatenate
  concat(str1, str2) {
    const ptr1 = this.Module.allocateUTF8(str1);
    const ptr2 = this.Module.allocateUTF8(str2);

    const resultPtr = this.Module._concatStrings(ptr1, ptr2);
    const result = this.Module.UTF8ToString(resultPtr);

    this.Module._free(ptr1);
    this.Module._free(ptr2);
    this.Module._free(resultPtr);

    return result;
  }

  // Find substring
  find(haystack, needle) {
    const haystackPtr = this.Module.allocateUTF8(haystack);
    const needlePtr = this.Module.allocateUTF8(needle);

    const index = this.Module._findSubstring(haystackPtr, needlePtr);

    this.Module._free(haystackPtr);
    this.Module._free(needlePtr);

    return index;
  }

  // Replace all
  replaceAll(str, find, replace) {
    const strPtr = this.Module.allocateUTF8(str);
    const findPtr = this.Module.allocateUTF8(find);
    const replacePtr = this.Module.allocateUTF8(replace);

    const resultPtr = this.Module._replaceAll(strPtr, findPtr, replacePtr);
    const result = this.Module.UTF8ToString(resultPtr);

    this.Module._free(strPtr);
    this.Module._free(findPtr);
    this.Module._free(replacePtr);
    this.Module._free(resultPtr);

    return result;
  }

  // Split string
  split(str, delimiter) {
    const len = this.Module.lengthBytesUTF8(str) + 1;
    const strPtr = this.Module._malloc(len);
    this.Module.stringToUTF8(str, strPtr, len);

    const delimPtr = this.Module.allocateUTF8(delimiter);

    const tokens = [];

    // Get first token
    let tokenPtr = this.Module._splitString(strPtr, delimPtr);
    while (tokenPtr !== 0) {
      tokens.push(this.Module.UTF8ToString(tokenPtr));
      tokenPtr = this.Module._nextToken(delimPtr);
    }

    this.Module._free(strPtr);
    this.Module._free(delimPtr);

    return tokens;
  }
}
```

**Part 3: Test Unicode**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>String Handling Test</title>
    <style>
      body {
        font-family: Arial;
        margin: 20px;
      }
      .test {
        margin: 20px 0;
        padding: 10px;
        background: #f0f0f0;
      }
      input {
        padding: 5px;
        width: 300px;
      }
      button {
        margin: 5px;
        padding: 5px 10px;
      }
      .result {
        background: white;
        padding: 10px;
        margin: 10px 0;
        font-family: monospace;
      }
    </style>
  </head>
  <body>
    <h1>WASM String Handling</h1>

    <div class="test">
      <h3>Reverse String</h3>
      <input type="text" id="reverseInput" value="Hello World" />
      <button onclick="testReverse()">Reverse</button>
      <div id="reverseResult" class="result"></div>
    </div>

    <div class="test">
      <h3>Unicode Test</h3>
      <input type="text" id="unicodeInput" value="Hello 世界 🌍" />
      <button onclick="testUnicode()">Test Unicode</button>
      <div id="unicodeResult" class="result"></div>
    </div>

    <div class="test">
      <h3>String Operations</h3>
      <input type="text" id="opsInput" value="The quick brown fox" />
      <button onclick="testOperations()">Run All Operations</button>
      <div id="opsResult" class="result"></div>
    </div>

    <div class="test">
      <h3>Replace All</h3>
      <input type="text" id="replaceInput" value="foo bar foo baz foo" />
      <button onclick="testReplace()">Replace 'foo' with 'REPLACED'</button>
      <div id="replaceResult" class="result"></div>
    </div>

    <div class="test">
      <h3>Split String</h3>
      <input type="text" id="splitInput" value="apple,banana,cherry,date" />
      <button onclick="testSplit()">Split by comma</button>
      <div id="splitResult" class="result"></div>
    </div>

    <script src="strings.js"></script>
    <script src="string-handler.js"></script>
    <script>
      let handler;

      Module.onRuntimeInitialized = function () {
        handler = new WasmStringHandler(Module);
      };

      function testReverse() {
        const input = document.getElementById("reverseInput").value;
        const result = handler.reverse(input);
        document.getElementById(
          "reverseResult"
        ).textContent = `Input: "${input}"\nReversed: "${result}"`;
      }

      function testUnicode() {
        const input = document.getElementById("unicodeInput").value;

        const reversed = handler.reverse(input);
        const charCount = handler.countChars(input);
        const byteLength = new TextEncoder().encode(input).length;

        const result = `
Input: "${input}"
Reversed: "${reversed}"
Character count: ${charCount}
Byte length: ${byteLength}
Note: Emojis and multibyte chars are counted correctly!
            `.trim();

        document.getElementById("unicodeResult").textContent = result;
      }

      function testOperations() {
        const input = document.getElementById("opsInput").value;

        const upper = handler.toUpperCase(input);
        const concat = handler.concat(input, " jumps!");
        const findPos = handler.find(input, "fox");

        const result = `
Original: "${input}"
Uppercase: "${upper}"
Concatenated: "${concat}"
Position of 'fox': ${findPos}
            `.trim();

        document.getElementById("opsResult").textContent = result;
      }

      function testReplace() {
        const input = document.getElementById("replaceInput").value;
        const result = handler.replaceAll(input, "foo", "REPLACED");

        document.getElementById(
          "replaceResult"
        ).textContent = `Before: "${input}"\nAfter: "${result}"`;
      }

      function testSplit() {
        const input = document.getElementById("splitInput").value;
        const parts = handler.split(input, ",");

        const result = `
Original: "${input}"
Split into ${parts.length} parts:
${parts.map((p, i) => `  [${i}] "${p}"`).join("\n")}
            `.trim();

        document.getElementById("splitResult").textContent = result;
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Test with very long strings
- Test with different Unicode characters (emoji, Chinese, Arabic)
- Measure performance vs JavaScript string operations
- Try to break memory management - cause leaks
- Test with null characters in strings
- Compare byte length vs character length

### Reflection Questions

1. **String Encoding:**

   - Why UTF-8 for WASM?
   - How does it affect performance?
   - What about other encodings?

2. **Memory Management:**

   - Who should allocate string memory?
   - How do you avoid leaks?
   - What about string constants?

3. **Performance:**
   - When is WASM string processing faster?
   - What's the cost of conversion?
   - How do you minimize copying?

---

## Section 14: Arrays and Pointers Across the Boundary

### The Problem

You want to pass a large array between JavaScript and WASM. **Should you copy it? Share memory? Who owns it? How do you handle cleanup?**

### Sharing vs Copying

- When should you copy data?
- When should you share memory?
- What's the performance difference?
- What about TypedArrays?
- How does ownership work?

### TypedArray Views

- What's a TypedArray?
- How do you create views into WASM memory?
- What happens if memory grows?
- How do you handle view invalidation?
- What about concurrent access?

### Array Lifetime

- Who allocates array memory?
- Who frees it?
- What if JavaScript holds a reference?
- What if WASM frees while JS uses it?
- How do you coordinate lifetime?

### Large Data Transfer

- How do you efficiently transfer large arrays?
- Should you process in chunks?
- What about streaming data?
- How do you avoid blocking?
- What about workers?

### Build It: Efficient Array Processing

Handle arrays efficiently:

**Requirements:**

**Part 1: C Array Functions (arrays.c)**

```c
#include <emscripten/emscripten.h>
#include <stdlib.h>
#include <string.h>

// === Array Creation ===

EMSCRIPTEN_KEEPALIVE
int* createIntArray(int size) {
    return (int*)calloc(size, sizeof(int));
}

EMSCRIPTEN_KEEPALIVE
float* createFloatArray(int size) {
    return (float*)calloc(size, sizeof(float));
}

EMSCRIPTEN_KEEPALIVE
void freeArray(void* arr) {
    free(arr);
}

// === Array Operations ===

EMSCRIPTEN_KEEPALIVE
void fillSequence(int* arr, int size, int start) {
    for (int i = 0; i < size; i++) {
        arr[i] = start + i;
    }
}

EMSCRIPTEN_KEEPALIVE
void multiplyArray(float* arr, int size, float multiplier) {
    for (int i = 0; i < size; i++) {
        arr[i] *= multiplier;
    }
}

EMSCRIPTEN_KEEPALIVE
int sumIntArray(const int* arr, int size) {
    int sum = 0;
    for (int i = 0; i < size; i++) {
        sum += arr[i];
    }
    return sum;
}

EMSCRIPTEN_KEEPALIVE
float sumFloatArray(const float* arr, int size) {
    float sum = 0.0f;
    for (int i = 0; i < size; i++) {
        sum += arr[i];
    }
    return sum;
}

// === Array Transformations ===

EMSCRIPTEN_KEEPALIVE
void reverseArray(int* arr, int size) {
    for (int i = 0; i < size / 2; i++) {
        int temp = arr[i];
        arr[i] = arr[size - 1 - i];
        arr[size - 1 - i] = temp;
    }
}

EMSCRIPTEN_KEEPALIVE
void sortArray(int* arr, int size) {
    // Simple bubble sort
    for (int i = 0; i < size - 1; i++) {
        for (int j = 0; j < size - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

// === Complex Operations ===

EMSCRIPTEN_KEEPALIVE
void mapArray(float* arr, int size, float (*func)(float)) {
    for (int i = 0; i < size; i++) {
        arr[i] = func(arr[i]);
    }
}

EMSCRIPTEN_KEEPALIVE
void filterArray(int* source, int sourceSize, int* dest, int* destSize, int threshold) {
    int count = 0;
    for (int i = 0; i < sourceSize; i++) {
        if (source[i] >= threshold) {
            dest[count++] = source[i];
        }
    }
    *destSize = count;
}

// === Chunked Processing ===

typedef struct {
    float* data;
    int size;
    int processed;
} ChunkProcessor;

EMSCRIPTEN_KEEPALIVE
ChunkProcessor* createProcessor(int totalSize) {
    ChunkProcessor* proc = (ChunkProcessor*)malloc(sizeof(ChunkProcessor));
    proc->data = (float*)malloc(totalSize * sizeof(float));
    proc->size = totalSize;
    proc->processed = 0;
    return proc;
}

EMSCRIPTEN_KEEPALIVE
int processChunk(ChunkProcessor* proc, int chunkSize) {
    int remaining = proc->size - proc->processed;
    int toProcess = (chunkSize < remaining) ? chunkSize : remaining;

    for (int i = 0; i < toProcess; i++) {
        int idx = proc->processed + i;
        proc->data[idx] = proc->data[idx] * 2.0f + 1.0f;
    }

    proc->processed += toProcess;
    return proc->processed;
}

EMSCRIPTEN_KEEPALIVE
void freeProcessor(ChunkProcessor* proc) {
    free(proc->data);
    free(proc);
}
```

**Part 2: JavaScript Array Manager**

```javascript
// array-manager.js
class WasmArrayManager {
  constructor(module) {
    this.Module = module;
  }

  // === Shared Memory Approach ===

  createSharedInt32Array(size) {
    // Allocate in WASM
    const ptr = this.Module._createIntArray(size);

    // Create TypedArray view
    const view = new Int32Array(this.Module.HEAP32.buffer, ptr, size);

    return {
      ptr,
      view,
      size,
      free: () => this.Module._freeArray(ptr),
    };
  }

  createSharedFloat32Array(size) {
    const ptr = this.Module._createFloatArray(size);
    const view = new Float32Array(this.Module.HEAPF32.buffer, ptr, size);

    return {
      ptr,
      view,
      size,
      free: () => this.Module._freeArray(ptr),
    };
  }

  // === Copy Approach ===

  copyToWasm(jsArray) {
    const size = jsArray.length;
    const ptr = this.Module._createIntArray(size);

    // Copy data
    this.Module.HEAP32.set(jsArray, ptr >> 2);

    return {ptr, size};
  }

  copyFromWasm(ptr, size) {
    // Create copy
    return new Int32Array(this.Module.HEAP32.buffer, ptr, size).slice();
  }

  // === Operations ===

  processInWasm(jsArray, operation) {
    const {ptr, size} = this.copyToWasm(jsArray);

    // Call WASM operation
    switch (operation) {
      case "reverse":
        this.Module._reverseArray(ptr, size);
        break;
      case "sort":
        this.Module._sortArray(ptr, size);
        break;
    }

    // Copy back
    const result = this.copyFromWasm(ptr, size);

    // Free
    this.Module._freeArray(ptr);

    return result;
  }

  // === Chunked Processing ===

  async processLargeArray(data, chunkSize = 1000, callback) {
    const totalSize = data.length;
    const proc = this.Module._createProcessor(totalSize);

    // Copy data to processor
    const procDataPtr = this.Module.HEAP32[proc >> 2];
    this.Module.HEAPF32.set(data, procDataPtr >> 2);

    // Process in chunks
    let processed = 0;
    while (processed < totalSize) {
      processed = this.Module._processChunk(proc, chunkSize);

      if (callback) {
        callback(processed, totalSize);
      }

      // Yield to browser
      await new Promise((resolve) => setTimeout(resolve, 0));
    }

    // Copy result back
    const result = new Float32Array(
      this.Module.HEAPF32.buffer,
      procDataPtr,
      totalSize
    ).slice();

    this.Module._freeProcessor(proc);

    return result;
  }

  // === Benchmarks ===

  benchmarkCopyVsShare(size) {
    // Create test data
    const jsArray = new Int32Array(size);
    for (let i = 0; i < size; i++) {
      jsArray[i] = i;
    }

    // Test 1: Copy approach
    const copyStart = performance.now();
    const {ptr: copyPtr, size: copySize} = this.copyToWasm(jsArray);
    this.Module._sumIntArray(copyPtr, copySize);
    const result1 = this.copyFromWasm(copyPtr, copySize);
    this.Module._freeArray(copyPtr);
    const copyTime = performance.now() - copyStart;

    // Test 2: Shared approach
    const shareStart = performance.now();
    const shared = this.createSharedInt32Array(size);
    shared.view.set(jsArray);
    this.Module._sumIntArray(shared.ptr, size);
    const result2 = shared.view.slice();
    shared.free();
    const shareTime = performance.now() - shareStart;

    return {
      copyTime,
      shareTime,
      difference: (((copyTime - shareTime) / shareTime) * 100).toFixed(2) + "%",
    };
  }
}
```

**Part 3: Test Page**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Array Processing</title>
    <style>
      body {
        font-family: monospace;
        margin: 20px;
      }
      .test {
        margin: 20px 0;
        padding: 10px;
        background: #f0f0f0;
      }
      button {
        margin: 5px;
        padding: 5px 10px;
      }
      .progress {
        width: 100%;
        height: 20px;
        background: #ddd;
        margin: 10px 0;
      }
      .progress-bar {
        height: 100%;
        background: #4caf50;
        transition: width 0.3s;
      }
      pre {
        background: white;
        padding: 10px;
      }
    </style>
  </head>
  <body>
    <h1>WASM Array Processing</h1>

    <div class="test">
      <h3>Shared Memory vs Copy</h3>
      <button onclick="testSharedVsCopy()">Run Benchmark</button>
      <pre id="benchResult"></pre>
    </div>

    <div class="test">
      <h3>Array Operations</h3>
      <button onclick="testOperations()">Test Operations</button>
      <pre id="opsResult"></pre>
    </div>

    <div class="test">
      <h3>Chunked Processing (Large Array)</h3>
      <button onclick="testChunked()">Process 1 Million Items</button>
      <div class="progress">
        <div id="progressBar" class="progress-bar" style="width: 0%"></div>
      </div>
      <pre id="chunkedResult"></pre>
    </div>

    <script src="arrays.js"></script>
    <script src="array-manager.js"></script>
    <script>
      let manager;

      Module.onRuntimeInitialized = function () {
        manager = new WasmArrayManager(Module);
      };

      function testSharedVsCopy() {
        const sizes = [1000, 10000, 100000];
        const results = ["Array Size | Copy Time | Shared Time | Difference"];
        results.push("-----------|-----------|-------------|------------");

        sizes.forEach((size) => {
          const bench = manager.benchmarkCopyVsShare(size);
          results.push(
            `${size.toLocaleString().padEnd(10)} | ` +
              `${bench.copyTime.toFixed(2)}ms | ` +
              `${bench.shareTime.toFixed(2)}ms | ` +
              `${bench.difference}`
          );
        });

        document.getElementById("benchResult").textContent = results.join("\n");
      }

      function testOperations() {
        const testArray = [5, 2, 8, 1, 9, 3, 7, 4, 6];
        const results = [];

        results.push(`Original: [${testArray}]`);

        // Reverse
        const reversed = manager.processInWasm(testArray, "reverse");
        results.push(`Reversed: [${reversed}]`);

        // Sort
        const sorted = manager.processInWasm(testArray, "sort");
        results.push(`Sorted: [${sorted}]`);

        document.getElementById("opsResult").textContent = results.join("\n");
      }

      async function testChunked() {
        const size = 1000000;
        const data = new Float32Array(size);
        for (let i = 0; i < size; i++) {
          data[i] = Math.random();
        }

        const progressBar = document.getElementById("progressBar");
        const resultDiv = document.getElementById("chunkedResult");

        resultDiv.textContent = "Processing...";

        const start = performance.now();

        const result = await manager.processLargeArray(
          data,
          10000,
          (processed, total) => {
            const percent = ((processed / total) * 100).toFixed(1);
            progressBar.style.width = percent + "%";
          }
        );

        const time = performance.now() - start;

        resultDiv.textContent = `
Processed ${size.toLocaleString()} items
Time: ${time.toFixed(2)}ms
Items/sec: ${((size / time) * 1000).toFixed(0).toLocaleString()}
Sample result: [${result.slice(0, 5).map((n) => n.toFixed(2))}...]
            `.trim();
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Test with very large arrays (10+ million items)
- Compare performance of copy vs shared memory
- Test memory growth during array operations
- Try concurrent array processing
- Measure overhead of TypedArray views
- Test on mobile devices

### Reflection Questions

1. **Memory Sharing:**

   - When should you share vs copy?
   - What are the trade-offs?
   - How do you handle view invalidation?

2. **Performance:**

   - What's the cost of copying?
   - When is sharing worth it?
   - How do you optimize large transfers?

3. **Design:**
   - How do you design array APIs?
   - What about ownership?
   - How do you prevent bugs?

---

## Section 15: Debugging Memory Issues

### The Problem

Your WASM program crashes. Memory is corrupted. Pointers are invalid. **How do you debug across the JavaScript/WASM boundary?**

### Common Memory Bugs

- Buffer overflows
- Use-after-free
- Memory leaks
- Null pointer dereferences
- Double free
- Stack overflow

### Browser DevTools

- How do you use Chrome DevTools with WASM?
- What's the Memory profiler?
- How do you see WASM memory?
- Can you set breakpoints in WASM?
- How do you inspect variables?

### Source Maps

- What are source maps?
- How do you generate them?
- How do you use them in DevTools?
- Can you debug C code in the browser?
- What about optimized builds?

### Sanitizers

- What's AddressSanitizer for WASM?
- How do you enable it?
- What bugs can it catch?
- What's the performance cost?
- Should you use it in production?

### Build It: Memory Debugging Tools

Create tools to catch memory bugs:

**Requirements:**

**Part 1: Buggy Code for Testing (bugs.c)**

```c
#include <emscripten/emscripten.h>
#include <stdlib.h>
#include <string.h>

// Bug 1: Buffer overflow
EMSCRIPTEN_KEEPALIVE
void bufferOverflow() {
    int arr[10];
    for (int i = 0; i <= 10; i++) {  // Off by one!
        arr[i] = i;
    }
}

// Bug 2: Use after free
EMSCRIPTEN_KEEPALIVE
void useAfterFree() {
    int* ptr = (int*)malloc(sizeof(int));
    *ptr = 42;
    free(ptr);
    *ptr = 100;  // Bug!
}

// Bug 3: Memory leak
EMSCRIPTEN_KEEPALIVE
void memoryLeak() {
    int* ptr = (int*)malloc(1000 * sizeof(int));
    // Never freed!
}

// Bug 4: Double free
EMSCRIPTEN_KEEPALIVE
void doubleFree() {
    int* ptr = (int*)malloc(sizeof(int));
    free(ptr);
    free(ptr);  // Bug!
}

// Bug 5: Null pointer dereference
EMSCRIPTEN_KEEPALIVE
void nullPointerDeref() {
    int* ptr = NULL;
    *ptr = 42;  // Bug!
}

// Bug 6: Stack overflow
EMSCRIPTEN_KEEPALIVE
int stackOverflow(int n) {
    if (n == 0) return 0;
    return stackOverflow(n - 1) + n;  // No base case check!
}

// Correct versions for comparison
EMSCRIPTEN_KEEPALIVE
void correctArrayAccess() {
    int arr[10];
    for (int i = 0; i < 10; i++) {  // Correct!
        arr[i] = i;
    }
}

EMSCRIPTEN_KEEPALIVE
void correctMemoryUse() {
    int* ptr = (int*)malloc(sizeof(int));
    if (ptr) {
        *ptr = 42;
        free(ptr);
        ptr = NULL;  // Good practice
    }
}
```

**Part 2: Compile with Debugging**

```bash
# With source maps
emcc bugs.c -o bugs_debug.js -g4

# With AddressSanitizer
emcc bugs.c -o bugs_asan.js \
    -fsanitize=address \
    -g

# Production build for comparison
emcc bugs.c -o bugs_prod.js -O3
```

**Part 3: Memory Checker**

```javascript
// memory-checker.js
class MemoryChecker {
  constructor(module) {
    this.Module = module;
    this.allocations = new Map();
    this.freed = new Set();

    // Wrap malloc and free
    this.originalMalloc = this.Module._malloc;
    this.originalFree = this.Module._free;

    this.setupTracking();
  }

  setupTracking() {
    const self = this;

    // Track allocations
    this.Module._malloc = function (size) {
      const ptr = self.originalMalloc.call(this, size);
      if (ptr) {
        self.allocations.set(ptr, {
          size,
          stack: new Error().stack,
          timestamp: Date.now(),
        });
        console.log(`[MALLOC] ${ptr} (${size} bytes)`);
      }
      return ptr;
    };

    // Track frees
    this.Module._free = function (ptr) {
      if (self.freed.has(ptr)) {
        console.error(`[DOUBLE FREE] ${ptr}`);
        console.trace();
      }

      if (!self.allocations.has(ptr)) {
        console.warn(`[FREE UNKNOWN] ${ptr}`);
      }

      self.originalFree.call(this, ptr);
      self.allocations.delete(ptr);
      self.freed.add(ptr);
      console.log(`[FREE] ${ptr}`);
    };
  }

  getLeaks() {
    return Array.from(this.allocations.entries()).map(([ptr, info]) => ({
      ptr,
      ...info,
      age: Date.now() - info.timestamp,
    }));
  }

  printLeaks() {
    const leaks = this.getLeaks();
    if (leaks.length === 0) {
      console.log("✓ No memory leaks detected");
    } else {
      console.error(`✗ ${leaks.length} memory leaks detected:`);
      leaks.forEach((leak) => {
        console.error(`  ${leak.ptr}: ${leak.size} bytes, age: ${leak.age}ms`);
      });
    }
  }

  reset() {
    this.allocations.clear();
    this.freed.clear();
  }
}
```

**Part 4: Test Page**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Memory Debugging</title>
    <style>
      body {
        font-family: Arial;
        margin: 20px;
      }
      .test {
        margin: 20px 0;
        padding: 10px;
        background: #f0f0f0;
      }
      button {
        margin: 5px;
        padding: 5px 10px;
      }
      .error {
        color: #cc0000;
      }
      .success {
        color: #006600;
      }
      pre {
        background: white;
        padding: 10px;
      }
    </style>
  </head>
  <body>
    <h1>Memory Debugging Tools</h1>

    <p>Open DevTools Console (F12) to see detailed output</p>

    <div class="test">
      <h3>Test Memory Bugs</h3>
      <button onclick="testBug('bufferOverflow')">Buffer Overflow</button>
      <button onclick="testBug('useAfterFree')">Use After Free</button>
      <button onclick="testBug('memoryLeak')">Memory Leak</button>
      <button onclick="testBug('doubleFree')">Double Free</button>
      <button onclick="testBug('nullPointerDeref')">Null Pointer</button>
      <div id="bugResult"></div>
    </div>

    <div class="test">
      <h3>Memory Leak Detection</h3>
      <button onclick="createLeaks()">Create 10 Leaks</button>
      <button onclick="checkLeaks()">Check for Leaks</button>
      <button onclick="resetChecker()">Reset</button>
      <pre id="leakResult"></pre>
    </div>

    <div class="test">
      <h3>Memory Profiling</h3>
      <button onclick="profileMemory()">Profile Memory Usage</button>
      <pre id="profileResult"></pre>
    </div>

    <script src="bugs_debug.js"></script>
    <script src="memory-checker.js"></script>
    <script>
      let checker;

      Module.onRuntimeInitialized = function () {
        checker = new MemoryChecker(Module);
        console.log("Memory checker initialized");
      };

      function testBug(bugName) {
        console.log(`\n=== Testing ${bugName} ===`);

        try {
          Module["_" + bugName]();
          document.getElementById(
            "bugResult"
          ).innerHTML = `<p class="success">Function executed (check console for issues)</p>`;
        } catch (error) {
          document.getElementById(
            "bugResult"
          ).innerHTML = `<p class="error">Error: ${error.message}</p>`;
          console.error(error);
        }
      }

      function createLeaks() {
        for (let i = 0; i < 10; i++) {
          Module._memoryLeak();
        }
        console.log("Created 10 memory leaks");
      }

      function checkLeaks() {
        checker.printLeaks();
        const leaks = checker.getLeaks();

        document.getElementById("leakResult").textContent =
          leaks.length === 0
            ? "✓ No leaks detected"
            : `✗ Found ${leaks.length} leaks:\n` +
              leaks.map((l) => `  ${l.ptr}: ${l.size} bytes`).join("\n");
      }

      function resetChecker() {
        checker.reset();
        console.log("Checker reset");
        document.getElementById("leakResult").textContent = "Reset complete";
      }

      function profileMemory() {
        const before = Module.HEAP8.buffer.byteLength;

        // Allocate some memory
        const ptrs = [];
        for (let i = 0; i < 100; i++) {
          ptrs.push(Module._malloc(1024 * 1024)); // 1 MB each
        }

        const after = Module.HEAP8.buffer.byteLength;

        // Free memory
        ptrs.forEach((ptr) => Module._free(ptr));

        const result = `
Before: ${(before / 1024 / 1024).toFixed(2)} MB
After allocation: ${(after / 1024 / 1024).toFixed(2)} MB
Growth: ${((after - before) / 1024 / 1024).toFixed(2)} MB
Allocations: 100 x 1 MB
            `.trim();

        document.getElementById("profileResult").textContent = result;
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Use Chrome DevTools Memory profiler
- Take heap snapshots before/after operations
- Try debugging with source maps
- Compile with AddressSanitizer and test
- Create complex memory bugs and debug them
- Profile memory usage over time

### Reflection Questions

1. **Debugging:**

   - How do you debug WASM effectively?
   - What tools are available?
   - How is it different from native debugging?

2. **Memory Safety:**

   - How do you prevent memory bugs?
   - What patterns are safe?
   - When should you use sanitizers?

3. **Production:**
   - How do you handle bugs in production?
   - What logging should you add?
   - How do you monitor memory usage?

---

# 🟠 PART 5: BUILDING REAL APPLICATIONS

---

## Section 16: Image Processing with WASM

### The Problem

JavaScript is slow for pixel manipulation. You need to process images in real-time. **WASM can process images 10-100x faster than JavaScript.**

### Image Data

- How are images represented in browsers?
- What's ImageData?
- What's the format? (RGBA)
- How do you get pixel data?
- How do you modify pixels?

### Processing Images

- How do you pass image data to WASM?
- What operations are good for WASM?
- How do you handle different formats?
- What about color spaces?
- How do you optimize for performance?

### Common Filters

- Grayscale
- Blur
- Sharpen
- Edge detection
- Color adjustment
- Convolution

### Build It: Image Filter Library

Create fast image processing:

**Requirements:**

**Part 1: C Image Processing (image.c)**

```c
#include <emscripten/emscripten.h>
#include <math.h>
#include <stdlib.h>

// Grayscale filter
EMSCRIPTEN_KEEPALIVE
void grayscale(unsigned char* data, int width, int height) {
    int size = width * height * 4;

    for (int i = 0; i < size; i += 4) {
        int r = data[i];
        int g = data[i + 1];
        int b = data[i + 2];

        // Use luminosity method
        int gray = (int)(0.299 * r + 0.587 * g + 0.114 * b);

        data[i] = gray;
        data[i + 1] = gray;
        data[i + 2] = gray;
        // Alpha (i + 3) unchanged
    }
}

// Invert colors
EMSCRIPTEN_KEEPALIVE
void invert(unsigned char* data, int width, int height) {
    int size = width * height * 4;

    for (int i = 0; i < size; i += 4) {
        data[i] = 255 - data[i];       // R
        data[i + 1] = 255 - data[i + 1]; // G
        data[i + 2] = 255 - data[i + 2]; // B
    }
}

// Brightness adjustment
EMSCRIPTEN_KEEPALIVE
void brightness(unsigned char* data, int width, int height, int adjustment) {
    int size = width * height * 4;

    for (int i = 0; i < size; i += 4) {
        data[i] = fmin(255, fmax(0, data[i] + adjustment));
        data[i + 1] = fmin(255, fmax(0, data[i + 1] + adjustment));
        data[i + 2] = fmin(255, fmax(0, data[i + 2] + adjustment));
    }
}

// Contrast adjustment
EMSCRIPTEN_KEEPALIVE
void contrast(unsigned char* data, int width, int height, float factor) {
    int size = width * height * 4;

    for (int i = 0; i < size; i += 4) {
        data[i] = fmin(255, fmax(0, ((data[i] - 128) * factor) + 128));
        data[i + 1] = fmin(255, fmax(0, ((data[i + 1] - 128) * factor) + 128));
        data[i + 2] = fmin(255, fmax(0, ((data[i + 2] - 128) * factor) + 128));
    }
}

// Box blur
EMSCRIPTEN_KEEPALIVE
void boxBlur(unsigned char* src, unsigned char* dest, int width, int height, int radius) {
    for (int y = 0; y < height; y++) {
        for (int x = 0; x < width; x++) {
            int r = 0, g = 0, b = 0, count = 0;

            // Sample box
            for (int dy = -radius; dy <= radius; dy++) {
                for (int dx = -radius; dx <= radius; dx++) {
                    int nx = x + dx;
                    int ny = y + dy;

                    if (nx >= 0 && nx < width && ny >= 0 && ny < height) {
                        int idx = (ny * width + nx) * 4;
                        r += src[idx];
                        g += src[idx + 1];
                        b += src[idx + 2];
                        count++;
                    }
                }
            }

            int idx = (y * width + x) * 4;
            dest[idx] = r / count;
            dest[idx + 1] = g / count;
            dest[idx + 2] = b / count;
            dest[idx + 3] = src[idx + 3]; // Copy alpha
        }
    }
}

// Edge detection (Sobel)
EMSCRIPTEN_KEEPALIVE
void edgeDetect(unsigned char* src, unsigned char* dest, int width, int height) {
    int sobelX[3][3] = {{-1, 0, 1}, {-2, 0, 2}, {-1, 0, 1}};
    int sobelY[3][3] = {{-1, -2, -1}, {0, 0, 0}, {1, 2, 1}};

    for (int y = 1; y < height - 1; y++) {
        for (int x = 1; x < width - 1; x++) {
            int gx = 0, gy = 0;

            for (int dy = -1; dy <= 1; dy++) {
                for (int dx = -1; dx <= 1; dx++) {
                    int idx = ((y + dy) * width + (x + dx)) * 4;
                    int gray = (src[idx] + src[idx + 1] + src[idx + 2]) / 3;

                    gx += gray * sobelX[dy + 1][dx + 1];
                    gy += gray * sobelY[dy + 1][dx + 1];
                }
            }

            int magnitude = sqrt(gx * gx + gy * gy);
            magnitude = fmin(255, magnitude);

            int idx = (y * width + x) * 4;
            dest[idx] = magnitude;
            dest[idx + 1] = magnitude;
            dest[idx + 2] = magnitude;
            dest[idx + 3] = 255;
        }
    }
}
```

**Part 2: JavaScript Integration**

```javascript
// image-processor.js
class ImageProcessor {
  constructor(module) {
    this.Module = module;
  }

  async loadImage(src) {
    return new Promise((resolve, reject) => {
      const img = new Image();
      img.crossOrigin = "anonymous";
      img.onload = () => resolve(img);
      img.onerror = reject;
      img.src = src;
    });
  }

  imageToData(img) {
    const canvas = document.createElement("canvas");
    canvas.width = img.width;
    canvas.height = img.height;
    const ctx = canvas.getContext("2d");
    ctx.drawImage(img, 0, 0);
    return ctx.getImageData(0, 0, canvas.width, canvas.height);
  }

  dataToCanvas(imageData, canvas) {
    canvas.width = imageData.width;
    canvas.height = imageData.height;
    const ctx = canvas.getContext("2d");
    ctx.putImageData(imageData, 0, 0);
  }

  processImage(imageData, filter, ...args) {
    const {width, height, data} = imageData;
    const size = data.length;

    // Allocate WASM memory
    const ptr = this.Module._malloc(size);

    // Copy image data
    this.Module.HEAP8.set(data, ptr);

    // Apply filter
    const start = performance.now();

    switch (filter) {
      case "grayscale":
        this.Module._grayscale(ptr, width, height);
        break;
      case "invert":
        this.Module._invert(ptr, width, height);
        break;
      case "brightness":
        this.Module._brightness(ptr, width, height, args[0] || 0);
        break;
      case "contrast":
        this.Module._contrast(ptr, width, height, args[0] || 1.0);
        break;
      case "blur":
        const destPtr = this.Module._malloc(size);
        this.Module._boxBlur(ptr, destPtr, width, height, args[0] || 1);
        this.Module._free(ptr);
        ptr = destPtr; // Use blurred version
        break;
      case "edges":
        const edgePtr = this.Module._malloc(size);
        this.Module._edgeDetect(ptr, edgePtr, width, height);
        this.Module._free(ptr);
        ptr = edgePtr;
        break;
    }

    const time = performance.now() - start;

    // Copy back
    const result = new Uint8ClampedArray(
      this.Module.HEAP8.buffer,
      ptr,
      size
    ).slice();

    // Free
    this.Module._free(ptr);

    return {
      data: new ImageData(result, width, height),
      time,
    };
  }

  async processImageFromFile(file, filter, ...args) {
    const url = URL.createObjectURL(file);
    const img = await this.loadImage(url);
    const imageData = this.imageToData(img);
    URL.revokeObjectURL(url);

    return this.processImage(imageData, filter, ...args);
  }
}
```

**Part 3: Interactive Demo**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Image Processing with WASM</title>
    <style>
      body {
        font-family: Arial;
        margin: 20px;
      }
      .container {
        display: flex;
        gap: 20px;
        margin: 20px 0;
      }
      canvas {
        max-width: 400px;
        border: 1px solid #ccc;
        display: block;
      }
      .controls {
        margin: 20px 0;
      }
      button {
        margin: 5px;
        padding: 8px 15px;
      }
      input[type="range"] {
        width: 200px;
      }
      .time {
        color: #006600;
        font-weight: bold;
      }
    </style>
  </head>
  <body>
    <h1>Image Processing with WebAssembly</h1>

    <div>
      <input type="file" id="fileInput" accept="image/*" />
      <p>
        Or use sample image:
        <button onclick="loadSample()">Load Sample</button>
      </p>
    </div>

    <div class="controls">
      <h3>Filters</h3>
      <button onclick="applyFilter('grayscale')">Grayscale</button>
      <button onclick="applyFilter('invert')">Invert</button>
      <button onclick="applyFilter('edges')">Edge Detect</button>
      <br />
      <label
        >Brightness:
        <input type="range" id="brightness" min="-100" max="100" value="0" />
        <span id="brightnessValue">0</span>
      </label>
      <button onclick="applyBrightness()">Apply</button>
      <br />
      <label
        >Contrast:
        <input
          type="range"
          id="contrast"
          min="0"
          max="3"
          step="0.1"
          value="1"
        />
        <span id="contrastValue">1.0</span>
      </label>
      <button onclick="applyContrast()">Apply</button>
      <br />
      <label
        >Blur Radius:
        <input type="range" id="blur" min="1" max="10" value="2" />
        <span id="blurValue">2</span>
      </label>
      <button onclick="applyBlur()">Apply</button>
      <br />
      <button onclick="reset()">Reset</button>
      <div id="time" class="time"></div>
    </div>

    <div class="container">
      <div>
        <h3>Original</h3>
        <canvas id="original"></canvas>
      </div>
      <div>
        <h3>Processed</h3>
        <canvas id="processed"></canvas>
      </div>
    </div>

    <script src="image.js"></script>
    <script src="image-processor.js"></script>
    <script>
      let processor;
      let originalImageData;

      Module.onRuntimeInitialized = function () {
        processor = new ImageProcessor(Module);
      };

      document.getElementById("fileInput").onchange = function (e) {
        const file = e.target.files[0];
        if (file) {
          loadImageFile(file);
        }
      };

      // Update value displays
      document.getElementById("brightness").oninput = function () {
        document.getElementById("brightnessValue").textContent = this.value;
      };
      document.getElementById("contrast").oninput = function () {
        document.getElementById("contrastValue").textContent = this.value;
      };
      document.getElementById("blur").oninput = function () {
        document.getElementById("blurValue").textContent = this.value;
      };

      async function loadImageFile(file) {
        const img = await processor.loadImage(URL.createObjectURL(file));
        originalImageData = processor.imageToData(img);
        processor.dataToCanvas(
          originalImageData,
          document.getElementById("original")
        );
        processor.dataToCanvas(
          originalImageData,
          document.getElementById("processed")
        );
      }

      function loadSample() {
        // Create sample image
        const canvas = document.createElement("canvas");
        canvas.width = 300;
        canvas.height = 300;
        const ctx = canvas.getContext("2d");

        // Draw colorful pattern
        for (let y = 0; y < 300; y++) {
          for (let x = 0; x < 300; x++) {
            const r = (x / 300) * 255;
            const g = (y / 300) * 255;
            const b = 128;
            ctx.fillStyle = `rgb(${r},${g},${b})`;
            ctx.fillRect(x, y, 1, 1);
          }
        }

        originalImageData = ctx.getImageData(0, 0, 300, 300);
        processor.dataToCanvas(
          originalImageData,
          document.getElementById("original")
        );
        processor.dataToCanvas(
          originalImageData,
          document.getElementById("processed")
        );
      }

      function applyFilter(filter) {
        if (!originalImageData) {
          alert("Load an image first!");
          return;
        }

        const result = processor.processImage(originalImageData, filter);
        processor.dataToCanvas(
          result.data,
          document.getElementById("processed")
        );
        document.getElementById(
          "time"
        ).textContent = `Processed in ${result.time.toFixed(2)}ms`;
      }

      function applyBrightness() {
        const value = parseInt(document.getElementById("brightness").value);
        applyFilterWithArg("brightness", value);
      }

      function applyContrast() {
        const value = parseFloat(document.getElementById("contrast").value);
        applyFilterWithArg("contrast", value);
      }

      function applyBlur() {
        const value = parseInt(document.getElementById("blur").value);
        applyFilterWithArg("blur", value);
      }

      function applyFilterWithArg(filter, arg) {
        if (!originalImageData) {
          alert("Load an image first!");
          return;
        }

        const result = processor.processImage(originalImageData, filter, arg);
        processor.dataToCanvas(
          result.data,
          document.getElementById("processed")
        );
        document.getElementById(
          "time"
        ).textContent = `Processed in ${result.time.toFixed(2)}ms`;
      }

      function reset() {
        if (originalImageData) {
          processor.dataToCanvas(
            originalImageData,
            document.getElementById("processed")
          );
        }
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Compare WASM performance vs JavaScript canvas operations
- Try with large images (4K, 8K)
- Implement more filters (sepia, vignette, etc.)
- Test on mobile devices
- Implement real-time webcam processing
- Add batch processing

### Reflection Questions

1. **Performance:**

   - When is WASM faster for images?
   - What's the break-even point?
   - How do you optimize further?

2. **Architecture:**

   - How do you design image APIs?
   - What should be in WASM vs JS?
   - How do you handle different formats?

3. **Real-World:**
   - What apps benefit from this?
   - What are the limitations?
   - How do you handle edge cases?

---

## Section 17: Mathematical Libraries

### The Problem

JavaScript's Math library is limited. You need advanced mathematical operations - matrix multiplication, FFT, linear algebra. **WASM can provide optimized math libraries that are orders of magnitude faster.**

### Mathematical Operations

- What math operations are slow in JavaScript?
- What operations benefit from WASM?
- How do you handle floating point precision?
- What about numerical stability?
- How do you optimize math-heavy code?

### Matrix Operations

- How do you represent matrices in memory?
- How do you multiply matrices efficiently?
- What's the difference between row-major and column-major?
- How do you optimize for cache?
- What about SIMD?

### Linear Algebra

- Vector operations
- Matrix decomposition
- Eigenvalues and eigenvectors
- Solving linear systems
- When to use WASM vs libraries like math.js?

### Build It: Math Library

Create high-performance math functions:

**Requirements:**

**Part 1: C Math Library (mathlib.c)**

```c
#include <emscripten/emscripten.h>
#include <math.h>
#include <stdlib.h>
#include <string.h>

// === Vector Operations ===

EMSCRIPTEN_KEEPALIVE
float vectorDot(const float* a, const float* b, int size) {
    float result = 0.0f;
    for (int i = 0; i < size; i++) {
        result += a[i] * b[i];
    }
    return result;
}

EMSCRIPTEN_KEEPALIVE
void vectorAdd(const float* a, const float* b, float* result, int size) {
    for (int i = 0; i < size; i++) {
        result[i] = a[i] + b[i];
    }
}

EMSCRIPTEN_KEEPALIVE
void vectorScale(float* vec, float scalar, int size) {
    for (int i = 0; i < size; i++) {
        vec[i] *= scalar;
    }
}

EMSCRIPTEN_KEEPALIVE
float vectorLength(const float* vec, int size) {
    float sum = 0.0f;
    for (int i = 0; i < size; i++) {
        sum += vec[i] * vec[i];
    }
    return sqrtf(sum);
}

EMSCRIPTEN_KEEPALIVE
void vectorNormalize(float* vec, int size) {
    float length = vectorLength(vec, size);
    if (length > 0.0f) {
        for (int i = 0; i < size; i++) {
            vec[i] /= length;
        }
    }
}

// === Matrix Operations ===

EMSCRIPTEN_KEEPALIVE
void matrixMultiply(const float* a, const float* b, float* result,
                    int m, int n, int p) {
    // A is m×n, B is n×p, Result is m×p
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < p; j++) {
            float sum = 0.0f;
            for (int k = 0; k < n; k++) {
                sum += a[i * n + k] * b[k * p + j];
            }
            result[i * p + j] = sum;
        }
    }
}

EMSCRIPTEN_KEEPALIVE
void matrixTranspose(const float* matrix, float* result, int rows, int cols) {
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            result[j * rows + i] = matrix[i * cols + j];
        }
    }
}

EMSCRIPTEN_KEEPALIVE
void matrixAdd(const float* a, const float* b, float* result, int rows, int cols) {
    int size = rows * cols;
    for (int i = 0; i < size; i++) {
        result[i] = a[i] + b[i];
    }
}

EMSCRIPTEN_KEEPALIVE
void matrixScale(float* matrix, float scalar, int rows, int cols) {
    int size = rows * cols;
    for (int i = 0; i < size; i++) {
        matrix[i] *= scalar;
    }
}

// === Statistical Functions ===

EMSCRIPTEN_KEEPALIVE
float mean(const float* data, int size) {
    float sum = 0.0f;
    for (int i = 0; i < size; i++) {
        sum += data[i];
    }
    return sum / size;
}

EMSCRIPTEN_KEEPALIVE
float variance(const float* data, int size) {
    float m = mean(data, size);
    float sum = 0.0f;
    for (int i = 0; i < size; i++) {
        float diff = data[i] - m;
        sum += diff * diff;
    }
    return sum / size;
}

EMSCRIPTEN_KEEPALIVE
float standardDeviation(const float* data, int size) {
    return sqrtf(variance(data, size));
}

EMSCRIPTEN_KEEPALIVE
float correlation(const float* x, const float* y, int size) {
    float meanX = mean(x, size);
    float meanY = mean(y, size);

    float sumXY = 0.0f;
    float sumX2 = 0.0f;
    float sumY2 = 0.0f;

    for (int i = 0; i < size; i++) {
        float dx = x[i] - meanX;
        float dy = y[i] - meanY;
        sumXY += dx * dy;
        sumX2 += dx * dx;
        sumY2 += dy * dy;
    }

    return sumXY / sqrtf(sumX2 * sumY2);
}

// === Fast Fourier Transform (simplified) ===

EMSCRIPTEN_KEEPALIVE
void fft(float* real, float* imag, int n) {
    // Bit-reversal permutation
    int j = 0;
    for (int i = 0; i < n - 1; i++) {
        if (i < j) {
            float temp = real[i];
            real[i] = real[j];
            real[j] = temp;

            temp = imag[i];
            imag[i] = imag[j];
            imag[j] = temp;
        }

        int k = n / 2;
        while (k <= j) {
            j -= k;
            k /= 2;
        }
        j += k;
    }

    // FFT computation
    for (int len = 2; len <= n; len *= 2) {
        float angle = -2.0f * M_PI / len;
        float wlen_real = cosf(angle);
        float wlen_imag = sinf(angle);

        for (int i = 0; i < n; i += len) {
            float w_real = 1.0f;
            float w_imag = 0.0f;

            for (int j = 0; j < len / 2; j++) {
                float u_real = real[i + j];
                float u_imag = imag[i + j];

                float v_real = real[i + j + len / 2];
                float v_imag = imag[i + j + len / 2];

                float t_real = w_real * v_real - w_imag * v_imag;
                float t_imag = w_real * v_imag + w_imag * v_real;

                real[i + j] = u_real + t_real;
                imag[i + j] = u_imag + t_imag;

                real[i + j + len / 2] = u_real - t_real;
                imag[i + j + len / 2] = u_imag - t_imag;

                float temp = w_real * wlen_real - w_imag * wlen_imag;
                w_imag = w_real * wlen_imag + w_imag * wlen_real;
                w_real = temp;
            }
        }
    }
}

// === Numerical Integration ===

EMSCRIPTEN_KEEPALIVE
float integrate(float (*func)(float), float a, float b, int steps) {
    float h = (b - a) / steps;
    float sum = 0.0f;

    for (int i = 0; i < steps; i++) {
        float x = a + i * h;
        sum += func(x);
    }

    return sum * h;
}

// === Polynomial Operations ===

EMSCRIPTEN_KEEPALIVE
float evaluatePolynomial(const float* coefficients, int degree, float x) {
    float result = coefficients[degree];
    for (int i = degree - 1; i >= 0; i--) {
        result = result * x + coefficients[i];
    }
    return result;
}

EMSCRIPTEN_KEEPALIVE
void polynomialRoots(const float* coefficients, int degree,
                     float* roots, int maxIterations) {
    // Newton-Raphson method for finding roots
    // Simplified implementation
    for (int r = 0; r < degree; r++) {
        float x = (float)r; // Initial guess

        for (int iter = 0; iter < maxIterations; iter++) {
            float fx = evaluatePolynomial(coefficients, degree, x);

            // Compute derivative
            float dfx = 0.0f;
            for (int i = 1; i <= degree; i++) {
                dfx += i * coefficients[i] * powf(x, i - 1);
            }

            if (fabsf(dfx) < 1e-10f) break;

            x = x - fx / dfx;
        }

        roots[r] = x;
    }
}
```

**Part 2: Benchmark Against JavaScript**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Math Library Benchmark</title>
    <style>
      body {
        font-family: monospace;
        margin: 20px;
      }
      .test {
        margin: 20px 0;
        padding: 10px;
        background: #f0f0f0;
      }
      table {
        border-collapse: collapse;
        margin: 10px 0;
      }
      th,
      td {
        border: 1px solid #ccc;
        padding: 8px;
        text-align: left;
      }
      .faster {
        color: #006600;
        font-weight: bold;
      }
    </style>
  </head>
  <body>
    <h1>WASM Math Library Benchmark</h1>

    <div class="test">
      <h3>Matrix Multiplication</h3>
      <button onclick="benchmarkMatrixMult()">Run Benchmark</button>
      <table id="matrixResults"></table>
    </div>

    <div class="test">
      <h3>Vector Operations</h3>
      <button onclick="benchmarkVectorOps()">Run Benchmark</button>
      <table id="vectorResults"></table>
    </div>

    <div class="test">
      <h3>Statistical Functions</h3>
      <button onclick="benchmarkStats()">Run Benchmark</button>
      <table id="statsResults"></table>
    </div>

    <div class="test">
      <h3>FFT Performance</h3>
      <button onclick="benchmarkFFT()">Run Benchmark</button>
      <table id="fftResults"></table>
    </div>

    <script src="mathlib.js"></script>
    <script>
      let wasmModule;

      Module.onRuntimeInitialized = function () {
        wasmModule = Module;
      };

      // JavaScript implementations for comparison
      function jsMatrixMultiply(a, b, m, n, p) {
        const result = new Float32Array(m * p);
        for (let i = 0; i < m; i++) {
          for (let j = 0; j < p; j++) {
            let sum = 0;
            for (let k = 0; k < n; k++) {
              sum += a[i * n + k] * b[k * p + j];
            }
            result[i * p + j] = sum;
          }
        }
        return result;
      }

      function jsVectorDot(a, b) {
        let sum = 0;
        for (let i = 0; i < a.length; i++) {
          sum += a[i] * b[i];
        }
        return sum;
      }

      function jsMean(data) {
        return data.reduce((a, b) => a + b, 0) / data.length;
      }

      function benchmarkMatrixMult() {
        const sizes = [64, 128, 256];
        const results = [];

        results.push(["Size", "JavaScript", "WASM", "Speedup"]);

        sizes.forEach((size) => {
          // Create test matrices
          const a = new Float32Array(size * size);
          const b = new Float32Array(size * size);
          for (let i = 0; i < size * size; i++) {
            a[i] = Math.random();
            b[i] = Math.random();
          }

          // JavaScript
          const jsStart = performance.now();
          jsMatrixMultiply(a, b, size, size, size);
          const jsTime = performance.now() - jsStart;

          // WASM
          const aPtr = wasmModule._malloc(size * size * 4);
          const bPtr = wasmModule._malloc(size * size * 4);
          const resultPtr = wasmModule._malloc(size * size * 4);

          wasmModule.HEAPF32.set(a, aPtr >> 2);
          wasmModule.HEAPF32.set(b, bPtr >> 2);

          const wasmStart = performance.now();
          wasmModule._matrixMultiply(aPtr, bPtr, resultPtr, size, size, size);
          const wasmTime = performance.now() - wasmStart;

          wasmModule._free(aPtr);
          wasmModule._free(bPtr);
          wasmModule._free(resultPtr);

          const speedup = (jsTime / wasmTime).toFixed(2);
          results.push([
            `${size}×${size}`,
            `${jsTime.toFixed(2)}ms`,
            `${wasmTime.toFixed(2)}ms`,
            `${speedup}x`,
          ]);
        });

        displayResults("matrixResults", results);
      }

      function benchmarkVectorOps() {
        const sizes = [1000, 10000, 100000];
        const results = [];

        results.push(["Size", "JavaScript", "WASM", "Speedup"]);

        sizes.forEach((size) => {
          const a = new Float32Array(size);
          const b = new Float32Array(size);
          for (let i = 0; i < size; i++) {
            a[i] = Math.random();
            b[i] = Math.random();
          }

          // JavaScript
          const jsStart = performance.now();
          for (let i = 0; i < 100; i++) {
            jsVectorDot(a, b);
          }
          const jsTime = performance.now() - jsStart;

          // WASM
          const aPtr = wasmModule._malloc(size * 4);
          const bPtr = wasmModule._malloc(size * 4);
          wasmModule.HEAPF32.set(a, aPtr >> 2);
          wasmModule.HEAPF32.set(b, bPtr >> 2);

          const wasmStart = performance.now();
          for (let i = 0; i < 100; i++) {
            wasmModule._vectorDot(aPtr, bPtr, size);
          }
          const wasmTime = performance.now() - wasmStart;

          wasmModule._free(aPtr);
          wasmModule._free(bPtr);

          const speedup = (jsTime / wasmTime).toFixed(2);
          results.push([
            size.toLocaleString(),
            `${jsTime.toFixed(2)}ms`,
            `${wasmTime.toFixed(2)}ms`,
            `${speedup}x`,
          ]);
        });

        displayResults("vectorResults", results);
      }

      function benchmarkStats() {
        const size = 100000;
        const data = new Float32Array(size);
        for (let i = 0; i < size; i++) {
          data[i] = Math.random();
        }

        const results = [];
        results.push(["Operation", "JavaScript", "WASM", "Speedup"]);

        // Mean
        let jsStart = performance.now();
        jsMean(data);
        let jsTime = performance.now() - jsStart;

        const dataPtr = wasmModule._malloc(size * 4);
        wasmModule.HEAPF32.set(data, dataPtr >> 2);

        let wasmStart = performance.now();
        wasmModule._mean(dataPtr, size);
        let wasmTime = performance.now() - wasmStart;

        results.push([
          "Mean",
          `${jsTime.toFixed(3)}ms`,
          `${wasmTime.toFixed(3)}ms`,
          `${(jsTime / wasmTime).toFixed(2)}x`,
        ]);

        wasmModule._free(dataPtr);

        displayResults("statsResults", results);
      }

      function benchmarkFFT() {
        const sizes = [256, 512, 1024];
        const results = [];

        results.push(["Size", "WASM Time"]);

        sizes.forEach((size) => {
          const real = new Float32Array(size);
          const imag = new Float32Array(size);

          for (let i = 0; i < size; i++) {
            real[i] = Math.sin((2 * Math.PI * i) / size);
            imag[i] = 0;
          }

          const realPtr = wasmModule._malloc(size * 4);
          const imagPtr = wasmModule._malloc(size * 4);

          wasmModule.HEAPF32.set(real, realPtr >> 2);
          wasmModule.HEAPF32.set(imag, imagPtr >> 2);

          const start = performance.now();
          wasmModule._fft(realPtr, imagPtr, size);
          const time = performance.now() - start;

          wasmModule._free(realPtr);
          wasmModule._free(imagPtr);

          results.push([size, `${time.toFixed(3)}ms`]);
        });

        displayResults("fftResults", results);
      }

      function displayResults(tableId, data) {
        const table = document.getElementById(tableId);
        let html = "";

        data.forEach((row, i) => {
          const tag = i === 0 ? "th" : "td";
          html += "<tr>";
          row.forEach((cell, j) => {
            const className =
              i > 0 && j === 3 && parseFloat(cell) > 1 ? "faster" : "";
            html += `<${tag} class="${className}">${cell}</${tag}>`;
          });
          html += "</tr>";
        });

        table.innerHTML = html;
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Compare with JavaScript math libraries
- Test numerical stability
- Optimize matrix multiplication further
- Implement more advanced algorithms
- Test on different hardware
- Profile with different optimization levels

### Reflection Questions

1. **Performance:**

   - When is WASM significantly faster?
   - What operations don't benefit?
   - How do you optimize math code?

2. **Numerical Computing:**

   - What about precision?
   - How do you handle edge cases?
   - What about numerical stability?

3. **Libraries:**
   - When should you use WASM vs existing libraries?
   - How do you integrate with NumPy/SciPy workflows?
   - What about GPU acceleration?

---

## Section 18: Cryptography Functions

### The Problem

Cryptographic operations are computationally intensive. JavaScript implementations can be slow and vulnerable. **WASM provides fast, secure crypto implementations.**

### Cryptographic Algorithms

- Hashing (SHA-256, SHA-512)
- Encryption (AES, ChaCha20)
- Key derivation (PBKDF2, Argon2)
- Random number generation
- Constant-time operations

### Security Considerations

- Side-channel attacks
- Timing attacks
- Constant-time comparisons
- Secure memory wiping
- How WASM helps security

### Build It: Crypto Library

Implement cryptographic functions:

**Requirements:**

**Part 1: C Crypto Implementation (crypto.c)**

```c
#include <emscripten/emscripten.h>
#include <stdint.h>
#include <string.h>

// === SHA-256 Implementation ===

#define ROTR(x, n) (((x) >> (n)) | ((x) << (32 - (n))))
#define CH(x, y, z) (((x) & (y)) ^ (~(x) & (z)))
#define MAJ(x, y, z) (((x) & (y)) ^ ((x) & (z)) ^ ((y) & (z)))
#define EP0(x) (ROTR(x, 2) ^ ROTR(x, 13) ^ ROTR(x, 22))
#define EP1(x) (ROTR(x, 6) ^ ROTR(x, 11) ^ ROTR(x, 25))
#define SIG0(x) (ROTR(x, 7) ^ ROTR(x, 18) ^ ((x) >> 3))
#define SIG1(x) (ROTR(x, 17) ^ ROTR(x, 19) ^ ((x) >> 10))

static const uint32_t k[64] = {
    0x428a2f98, 0x71374491, 0xb5c0fbcf, 0xe9b5dba5,
    0x3956c25b, 0x59f111f1, 0x923f82a4, 0xab1c5ed5,
    0xd807aa98, 0x12835b01, 0x243185be, 0x550c7dc3,
    0x72be5d74, 0x80deb1fe, 0x9bdc06a7, 0xc19bf174,
    0xe49b69c1, 0xefbe4786, 0x0fc19dc6, 0x240ca1cc,
    0x2de92c6f, 0x4a7484aa, 0x5cb0a9dc, 0x76f988da,
    0x983e5152, 0xa831c66d, 0xb00327c8, 0xbf597fc7,
    0xc6e00bf3, 0xd5a79147, 0x06ca6351, 0x14292967,
    0x27b70a85, 0x2e1b2138, 0x4d2c6dfc, 0x53380d13,
    0x650a7354, 0x766a0abb, 0x81c2c92e, 0x92722c85,
    0xa2bfe8a1, 0xa81a664b, 0xc24b8b70, 0xc76c51a3,
    0xd192e819, 0xd6990624, 0xf40e3585, 0x106aa070,
    0x19a4c116, 0x1e376c08, 0x2748774c, 0x34b0bcb5,
    0x391c0cb3, 0x4ed8aa4a, 0x5b9cca4f, 0x682e6ff3,
    0x748f82ee, 0x78a5636f, 0x84c87814, 0x8cc70208,
    0x90befffa, 0xa4506ceb, 0xbef9a3f7, 0xc67178f2
};

typedef struct {
    uint8_t data[64];
    uint32_t datalen;
    uint64_t bitlen;
    uint32_t state[8];
} SHA256_CTX;

static void sha256_transform(SHA256_CTX *ctx, const uint8_t data[]) {
    uint32_t a, b, c, d, e, f, g, h, t1, t2, m[64];

    for (int i = 0, j = 0; i < 16; ++i, j += 4)
        m[i] = (data[j] << 24) | (data[j + 1] << 16) |
               (data[j + 2] << 8) | (data[j + 3]);

    for (int i = 16; i < 64; ++i)
        m[i] = SIG1(m[i - 2]) + m[i - 7] + SIG0(m[i - 15]) + m[i - 16];

    a = ctx->state[0];
    b = ctx->state[1];
    c = ctx->state[2];
    d = ctx->state[3];
    e = ctx->state[4];
    f = ctx->state[5];
    g = ctx->state[6];
    h = ctx->state[7];

    for (int i = 0; i < 64; ++i) {
        t1 = h + EP1(e) + CH(e, f, g) + k[i] + m[i];
        t2 = EP0(a) + MAJ(a, b, c);
        h = g;
        g = f;
        f = e;
        e = d + t1;
        d = c;
        c = b;
        b = a;
        a = t1 + t2;
    }

    ctx->state[0] += a;
    ctx->state[1] += b;
    ctx->state[2] += c;
    ctx->state[3] += d;
    ctx->state[4] += e;
    ctx->state[5] += f;
    ctx->state[6] += g;
    ctx->state[7] += h;
}

EMSCRIPTEN_KEEPALIVE
void sha256_init(SHA256_CTX *ctx) {
    ctx->datalen = 0;
    ctx->bitlen = 0;
    ctx->state[0] = 0x6a09e667;
    ctx->state[1] = 0xbb67ae85;
    ctx->state[2] = 0x3c6ef372;
    ctx->state[3] = 0xa54ff53a;
    ctx->state[4] = 0x510e527f;
    ctx->state[5] = 0x9b05688c;
    ctx->state[6] = 0x1f83d9ab;
    ctx->state[7] = 0x5be0cd19;
}

EMSCRIPTEN_KEEPALIVE
void sha256_update(SHA256_CTX *ctx, const uint8_t data[], size_t len) {
    for (size_t i = 0; i < len; ++i) {
        ctx->data[ctx->datalen] = data[i];
        ctx->datalen++;
        if (ctx->datalen == 64) {
            sha256_transform(ctx, ctx->data);
            ctx->bitlen += 512;
            ctx->datalen = 0;
        }
    }
}

EMSCRIPTEN_KEEPALIVE
void sha256_final(SHA256_CTX *ctx, uint8_t hash[]) {
    uint32_t i = ctx->datalen;

    if (ctx->datalen < 56) {
        ctx->data[i++] = 0x80;
        while (i < 56)
            ctx->data[i++] = 0x00;
    } else {
        ctx->data[i++] = 0x80;
        while (i < 64)
            ctx->data[i++] = 0x00;
        sha256_transform(ctx, ctx->data);
        memset(ctx->data, 0, 56);
    }

    ctx->bitlen += ctx->datalen * 8;
    ctx->data[63] = ctx->bitlen;
    ctx->data[62] = ctx->bitlen >> 8;
    ctx->data[61] = ctx->bitlen >> 16;
    ctx->data[60] = ctx->bitlen >> 24;
    ctx->data[59] = ctx->bitlen >> 32;
    ctx->data[58] = ctx->bitlen >> 40;
    ctx->data[57] = ctx->bitlen >> 48;
    ctx->data[56] = ctx->bitlen >> 56;
    sha256_transform(ctx, ctx->data);

    for (i = 0; i < 4; ++i) {
        hash[i]      = (ctx->state[0] >> (24 - i * 8)) & 0x000000ff;
        hash[i + 4]  = (ctx->state[1] >> (24 - i * 8)) & 0x000000ff;
        hash[i + 8]  = (ctx->state[2] >> (24 - i * 8)) & 0x000000ff;
        hash[i + 12] = (ctx->state[3] >> (24 - i * 8)) & 0x000000ff;
        hash[i + 16] = (ctx->state[4] >> (24 - i * 8)) & 0x000000ff;
        hash[i + 20] = (ctx->state[5] >> (24 - i * 8)) & 0x000000ff;
        hash[i + 24] = (ctx->state[6] >> (24 - i * 8)) & 0x000000ff;
        hash[i + 28] = (ctx->state[7] >> (24 - i * 8)) & 0x000000ff;
    }
}

// Convenience function
EMSCRIPTEN_KEEPALIVE
void sha256(const uint8_t *data, size_t len, uint8_t hash[32]) {
    SHA256_CTX ctx;
    sha256_init(&ctx);
    sha256_update(&ctx, data, len);
    sha256_final(&ctx, hash);
}

// === Constant-time comparison ===

EMSCRIPTEN_KEEPALIVE
int constantTimeCompare(const uint8_t *a, const uint8_t *b, size_t len) {
    uint8_t result = 0;
    for (size_t i = 0; i < len; i++) {
        result |= a[i] ^ b[i];
    }
    return result == 0;
}

// === Simple XOR cipher (for demonstration) ===

EMSCRIPTEN_KEEPALIVE
void xorCipher(uint8_t *data, size_t len, const uint8_t *key, size_t keyLen) {
    for (size_t i = 0; i < len; i++) {
        data[i] ^= key[i % keyLen];
    }
}

// === Secure memory wipe ===

EMSCRIPTEN_KEEPALIVE
void secureWipe(uint8_t *data, size_t len) {
    volatile uint8_t *p = data;
    while (len--) {
        *p++ = 0;
    }
}
```

**Part 2: JavaScript Wrapper**

```javascript
// crypto-wrapper.js
class WasmCrypto {
  constructor(module) {
    this.Module = module;
  }

  sha256(data) {
    // Convert string or array to Uint8Array
    const bytes =
      typeof data === "string"
        ? new TextEncoder().encode(data)
        : new Uint8Array(data);

    // Allocate memory
    const dataPtr = this.Module._malloc(bytes.length);
    const hashPtr = this.Module._malloc(32);

    // Copy data
    this.Module.HEAP8.set(bytes, dataPtr);

    // Compute hash
    this.Module._sha256(dataPtr, bytes.length, hashPtr);

    // Read result
    const hash = new Uint8Array(this.Module.HEAP8.buffer, hashPtr, 32).slice();

    // Free memory
    this.Module._free(dataPtr);
    this.Module._free(hashPtr);

    return hash;
  }

  sha256Hex(data) {
    const hash = this.sha256(data);
    return Array.from(hash)
      .map((b) => b.toString(16).padStart(2, "0"))
      .join("");
  }

  constantTimeCompare(a, b) {
    if (a.length !== b.length) return false;

    const aPtr = this.Module._malloc(a.length);
    const bPtr = this.Module._malloc(b.length);

    this.Module.HEAP8.set(a, aPtr);
    this.Module.HEAP8.set(b, bPtr);

    const result = this.Module._constantTimeCompare(aPtr, bPtr, a.length);

    this.Module._free(aPtr);
    this.Module._free(bPtr);

    return result === 1;
  }

  xorEncrypt(data, key) {
    const bytes = new Uint8Array(data);
    const keyBytes =
      typeof key === "string"
        ? new TextEncoder().encode(key)
        : new Uint8Array(key);

    const dataPtr = this.Module._malloc(bytes.length);
    const keyPtr = this.Module._malloc(keyBytes.length);

    this.Module.HEAP8.set(bytes, dataPtr);
    this.Module.HEAP8.set(keyBytes, keyPtr);

    this.Module._xorCipher(dataPtr, bytes.length, keyPtr, keyBytes.length);

    const result = new Uint8Array(
      this.Module.HEAP8.buffer,
      dataPtr,
      bytes.length
    ).slice();

    this.Module._free(dataPtr);
    this.Module._free(keyPtr);

    return result;
  }

  xorDecrypt(data, key) {
    // XOR is symmetric
    return this.xorEncrypt(data, key);
  }
}
```

**Part 3: Test and Benchmark**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Crypto Functions</title>
    <style>
      body {
        font-family: Arial;
        margin: 20px;
      }
      .test {
        margin: 20px 0;
        padding: 10px;
        background: #f0f0f0;
      }
      input[type="text"] {
        width: 400px;
        padding: 5px;
      }
      .hash {
        font-family: monospace;
        word-break: break-all;
        background: white;
        padding: 10px;
        margin: 10px 0;
      }
    </style>
  </head>
  <body>
    <h1>WebAssembly Cryptography</h1>

    <div class="test">
      <h3>SHA-256 Hash</h3>
      <input
        type="text"
        id="hashInput"
        value="Hello, World!"
        placeholder="Enter text to hash"
      />
      <button onclick="testHash()">Hash</button>
      <div class="hash" id="hashOutput"></div>
    </div>

    <div class="test">
      <h3>Constant-Time Comparison</h3>
      <input
        type="text"
        id="compare1"
        value="secret123"
        placeholder="String 1"
      />
      <input
        type="text"
        id="compare2"
        value="secret123"
        placeholder="String 2"
      />
      <button onclick="testCompare()">Compare</button>
      <div id="compareOutput"></div>
    </div>

    <div class="test">
      <h3>XOR Encryption/Decryption</h3>
      <input
        type="text"
        id="plaintext"
        value="Secret Message"
        placeholder="Message"
      />
      <input type="text" id="key" value="mykey" placeholder="Key" />
      <button onclick="testEncrypt()">Encrypt</button>
      <button onclick="testDecrypt()">Decrypt</button>
      <div id="encryptOutput"></div>
    </div>

    <div class="test">
      <h3>Performance Benchmark</h3>
      <button onclick="benchmarkHash()">Benchmark SHA-256</button>
      <div id="benchOutput"></div>
    </div>

    <script src="crypto.js"></script>
    <script src="crypto-wrapper.js"></script>
    <script>
      let crypto;
      let encryptedData = null;

      Module.onRuntimeInitialized = function () {
        crypto = new WasmCrypto(Module);
      };

      function testHash() {
        const input = document.getElementById("hashInput").value;
        const hash = crypto.sha256Hex(input);

        document.getElementById("hashOutput").innerHTML = `
                <strong>Input:</strong> ${input}<br>
                <strong>SHA-256:</strong> ${hash}
            `;
      }

      function testCompare() {
        const str1 = document.getElementById("compare1").value;
        const str2 = document.getElementById("compare2").value;

        const bytes1 = new TextEncoder().encode(str1);
        const bytes2 = new TextEncoder().encode(str2);

        const result = crypto.constantTimeCompare(bytes1, bytes2);

        document.getElementById("compareOutput").textContent = result
          ? "✓ Strings match"
          : "✗ Strings do not match";
      }

      function testEncrypt() {
        const plaintext = document.getElementById("plaintext").value;
        const key = document.getElementById("key").value;

        const plaintextBytes = new TextEncoder().encode(plaintext);
        encryptedData = crypto.xorEncrypt(plaintextBytes, key);

        const hex = Array.from(encryptedData)
          .map((b) => b.toString(16).padStart(2, "0"))
          .join("");

        document.getElementById("encryptOutput").innerHTML = `
                <strong>Plaintext:</strong> ${plaintext}<br>
                <strong>Encrypted (hex):</strong> ${hex}
            `;
      }

      function testDecrypt() {
        if (!encryptedData) {
          alert("Encrypt something first!");
          return;
        }

        const key = document.getElementById("key").value;
        const decrypted = crypto.xorDecrypt(encryptedData, key);
        const text = new TextDecoder().decode(decrypted);

        document.getElementById("encryptOutput").innerHTML += `<br>
                <strong>Decrypted:</strong> ${text}
            `;
      }

      async function benchmarkHash() {
        const sizes = [1000, 10000, 100000, 1000000];
        const results = [];

        for (const size of sizes) {
          const data = new Uint8Array(size);
          for (let i = 0; i < size; i++) {
            data[i] = i % 256;
          }

          // WASM
          const wasmStart = performance.now();
          for (let i = 0; i < 100; i++) {
            crypto.sha256(data);
          }
          const wasmTime = performance.now() - wasmStart;

          // JavaScript (using SubtleCrypto if available)
          let jsTime = "N/A";
          if (window.crypto && window.crypto.subtle) {
            const jsStart = performance.now();
            for (let i = 0; i < 100; i++) {
              await window.crypto.subtle.digest("SHA-256", data);
            }
            jsTime = (performance.now() - jsStart).toFixed(2) + "ms";
          }

          const throughput = (
            (((size * 100) / wasmTime) * 1000) /
            1024 /
            1024
          ).toFixed(2);

          results.push(
            `
${size.toLocaleString()} bytes:
  WASM: ${wasmTime.toFixed(2)}ms (${throughput} MB/s)
  JS Crypto API: ${jsTime}
                `.trim()
          );
        }

        document.getElementById("benchOutput").innerHTML =
          "<pre>" + results.join("\n\n") + "</pre>";
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Implement other hash functions (SHA-512, BLAKE2)
- Implement AES encryption
- Test timing attack resistance
- Benchmark against Web Crypto API
- Implement password hashing (PBKDF2, Argon2)
- Test with large files

### Reflection Questions

1. **Security:**

   - How does WASM improve crypto security?
   - What about side-channel attacks?
   - How do you ensure constant-time operations?

2. **Performance:**

   - When is WASM crypto faster?
   - How does it compare to Web Crypto API?
   - What operations benefit most?

3. **Best Practices:**
   - When should you use WASM crypto?
   - What about browser crypto APIs?
   - How do you handle key management?

---

## Section 19: Game Logic and Physics

### The Problem

Game loops need to run at 60 FPS. Physics calculations are expensive. Collision detection is complex. **WASM can handle game logic and physics much faster than JavaScript.**

### Game Architecture

- Game loop design
- Entity management
- State updates
- Rendering separation
- Frame timing

### Physics Simulation

- Collision detection
- Rigid body dynamics
- Particle systems
- Spatial partitioning
- Optimization techniques

### Build It: 2D Physics Engine

Create a simple physics system:

**Requirements:**

**Part 1: C Physics Engine (physics.c)**

```c
#include <emscripten/emscripten.h>
#include <math.h>
#include <stdlib.h>
#include <string.h>

#define MAX_ENTITIES 1000

typedef struct {
    float x, y;
} Vector2;

typedef struct {
    int id;
    float x, y;        // Position
    float vx, vy;      // Velocity
    float ax, ay;      // Acceleration
    float radius;
    float mass;
    int active;
} Entity;

typedef struct {
    Entity entities[MAX_ENTITIES];
    int count;
    float gravity;
    float damping;
    float width, height; // World bounds
} World;

static World world;

EMSCRIPTEN_KEEPALIVE
void initWorld(float width, float height, float gravity) {
    world.count = 0;
    world.gravity = gravity;
    world.damping = 0.99f;
    world.width = width;
    world.height = height;
    memset(world.entities, 0, sizeof(world.entities));
}

EMSCRIPTEN_KEEPALIVE
int addEntity(float x, float y, float radius, float mass) {
    if (world.count >= MAX_ENTITIES) return -1;

    Entity *e = &world.entities[world.count];
    e->id = world.count;
    e->x = x;
    e->y = y;
    e->vx = 0;
    e->vy = 0;
    e->ax = 0;
    e->ay = world.gravity;
    e->radius = radius;
    e->mass = mass;
    e->active = 1;

    return world.count++;
}

EMSCRIPTEN_KEEPALIVE
void setEntityVelocity(int id, float vx, float vy) {
    if (id >= 0 && id < world.count) {
        world.entities[id].vx = vx;
        world.entities[id].vy = vy;
    }
}

EMSCRIPTEN_KEEPALIVE
void applyForce(int id, float fx, float fy) {
    if (id >= 0 && id < world.count) {
        Entity *e = &world.entities[id];
        e->ax += fx / e->mass;
        e->ay += fy / e->mass;
    }
}

static int checkCollision(Entity *a, Entity *b) {
    float dx = b->x - a->x;
    float dy = b->y - a->y;
    float distance = sqrtf(dx * dx + dy * dy);
    return distance < (a->radius + b->radius);
}

static void resolveCollision(Entity *a, Entity *b) {
    // Calculate collision normal
    float dx = b->x - a->x;
    float dy = b->y - a->y;
    float distance = sqrtf(dx * dx + dy * dy);

    if (distance == 0) return; // Same position

    float nx = dx / distance;
    float ny = dy / distance;

    // Relative velocity
    float rvx = b->vx - a->vx;
    float rvy = b->vy - a->vy;

    // Velocity along normal
    float velAlongNormal = rvx * nx + rvy * ny;

    // Don't resolve if velocities are separating
    if (velAlongNormal > 0) return;

    // Coefficient of restitution (bounciness)
    float restitution = 0.8f;

    // Calculate impulse scalar
    float j = -(1 + restitution) * velAlongNormal;
    j /= 1 / a->mass + 1 / b->mass;

    // Apply impulse
    float impulseX = j * nx;
    float impulseY = j * ny;

    a->vx -= impulseX / a->mass;
    a->vy -= impulseY / a->mass;
    b->vx += impulseX / b->mass;
    b->vy += impulseY / b->mass;

    // Separate overlapping entities
    float overlap = (a->radius + b->radius) - distance;
    float separationX = nx * overlap * 0.5f;
    float separationY = ny * overlap * 0.5f;

    a->x -= separationX;
    a->y -= separationY;
    b->x += separationX;
    b->y += separationY;
}

EMSCRIPTEN_KEEPALIVE
void update(float deltaTime) {
    // Update entities
    for (int i = 0; i < world.count; i++) {
        Entity *e = &world.entities[i];
        if (!e->active) continue;

        // Update velocity
        e->vx += e->ax * deltaTime;
        e->vy += e->ay * deltaTime;

        // Apply damping
        e->vx *= world.damping;
        e->vy *= world.damping;

        // Update position
        e->x += e->vx * deltaTime;
        e->y += e->vy * deltaTime;

        // Reset acceleration
        e->ax = 0;
        e->ay = world.gravity;

        // Boundary collision
        if (e->x - e->radius < 0) {
            e->x = e->radius;
            e->vx = -e->vx * 0.8f;
        } else if (e->x + e->radius > world.width) {
            e->x = world.width - e->radius;
            e->vx = -e->vx * 0.8f;
        }

        if (e->y - e->radius < 0) {
            e->y = e->radius;
            e->vy = -e->vy * 0.8f;
        } else if (e->y + e->radius > world.height) {
            e->y = world.height - e->radius;
            e->vy = -e->vy * 0.8f;
        }
    }

    // Check collisions
    for (int i = 0; i < world.count - 1; i++) {
        for (int j = i + 1; j < world.count; j++) {
            if (world.entities[i].active && world.entities[j].active) {
                if (checkCollision(&world.entities[i], &world.entities[j])) {
                    resolveCollision(&world.entities[i], &world.entities[j]);
                }
            }
        }
    }
}

EMSCRIPTEN_KEEPALIVE
float* getEntityData() {
    static float data[MAX_ENTITIES * 3]; // x, y, radius for each

    for (int i = 0; i < world.count; i++) {
        data[i * 3] = world.entities[i].x;
        data[i * 3 + 1] = world.entities[i].y;
        data[i * 3 + 2] = world.entities[i].radius;
    }

    return data;
}

EMSCRIPTEN_KEEPALIVE
int getEntityCount() {
    return world.count;
}

EMSCRIPTEN_KEEPALIVE
void removeEntity(int id) {
    if (id >= 0 && id < world.count) {
        world.entities[id].active = 0;
    }
}

EMSCRIPTEN_KEEPALIVE
void clear() {
    world.count = 0;
}
```

**Part 2: JavaScript Game Loop**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>2D Physics Engine</title>
    <style>
      body {
        margin: 0;
        padding: 20px;
        font-family: Arial;
        display: flex;
        gap: 20px;
      }
      canvas {
        border: 1px solid #000;
        background: #f0f0f0;
      }
      .controls {
        display: flex;
        flex-direction: column;
        gap: 10px;
      }
      button {
        padding: 10px;
      }
      .stats {
        font-family: monospace;
        background: #fff;
        padding: 10px;
        border: 1px solid #ccc;
      }
    </style>
  </head>
  <body>
    <div>
      <canvas id="canvas" width="800" height="600"></canvas>
    </div>
    <div class="controls">
      <h3>Physics Simulation</h3>
      <button onclick="spawnBall()">Spawn Ball</button>
      <button onclick="spawnMany()">Spawn 50 Balls</button>
      <button onclick="clearWorld()">Clear</button>
      <button onclick="toggleGravity()">Toggle Gravity</button>
      <div class="stats" id="stats"></div>
      <p>Click canvas to spawn balls</p>
    </div>

    <script src="physics.js"></script>
    <script>
      const canvas = document.getElementById("canvas");
      const ctx = canvas.getContext("2d");
      let lastTime = 0;
      let gravityEnabled = true;

      Module.onRuntimeInitialized = function () {
        Module._initWorld(canvas.width, canvas.height, 500);
        requestAnimationFrame(gameLoop);
      };

      function gameLoop(timestamp) {
        const deltaTime = lastTime ? (timestamp - lastTime) / 1000 : 0;
        lastTime = timestamp;

        // Update physics (cap at 60 FPS equivalent)
        const dt = Math.min(deltaTime, 1 / 60);
        Module._update(dt);

        // Render
        render();

        // Stats
        updateStats(deltaTime);

        requestAnimationFrame(gameLoop);
      }

      function render() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        const count = Module._getEntityCount();
        const dataPtr = Module._getEntityData();
        const data = new Float32Array(
          Module.HEAPF32.buffer,
          dataPtr,
          count * 3
        );

        ctx.fillStyle = "#4CAF50";
        ctx.strokeStyle = "#2E7D32";
        ctx.lineWidth = 2;

        for (let i = 0; i < count; i++) {
          const x = data[i * 3];
          const y = data[i * 3 + 1];
          const radius = data[i * 3 + 2];

          ctx.beginPath();
          ctx.arc(x, y, radius, 0, Math.PI * 2);
          ctx.fill();
          ctx.stroke();
        }
      }

      function updateStats(deltaTime) {
        const fps = deltaTime > 0 ? (1 / deltaTime).toFixed(0) : 0;
        const count = Module._getEntityCount();

        document.getElementById("stats").textContent = `
FPS: ${fps}
Entities: ${count}
Frame time: ${(deltaTime * 1000).toFixed(2)}ms
            `.trim();
      }

      function spawnBall() {
        const x = Math.random() * canvas.width;
        const y = Math.random() * 100;
        const radius = 10 + Math.random() * 20;
        const mass = radius * radius;

        const id = Module._addEntity(x, y, radius, mass);

        // Random initial velocity
        Module._setEntityVelocity(
          id,
          (Math.random() - 0.5) * 200,
          Math.random() * 100
        );
      }

      function spawnMany() {
        for (let i = 0; i < 50; i++) {
          spawnBall();
        }
      }

      function clearWorld() {
        Module._clear();
        Module._initWorld(
          canvas.width,
          canvas.height,
          gravityEnabled ? 500 : 0
        );
      }

      function toggleGravity() {
        gravityEnabled = !gravityEnabled;
        Module._initWorld(
          canvas.width,
          canvas.height,
          gravityEnabled ? 500 : 0
        );
      }

      // Spawn on click
      canvas.addEventListener("click", (e) => {
        const rect = canvas.getBoundingClientRect();
        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;
        const radius = 15;
        const mass = radius * radius;

        Module._addEntity(x, y, radius, mass);
      });

      // Initial balls
      for (let i = 0; i < 10; i++) {
        spawnBall();
      }
    </script>
  </body>
</html>
```

**Experiments:**

- Add friction
- Implement different shapes (boxes, polygons)
- Add spatial partitioning (quadtree, grid)
- Implement joints and constraints
- Add particle effects
- Test with 1000+ entities
- Compare performance with JavaScript physics engines

### Reflection Questions

1. **Game Performance:**

   - When is WASM beneficial for games?
   - What logic should be in WASM?
   - What should stay in JavaScript?

2. **Physics:**

   - How do you optimize collision detection?
   - What about spatial partitioning?
   - How do you handle many entities?

3. **Architecture:**
   - How do you structure game code?
   - What about asset management?
   - How do you debug physics?

---

# 🔴 PART 6: PERFORMANCE OPTIMIZATION

---

## Section 20: Measuring WASM Performance

### The Problem

You built something in WASM. Is it actually faster? **You need to measure properly to know what to optimize.**

### Performance Measurement

- How do you measure WASM performance?
- What tools are available?
- How do you profile WASM?
- What's the overhead of measurement?
- How do you get accurate results?

### Browser Profiling

- Chrome DevTools Performance tab
- Firefox Profiler
- Memory profiling
- CPU profiling
- What information do you get?

### Bottleneck Identification

- Where is time spent?
- Is it computation or memory access?
- Is it the WASM or the boundary?
- How do you find hotspots?
- What should you optimize first?

### Build It: Performance Profiler

Create tools to measure performance:

**Requirements:**

```javascript
// performance-profiler.js
class WasmProfiler {
  constructor(module) {
    this.Module = module;
    this.measurements = new Map();
  }

  measure(name, fn, iterations = 1) {
    const times = [];

    for (let i = 0; i < iterations; i++) {
      const start = performance.now();
      fn();
      const end = performance.now();
      times.push(end - start);
    }

    const sorted = times.sort((a, b) => a - b);
    const result = {
      name,
      iterations,
      min: sorted[0],
      max: sorted[sorted.length - 1],
      mean: times.reduce((a, b) => a + b) / times.length,
      median: sorted[Math.floor(sorted.length / 2)],
      total: times.reduce((a, b) => a + b),
    };

    this.measurements.set(name, result);
    return result;
  }

  compare(name1, name2) {
    const m1 = this.measurements.get(name1);
    const m2 = this.measurements.get(name2);

    if (!m1 || !m2) return null;

    return {
      fasterOperation: m1.mean < m2.mean ? name1 : name2,
      speedup: Math.max(m1.mean, m2.mean) / Math.min(m1.mean, m2.mean),
      difference: Math.abs(m1.mean - m2.mean),
    };
  }

  report() {
    console.log("=== Performance Report ===\n");

    for (const [name, result] of this.measurements) {
      console.log(`${name}:`);
      console.log(`  Iterations: ${result.iterations}`);
      console.log(`  Min: ${result.min.toFixed(3)}ms`);
      console.log(`  Max: ${result.max.toFixed(3)}ms`);
      console.log(`  Mean: ${result.mean.toFixed(3)}ms`);
      console.log(`  Median: ${result.median.toFixed(3)}ms`);
      console.log(`  Total: ${result.total.toFixed(3)}ms\n`);
    }
  }

  clear() {
    this.measurements.clear();
  }
}
```

**Experiments:**

- Profile different optimization levels
- Measure memory allocation overhead
- Profile boundary crossings
- Test with different data sizes
- Use browser DevTools profiler
- Compare with JavaScript implementations

### Reflection Questions

1. **Measurement:**

   - How do you measure accurately?
   - What affects measurements?
   - How many iterations are needed?

2. **Profiling:**

   - What tools are most useful?
   - How do you interpret results?
   - What do flame graphs show?

3. **Optimization:**
   - What should you measure first?
   - When is optimization worth it?
   - How do you avoid premature optimization?

---

## Section 21: When WASM is Faster (and When It's Not)

### The Problem

Not everything should be in WASM. **Understanding when to use WASM vs JavaScript is crucial for performance.**

### WASM Advantages

- CPU-intensive computations
- Predictable performance
- No garbage collection pauses
- Optimized number crunching
- Existing C/C++ code

### WASM Disadvantages

- Boundary crossing overhead
- String handling
- DOM access
- Small operations
- Startup cost

### Making the Decision

- How much computation?
- How much data transfer?
- What's the break-even point?
- Can you batch operations?
- What about maintenance cost?

### Build It: Decision Framework

Create benchmarks to guide decisions:

```javascript
class WasmDecisionHelper {
  constructor(module) {
    this.Module = module;
  }

  // Test if operation benefits from WASM
  shouldUseWasm(jsFunc, wasmFunc, setup) {
    const testCases = [10, 100, 1000, 10000];
    const results = [];

    for (const size of testCases) {
      const data = setup(size);

      // JS
      const jsStart = performance.now();
      jsFunc(data);
      const jsTime = performance.now() - jsStart;

      // WASM
      const wasmStart = performance.now();
      wasmFunc(data);
      const wasmTime = performance.now() - wasmStart;

      results.push({
        size,
        jsTime,
        wasmTime,
        speedup: jsTime / wasmTime,
        recommendation: wasmTime < jsTime ? "WASM" : "JavaScript",
      });
    }

    return results;
  }

  // Find break-even point
  findBreakEven(jsFunc, wasmFunc, setup) {
    let low = 1,
      high = 100000;

    while (low < high) {
      const mid = Math.floor((low + high) / 2);
      const data = setup(mid);

      const jsTime = this.measure(() => jsFunc(data));
      const wasmTime = this.measure(() => wasmFunc(data));

      if (wasmTime < jsTime) {
        high = mid;
      } else {
        low = mid + 1;
      }
    }

    return low;
  }

  measure(fn) {
    const start = performance.now();
    fn();
    return performance.now() - start;
  }
}
```

### Reflection Questions

1. **When to Use WASM:**

   - What operations benefit most?
   - What's the break-even point?
   - How do you measure?

2. **Trade-offs:**

   - What's the maintenance cost?
   - What about debugging?
   - Is the speedup worth it?

3. **Real-World:**
   - How do you decide in production?
   - What about team skills?
   - Long-term considerations?

---

## Section 22: Optimizing C Code for WASM

### The Problem

C code that's fast natively might not be optimal for WASM. **WASM has different performance characteristics.**

### Compiler Optimization Levels

- What do -O0, -O1, -O2, -O3 do?
- What's -Os? When to use it?
- What optimizations does Emscripten apply?
- How do you control optimization?

### Memory Access Patterns

- Cache-friendly code matters
- Sequential access vs random access
- Alignment considerations
- Loop unrolling
- Data structure layout

### Function Inlining

- When should functions be inlined?
- How do you control inlining?
- What's the cost of function calls?
- What about indirect calls?

### Loop Optimization

- Loop unrolling
- Loop fusion
- Vectorization hints
- Minimizing branches

### Build It: Optimization Examples

```c
// Before: Cache-unfriendly
void process_bad(float* data, int width, int height) {
    for (int x = 0; x < width; x++) {
        for (int y = 0; y < height; y++) {
            data[y * width + x] *= 2.0f; // Column-major access
        }
    }
}

// After: Cache-friendly
void process_good(float* data, int width, int height) {
    for (int y = 0; y < height; y++) {
        for (int x = 0; x < width; x++) {
            data[y * width + x] *= 2.0f; // Row-major access
        }
    }
}

// Before: Many small allocations
int* create_bad(int size) {
    int* result = malloc(size * sizeof(int));
    for (int i = 0; i < size; i++) {
        result[i] = malloc(sizeof(int)); // Bad!
    }
    return result;
}

// After: Single allocation
int* create_good(int size) {
    return calloc(size, sizeof(int)); // Good!
}

// Before: Unnecessary abstraction
static inline int add(int a, int b) { return a + b; }
void compute_bad(int* arr, int size) {
    for (int i = 0; i < size; i++) {
        arr[i] = add(arr[i], 1); // Extra call overhead
    }
}

// After: Direct operation
void compute_good(int* arr, int size) {
    for (int i = 0; i < size; i++) {
        arr[i] += 1; // Inlined by compiler
    }
}

// Loop unrolling
void sum_unrolled(float* a, float* b, float* result, int size) {
    int i;
    for (i = 0; i < size - 3; i += 4) {
        result[i] = a[i] + b[i];
        result[i+1] = a[i+1] + b[i+1];
        result[i+2] = a[i+2] + b[i+2];
        result[i+3] = a[i+3] + b[i+3];
    }
    // Handle remainder
    for (; i < size; i++) {
        result[i] = a[i] + b[i];
    }
}
```

### Reflection Questions

1. **Optimization:**

   - What optimizations matter most?
   - How do you measure impact?
   - When is optimization worth it?

2. **Compiler:**

   - What does the compiler do?
   - How do you guide it?
   - What about compiler flags?

3. **Trade-offs:**
   - Code clarity vs performance?
   - When to micro-optimize?
   - How to maintain optimized code?

---

## Section 23: Understanding the Compilation Pipeline

### The Problem

Understanding how C becomes WASM helps you optimize better. **The compilation pipeline has multiple stages.**

### Compilation Stages

- Preprocessing
- C to LLVM IR
- LLVM optimization passes
- LLVM IR to WASM
- WASM optimization
- JavaScript glue code generation

### LLVM IR

- What is LLVM IR?
- How do you view it?
- What optimizations happen here?
- How does it map to WASM?

### WASM Format

- Text format (WAT)
- Binary format
- Optimization at WASM level
- What the browser sees

### Debugging

- Source maps
- DWARF debug info
- How to debug optimized code?
- What information is preserved?

### Build It: Explore Compilation

```bash
# See all compilation stages

# 1. Preprocessed C
emcc source.c -E -o source.i

# 2. LLVM IR
emcc source.c -S -emit-llvm -o source.ll

# 3. LLVM bitcode
emcc source.c -c -emit-llvm -o source.bc

# 4. WebAssembly text
emcc source.c -o source.wasm
wasm2wat source.wasm -o source.wat

# 5. With optimization
emcc source.c -O3 -o optimized.wasm
wasm2wat optimized.wasm -o optimized.wat

# Compare sizes
ls -lh source.wasm optimized.wasm

# With source maps
emcc source.c -o source.js -g4
```

### Reflection Questions

1. **Pipeline:**

   - What happens at each stage?
   - Where do optimizations occur?
   - How do you control the process?

2. **Optimization:**

   - What can you see in IR?
   - How does WASM differ from IR?
   - What optimizations are WASM-specific?

3. **Debugging:**
   - How do source maps work?
   - What's preserved in optimized builds?
   - How do you debug production issues?

---

# ⚫ PART 7: ADVANCED FEATURES

---

## Section 24: Working with Multiple WASM Modules

### The Problem

Large applications might split into multiple WASM modules. **How do you manage multiple modules? How do they interact?**

### Module Organization

- Why split into modules?
- How do modules communicate?
- Shared memory between modules?
- What about shared code?

### Loading Multiple Modules

- Sequential loading
- Parallel loading
- Dependencies between modules
- Module initialization order

### Sharing Resources

- Shared memory
- Shared tables
- Shared functions
- Import/export between modules

### Build It: Multi-Module System

```javascript
class ModuleManager {
  constructor() {
    this.modules = new Map();
  }

  async loadModule(name, url, imports = {}) {
    const response = await fetch(url);
    const module = await WebAssembly.instantiateStreaming(response, imports);

    this.modules.set(name, module.instance);
    return module.instance;
  }

  async loadModules(configs) {
    const promises = configs.map((config) =>
      this.loadModule(config.name, config.url, config.imports)
    );
    return Promise.all(promises);
  }

  getModule(name) {
    return this.modules.get(name);
  }

  // Create imports from other modules
  createImports(dependencies) {
    const imports = {};
    for (const [name, module] of this.modules) {
      if (dependencies.includes(name)) {
        imports[name] = module.exports;
      }
    }
    return imports;
  }
}

// Usage
const manager = new ModuleManager();

await manager.loadModules([
  {name: "math", url: "math.wasm"},
  {name: "utils", url: "utils.wasm"},
]);

// Load module that depends on others
const imports = manager.createImports(["math", "utils"]);
await manager.loadModule("app", "app.wasm", {
  env: imports,
});
```

### Reflection Questions

1. **Architecture:**

   - When should you split modules?
   - How do you organize code?
   - What about dependencies?

2. **Performance:**

   - What's the cost of multiple modules?
   - Loading time considerations?
   - Memory usage?

3. **Maintenance:**
   - How do you manage versions?
   - What about updates?
   - Testing multiple modules?

---

## Section 25: WebAssembly Tables and Function Pointers

### The Problem

Function pointers in C need to work in WASM. **Tables store function references.**

### Understanding Tables

- What is a WebAssembly table?
- How do function pointers work?
- What's the anyfunc type?
- How do you call through tables?

### Creating Tables

- How do you create a table?
- How do you populate it?
- Dynamic vs static tables
- Table growth

### Function Pointers in C

- How do function pointers compile?
- What happens when you call through a pointer?
- Indirect calls vs direct calls
- Performance implications

### Build It: Function Table Example

```c
#include <emscripten/emscripten.h>

typedef int (*Operation)(int, int);

EMSCRIPTEN_KEEPALIVE
int add(int a, int b) { return a + b; }

EMSCRIPTEN_KEEPALIVE
int subtract(int a, int b) { return a - b; }

EMSCRIPTEN_KEEPALIVE
int multiply(int a, int b) { return a * b; }

EMSCRIPTEN_KEEPALIVE
int apply(Operation op, int a, int b) {
    return op(a, b);
}

EMSCRIPTEN_KEEPALIVE
int compute(int choice, int a, int b) {
    Operation ops[] = {add, subtract, multiply};
    return ops[choice](a, b);
}
```

### Reflection Questions

1. **Tables:**

   - Why does WASM use tables?
   - How do they work?
   - What are the limitations?

2. **Performance:**

   - What's the cost of indirect calls?
   - How to minimize?
   - When to use function pointers?

3. **Design:**
   - When are function pointers useful?
   - What patterns use them?
   - What about callbacks?

---

## Section 26: SIMD in WebAssembly

### The Problem

SIMD (Single Instruction, Multiple Data) can process multiple values at once. **WASM supports SIMD for performance-critical code.**

### Understanding SIMD

- What is SIMD?
- What operations are available?
- How much speedup?
- Browser support?

### Using SIMD

- How do you enable SIMD?
- What's the syntax?
- How do you use it in C?
- What about portability?

### When to Use SIMD

- Image processing
- Vector math
- Audio processing
- Physics simulations
- Matrix operations

### Build It: SIMD Vector Operations

```c
#include <emscripten/emscripten.h>
#include <wasm_simd128.h>

EMSCRIPTEN_KEEPALIVE
void vector_add_simd(float* a, float* b, float* result, int size) {
    int i;
    for (i = 0; i < size - 3; i += 4) {
        v128_t va = wasm_v128_load(&a[i]);
        v128_t vb = wasm_v128_load(&b[i]);
        v128_t vr = wasm_f32x4_add(va, vb);
        wasm_v128_store(&result[i], vr);
    }

    // Handle remainder
    for (; i < size; i++) {
        result[i] = a[i] + b[i];
    }
}

EMSCRIPTEN_KEEPALIVE
void vector_multiply_simd(float* a, float* b, float* result, int size) {
    for (int i = 0; i < size - 3; i += 4) {
        v128_t va = wasm_v128_load(&a[i]);
        v128_t vb = wasm_v128_load(&b[i]);
        v128_t vr = wasm_f32x4_mul(va, vb);
        wasm_v128_store(&result[i], vr);
    }
}
```

Compile with SIMD:

```bash
emcc simd.c -o simd.js -msimd128 -O3
```

### Reflection Questions

1. **SIMD:**

   - When does it help?
   - What's the speedup?
   - What are limitations?

2. **Implementation:**

   - How do you write SIMD code?
   - What about auto-vectorization?
   - How to test?

3. **Portability:**
   - What's browser support?
   - How to handle fallbacks?
   - Is it worth the complexity?

---

## Section 27: Threading with WebAssembly

### The Problem

Some computations can be parallelized. **WASM supports threads for multi-core utilization.**

### WASM Threads

- How do WASM threads work?
- SharedArrayBuffer
- Atomics
- Thread creation and management

### Synchronization

- Mutexes
- Atomic operations
- Memory ordering
- Data races

### When to Use Threads

- Parallel computation
- Background tasks
- Data processing
- Not for everything!

### Build It: Threaded Computation

```c
#include <emscripten/emscripten.h>
#include <emscripten/threading.h>
#include <pthread.h>
#include <stdlib.h>

typedef struct {
    float* data;
    int start;
    int end;
    float result;
} ThreadData;

void* compute_sum(void* arg) {
    ThreadData* td = (ThreadData*)arg;
    float sum = 0;
    for (int i = td->start; i < td->end; i++) {
        sum += td->data[i];
    }
    td->result = sum;
    return NULL;
}

EMSCRIPTEN_KEEPALIVE
float parallel_sum(float* data, int size, int numThreads) {
    pthread_t threads[numThreads];
    ThreadData threadData[numThreads];
    int chunkSize = size / numThreads;

    // Create threads
    for (int i = 0; i < numThreads; i++) {
        threadData[i].data = data;
        threadData[i].start = i * chunkSize;
        threadData[i].end = (i == numThreads - 1) ? size : (i + 1) * chunkSize;
        pthread_create(&threads[i], NULL, compute_sum, &threadData[i]);
    }

    // Wait and sum results
    float total = 0;
    for (int i = 0; i < numThreads; i++) {
        pthread_join(threads[i], NULL);
        total += threadData[i].result;
    }

    return total;
}
```

Compile with threads:

```bash
emcc threads.c -o threads.js -pthread -O3 \
    -s USE_PTHREADS=1 \
    -s PTHREAD_POOL_SIZE=4
```

### Reflection Questions

1. **Threading:**

   - When is it beneficial?
   - What's the overhead?
   - What about browser support?

2. **Synchronization:**

   - How do you avoid data races?
   - What about deadlocks?
   - How to debug threading issues?

3. **Design:**
   - How to structure parallel code?
   - What granularity?
   - Is it worth the complexity?

---

# ⚪ PART 8: PRODUCTION DEPLOYMENT

---

## Section 28: Building for Production

### The Problem

Development builds are slow and large. **Production builds need optimization, smaller size, and reliability.**

### Build Configuration

- Optimization levels
- Link-time optimization (LTO)
- Dead code elimination
- Minification
- Source maps for production

### Size Optimization

- Code splitting
- Lazy loading
- Compression (gzip, brotli)
- Removing debug info
- What to include/exclude

### Build Scripts

```bash
# Production build script
#!/bin/bash

# Clean
rm -rf dist/*

# Build with optimizations
emcc src/*.c \
    -o dist/app.js \
    -O3 \
    -flto \
    -s WASM=1 \
    -s MODULARIZE=1 \
    -s EXPORT_ES6=1 \
    --closure 1 \
    -s ALLOW_MEMORY_GROWTH=1 \
    -s INITIAL_MEMORY=16MB \
    -s MAXIMUM_MEMORY=256MB

# Generate source maps
emcc src/*.c \
    -o dist/app.debug.js \
    -O3 \
    -g4

# Compress
gzip -k dist/app.wasm
brotli dist/app.wasm

# Report sizes
echo "Build complete:"
ls -lh dist/
```

### Reflection Questions

1. **Optimization:**

   - What flags matter most?
   - What's the size/speed trade-off?
   - How much can you reduce size?

2. **Reliability:**

   - How to ensure correctness?
   - What testing is needed?
   - How to catch regressions?

3. **Deployment:**
   - How to serve WASM files?
   - What about CDN?
   - Cache considerations?

---

## Section 29: Debugging WASM Applications

### The Problem

Production bugs are hard to debug. **You need tools and strategies for WASM debugging.**

### Development Tools

- Chrome DevTools
- Firefox DevTools
- Source maps
- Breakpoints in WASM
- Variable inspection

### Logging and Tracing

- Printf debugging
- Custom logging
- Performance marks
- Error reporting

### Common Issues

- Memory corruption
- Incorrect data transfer
- Performance problems
- Browser compatibility
- Race conditions

### Build It: Debug Helper

```c
#include <emscripten/emscripten.h>
#include <stdio.h>
#include <stdarg.h>

// Debug logging
#ifdef DEBUG
    #define DEBUG_LOG(fmt, ...) printf("[DEBUG] " fmt "\n", ##__VA_ARGS__)
#else
    #define DEBUG_LOG(fmt, ...) ((void)0)
#endif

// Assert with message
#define ASSERT(condition, message) \
    if (!(condition)) { \
        printf("ASSERTION FAILED: %s at %s:%d\n", message, __FILE__, __LINE__); \
        emscripten_force_exit(1); \
    }

// Memory check
EMSCRIPTEN_KEEPALIVE
void checkMemory(void* ptr, const char* name) {
    if (!ptr) {
        printf("ERROR: Null pointer for %s\n", name);
    } else {
        DEBUG_LOG("Memory OK: %s at %p", name, ptr);
    }
}

// Performance timer
static double startTime = 0;

EMSCRIPTEN_KEEPALIVE
void startTimer() {
    startTime = emscripten_get_now();
}

EMSCRIPTEN_KEEPALIVE
void endTimer(const char* label) {
    double elapsed = emscripten_get_now() - startTime;
    printf("TIMER [%s]: %.2fms\n", label, elapsed);
}
```

### Reflection Questions

1. **Debugging:**

   - What tools are most useful?
   - How to debug optimized code?
   - What about production issues?

2. **Prevention:**

   - How to prevent bugs?
   - What testing strategies?
   - How to catch issues early?

3. **Process:**
   - What's your debugging workflow?
   - How to reproduce issues?
   - Documentation practices?

---

## Section 30: Error Handling Patterns

### The Problem

Errors happen in production. **Robust error handling is essential.**

### Error Strategies

- Return codes
- Error callbacks
- Exceptions (limited in WASM)
- Logging
- Graceful degradation

### Validation

- Input validation
- Boundary checking
- Type checking
- State validation

### Recovery

- How to handle errors?
- Can you recover?
- Fallback strategies
- User communication

### Build It: Error Handling System

```c
#include <emscripten/emscripten.h>
#include <stdlib.h>
#include <string.h>

typedef enum {
    ERR_OK = 0,
    ERR_NULL_POINTER,
    ERR_INVALID_SIZE,
    ERR_OUT_OF_MEMORY,
    ERR_OUT_OF_BOUNDS,
    ERR_INVALID_STATE
} ErrorCode;

typedef struct {
    ErrorCode code;
    char message[256];
    const char* file;
    int line;
} Error;

static Error lastError = {ERR_OK, "", NULL, 0};

void setError(ErrorCode code, const char* message,
              const char* file, int line) {
    lastError.code = code;
    strncpy(lastError.message, message, 255);
    lastError.message[255] = '\0';
    lastError.file = file;
    lastError.line = line;
}

#define SET_ERROR(code, msg) setError(code, msg, __FILE__, __LINE__)

EMSCRIPTEN_KEEPALIVE
ErrorCode getLastErrorCode() {
    return lastError.code;
}

EMSCRIPTEN_KEEPALIVE
const char* getLastErrorMessage() {
    return lastError.message;
}

EMSCRIPTEN_KEEPALIVE
void clearError() {
    lastError.code = ERR_OK;
    lastError.message[0] = '\0';
}

// Example function with error handling
EMSCRIPTEN_KEEPALIVE
int* safeArrayCreate(int size) {
    if (size <= 0) {
        SET_ERROR(ERR_INVALID_SIZE, "Array size must be positive");
        return NULL;
    }

    if (size > 1000000) {
        SET_ERROR(ERR_INVALID_SIZE, "Array size too large");
        return NULL;
    }

    int* arr = malloc(size * sizeof(int));
    if (!arr) {
        SET_ERROR(ERR_OUT_OF_MEMORY, "Failed to allocate memory");
        return NULL;
    }

    return arr;
}
```

JavaScript error handling:

```javascript
class WasmErrorHandler {
  constructor(module) {
    this.Module = module;
  }

  checkError() {
    const code = this.Module._getLastErrorCode();
    if (code !== 0) {
      const message = this.Module.UTF8ToString(
        this.Module._getLastErrorMessage()
      );
      this.Module._clearError();
      throw new Error(`WASM Error ${code}: ${message}`);
    }
  }

  safeCall(fn) {
    try {
      const result = fn();
      this.checkError();
      return result;
    } catch (error) {
      console.error("WASM operation failed:", error);
      throw error;
    }
  }
}
```

### Reflection Questions

1. **Error Handling:**

   - What strategy works best?
   - How to communicate errors?
   - What about error recovery?

2. **Robustness:**

   - How to prevent errors?
   - What should be validated?
   - How thorough should checks be?

3. **User Experience:**
   - How to handle errors gracefully?
   - What to show users?
   - How to recover?

---

## Section 31: Browser Compatibility and Polyfills

### The Problem

Not all browsers support all WASM features. **You need to handle compatibility.**

### Feature Detection

- How to detect WASM support?
- How to detect SIMD support?
- How to detect threads support?
- SharedArrayBuffer availability?

### Fallbacks

- JavaScript fallback
- Feature-limited versions
- Progressive enhancement
- Graceful degradation

### Polyfills

- What can be polyfilled?
- What can't be polyfilled?
- Performance implications
- When to use fallbacks?

### Build It: Compatibility Layer

```javascript
class WasmCompatibility {
  static async checkSupport() {
    return {
      wasm: typeof WebAssembly !== "undefined",
      streaming: typeof WebAssembly.instantiateStreaming !== "undefined",
      threads: typeof SharedArrayBuffer !== "undefined",
      simd: await this.checkSIMD(),
      bigInt: typeof BigInt !== "undefined",
    };
  }

  static async checkSIMD() {
    try {
      const simdTest = new Uint8Array([
        0, 97, 115, 109, 1, 0, 0, 0, 1, 5, 1, 96, 0, 1, 123, 3, 2, 1, 0, 10, 10,
        1, 8, 0, 65, 0, 253, 15, 253, 98, 11,
      ]);
      await WebAssembly.instantiate(simdTest);
      return true;
    } catch {
      return false;
    }
  }

  static async loadWithFallback(wasmUrl, jsUrl) {
    const support = await this.checkSupport();

    if (!support.wasm) {
      console.log("WASM not supported, using JavaScript fallback");
      return import(jsUrl);
    }

    if (support.streaming) {
      return WebAssembly.instantiateStreaming(fetch(wasmUrl));
    } else {
      const response = await fetch(wasmUrl);
      const buffer = await response.arrayBuffer();
      return WebAssembly.instantiate(buffer);
    }
  }
}

// Usage
async function initApp() {
  const support = await WasmCompatibility.checkSupport();
  console.log("Browser support:", support);

  if (support.wasm) {
    // Load WASM version
    const module = await WasmCompatibility.loadWithFallback(
      "app.wasm",
      "app-fallback.js"
    );
    return new WasmApp(module);
  } else {
    // Load pure JS version
    const fallback = await import("./app-fallback.js");
    return new JSApp(fallback);
  }
}
```

### Reflection Questions

1. **Compatibility:**

   - What features are essential?
   - How to handle unsupported features?
   - What browsers to support?

2. **Fallbacks:**

   - When are they necessary?
   - What's the performance impact?
   - How to maintain two versions?

3. **Strategy:**
   - Progressive enhancement vs graceful degradation?
   - What about mobile browsers?
   - Future-proofing?

---

# 🎓 Congratulations!

You've completed the **WebAssembly using C Self-Mastery Workbook**!

### What You've Mastered

✅ **Part 1: WebAssembly Fundamentals** - Understanding WASM, stack machine, WAT  
✅ **Part 2: Compiling C to WASM** - Emscripten, compilation, memory model  
✅ **Part 3: JavaScript-WASM Interop** - Calling between JS and WASM, data transfer  
✅ **Part 4: Memory Management** - Linear memory, strings, arrays, debugging  
✅ **Part 5: Real Applications** - Image processing, math, crypto, games  
✅ **Part 6: Performance** - Measuring, optimizing, understanding trade-offs  
✅ **Part 7: Advanced Features** - SIMD, threads, tables, multiple modules  
✅ **Part 8: Production** - Building, debugging, error handling, compatibility

### You Now Have Deep WebAssembly Mastery

You understand WebAssembly at a level where:

- ✅ You can port C code to the web efficiently
- ✅ You know when to use WASM vs JavaScript
- ✅ You can optimize for performance
- ✅ You can debug complex issues
- ✅ You can build production applications
- ✅ You understand the compilation pipeline
- ✅ You can leverage advanced features

### What's Next?

#### Option 1: Specialize Further

- **Rust and WebAssembly** - Modern systems language for WASM
- **AssemblyScript** - TypeScript-like language for WASM
- **Advanced Graphics** - WebGL/WebGPU with WASM
- **Audio Processing** - Real-time audio with WASM
- **Game Engines** - Build complete game engines

#### Option 2: Production Projects

- **Port existing C/C++ libraries** - Bring powerful libraries to the web
- **Build high-performance web apps** - Leverage WASM for speed
- **Create hybrid applications** - Mix WASM and JavaScript optimally
- **Contribute to open source** - WASM ecosystem projects

#### Option 3: Advanced Topics

- **WASI (WebAssembly System Interface)** - Run WASM outside browsers
- **Component Model** - Next-gen WASM modularity
- **GC Proposal** - Garbage collection in WASM
- **Interface Types** - Better language interop

### Keep Growing

- **Build projects** - Apply what you learned
- **Optimize real applications** - Measure and improve
- **Share knowledge** - Blog, teach, contribute
- **Stay current** - WASM evolves rapidly
- **Experiment** - Try new features and techniques

### Resources

- **Emscripten Docs**: https://emscripten.org/docs/
- **WebAssembly Spec**: https://webassembly.github.io/spec/
- **MDN WebAssembly**: https://developer.mozilla.org/en-US/docs/WebAssembly
- **WebAssembly Weekly**: Newsletter for latest developments

---

**You're now a WebAssembly expert. You can bring the power of C to the web and build incredibly fast applications. Go create something amazing! 🚀**
