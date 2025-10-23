# The C Programming Self-Mastery Workbook

---

## Table of Contents

- [💻 Prerequisites](#-prerequisites)
- [How to Use This Workbook](#how-to-use-this-workbook)
- [🌱 Philosophy Behind This Workbook](#-philosophy-behind-this-workbook)

### 🟢 PART 1: FOUNDATIONS & COMPILATION

- [Section 1: What is C? Understanding Systems Programming](#section-1-what-is-c-understanding-systems-programming)
- [Section 2: Compilation Process & Build Systems](#section-2-compilation-process--build-systems)

### 🟡 PART 2: MEMORY FUNDAMENTALS

- [Section 3: Variables, Types & Memory Layout](#section-3-variables-types--memory-layout)
- [Section 4: Pointers - The Heart of C](#section-4-pointers---the-heart-of-c)
- [Section 5: Arrays & Pointer Arithmetic](#section-5-arrays--pointer-arithmetic)

### 🔵 PART 3: MANUAL MEMORY MANAGEMENT

- [Section 6: Dynamic Memory Allocation](#section-6-dynamic-memory-allocation)
- [Section 7: Memory Leaks & Debugging](#section-7-memory-leaks--debugging)
- [Section 8: Stack vs Heap - Understanding the Trade-offs](#section-8-stack-vs-heap---understanding-the-trade-offs)

### 🟣 PART 4: STRUCTURED DATA

- [Section 9: Structs & Custom Types](#section-9-structs--custom-types)
- [Section 10: Building Data Structures from Scratch](#section-10-building-data-structures-from-scratch)
- [Section 11: Function Pointers & Callbacks](#section-11-function-pointers--callbacks)

### 🟠 PART 5: STRINGS & FILE I/O

- [Section 12: String Manipulation - The C Way](#section-12-string-manipulation---the-c-way)
- [Section 13: File Operations & Binary I/O](#section-13-file-operations--binary-io)
- [Section 14: Command-Line Arguments & Environment](#section-14-command-line-arguments--environment)

### 🔴 PART 6: PREPROCESSOR & COMPILATION CONTROL

- [Section 15: Preprocessor Directives & Macros](#section-15-preprocessor-directives--macros)
- [Section 16: Header Files & Modular Design](#section-16-header-files--modular-design)
- [Section 17: Conditional Compilation & Portability](#section-17-conditional-compilation--portability)

### ⚫ PART 7: SYSTEMS PROGRAMMING

- [Section 18: System Calls & OS Interface](#section-18-system-calls--os-interface)
- [Section 19: Process Control & Signals](#section-19-process-control--signals)
- [Section 20: Inter-Process Communication](#section-20-inter-process-communication)

### ⚪ PART 8: ADVANCED MEMORY & OPTIMIZATION

- [Section 21: Memory Alignment & Padding](#section-21-memory-alignment--padding)
- [Section 22: Cache-Friendly Code & Performance](#section-22-cache-friendly-code--performance)
- [Section 23: Bit Manipulation & Low-Level Tricks](#section-23-bit-manipulation--low-level-tricks)

### 🟤 PART 9: PRODUCTION-QUALITY C

- [Section 24: Error Handling Patterns](#section-24-error-handling-patterns)
- [Section 25: Writing Testable & Maintainable C](#section-25-writing-testable--maintainable-c)
- [Section 26: Debugging Tools & Techniques](#section-26-debugging-tools--techniques)

---

## 💻 Prerequisites

Before starting this workbook, you should have:

### ✅ Basic Programming Knowledge

- Understanding of variables, functions, loops, and conditionals from ANY language
- Familiarity with the command line / terminal
- Basic problem-solving skills

### ✅ What You Need Installed

- **GCC or Clang compiler** (C compiler)
- **Text editor or IDE** (VSCode, Vim, Emacs, CLion)
- **Make** (build tool) - optional but recommended
- **GDB or LLDB** (debugger) - for debugging exercises
- **Valgrind** (memory checker) - for memory leak detection

### ✅ Helpful Knowledge (Not Required, But Useful)

- Basic understanding of how computers work (CPU, RAM, storage)
- Familiarity with hexadecimal notation
- Basic Linux/Unix command line

---

## How to Use This Workbook

This document is **not a tutorial**. It will not hand you the answers.

Instead, it gives you the **right questions to ask yourself** — questions every C programmer must be able to answer to master systems programming at a professional level.

### Here's how to use it effectively:

#### 1. Ask Yourself First

- Before looking things up, try to explain the answer in your own words
- If you can't, that's fine — it means you found a gap in your knowledge
- Write down questions that come up — your curiosity is your guide

#### 2. Leverage All Resources

- Use Google, Stack Overflow, and ChatGPT to research
- Read the C specification (though it's dense)
- Experiment with code — compile and run examples
- Use debugging tools to understand what's happening

#### 3. Learn by Doing

- Each section has "Build It" exercises
- These exercises force you to discover answers naturally
- Don't skip them — implementation solidifies understanding
- Make mistakes! Segfaults teach you about memory

#### 4. Reflect and Explain

- After finding an answer, teach it back:
  - Explain to a friend or colleague
  - Write notes in your own words
  - Draw memory diagrams
- If you can explain clearly, you've truly learned it

#### 5. Iterate and Improve

- Revisit sections as you grow
- Your understanding will deepen each time
- Come back to "Build It" projects and improve them

---

## 🌱 Philosophy Behind This Workbook

### This is a "find the answer within yourself" approach to C mastery.

Traditional C courses say: "Here's a pointer. It stores an address. Here's how to use it."

This workbook says: "Your program just crashed with a segfault. Why? What does the debugger show? How do you prevent this?"

### Core Beliefs

- **Understanding > Memorization** - You'll learn WHY C behaves this way, not just HOW to write syntax
- **Discovery > Lecture** - Questions guide you to discover through experimentation and debugging
- **Building > Reading** - You'll implement systems from scratch to understand them deeply
- **Debugging is Learning** - Every segfault, memory leak, and compiler error teaches you something
- **Tool-agnostic** - Use whatever helps you learn: man pages, Google, ChatGPT, documentation

### Questions Grow With You

This workbook starts with the fundamentals and progressively deepens:

- **Foundational questions** - What is this? Why does it exist?
- **How-to questions** - How do I use this correctly?
- **Deep questions** - Why does C behave this way at the assembly level?
- **Scenario questions** - Your program leaks memory. What tools do you use? How do you fix it?

By the time you've asked and answered everything here — and built all the exercises — you won't just "know C syntax." **You'll understand memory, compilation, and systems programming so deeply that you can write efficient, bug-free C code, debug complex issues, and read any C codebase with confidence.**

### What This Workbook Prepares You For

After completing this workbook, you'll be ready to:

- **Write operating system components** - Kernels, drivers, schedulers
- **Build performance-critical systems** - Game engines, databases, compilers
- **Read and contribute to** major C projects - Linux, Redis, SQLite, Git
- **Understand other systems languages** - Rust, Zig, Go will make more sense
- **Debug anything** - You'll understand what's happening at the machine level

---

# 🟢 PART 1: FOUNDATIONS & COMPILATION

---

## Section 1: What is C? Understanding Systems Programming

### The Problem

You want to write an operating system. Or a device driver. Or the fastest possible database. Python and JavaScript are too slow and hide too much. You need control over memory, you need to understand what the CPU is doing, and you need predictable performance.

**High-level languages abstract away the hardware.** C gives you direct access to memory and hardware while still being portable across systems. That's systems programming.

### Understanding C's Purpose

- What problem does C solve that higher-level languages don't?
- Why do operating systems like Linux, Windows (parts), and macOS use C?
- Your Python program allocates memory automatically. Your C program makes you manage it manually. Why would anyone want that?
- What makes C "close to the hardware"? What does that mean?
- JavaScript runs in a browser. Where does your C program run?

### Compiled vs Interpreted

- Python and JavaScript are interpreted. C is compiled. What's the difference?
- You write `hello.c`. What do you need to do before you can run it?
- What does the compiler do? What does it produce?
- You change one line in your C file. Do you need to recompile? Why?
- What's faster at runtime: compiled or interpreted code? Why?

### C's Philosophy

- C is often called "portable assembly." What does that mean?
- Why doesn't C have automatic garbage collection?
- Why doesn't C have classes, exceptions, or namespaces?
- C gives you enough rope to hang yourself. What does this mean?
- What's the difference between C's philosophy and modern language philosophy?

### The Power and Danger

- You allocate 10 bytes but write to the 11th byte. What happens?
- You forget to free memory. What happens?
- You dereference a NULL pointer. What happens?
- Why do people say C is "unsafe" compared to Rust or modern languages?
- If C is dangerous, why is it still everywhere?

### Build It: Hello World and Compilation

Create your first C program and understand the compilation process:

**Requirements:**

1. Create `hello.c`:

```c
#include <stdio.h>

int main(void) {
    printf("Hello, World!\n");
    return 0;
}
```

2. Compile it: `gcc hello.c -o hello`
3. Run it: `./hello`
4. Examine the output binary: `ls -lh hello`

**Experiments:**

- Compile without `-o hello` — what file does it create?
- Use `gcc -S hello.c` — open `hello.s` — what do you see?
- Use `gcc -E hello.c` — what does preprocessor output show?
- Forget the `#include <stdio.h>` — what error do you get?
- Change `return 0` to `return 42` — run `echo $?` after — what do you see?
- Try `gcc -O0 hello.c -o hello` vs `gcc -O3 hello.c -o hello` — compare binary sizes

### Reflection Questions

1. **Compilation Process:**

   - What are the stages of compilation?
   - What's the difference between compilation and linking?
   - What is an object file?

2. **Understanding Output:**

   - What's inside a compiled binary?
   - Can you read it? Why or why not?
   - How is it different from a script?

3. **Return Values:**
   - Why does `main` return an int?
   - What does `return 0` mean?
   - Who receives this return value?

---

## Section 2: Compilation Process & Build Systems

### The Problem

You have 50 C files. Compiling them individually is tedious. When you change one file, should you recompile everything? How do libraries get linked? What about platform-specific code?

**Managing compilation manually doesn't scale.** You need build systems and understanding of how compilation works.

### Understanding Compilation Stages

- You run `gcc hello.c -o hello` — what steps happen internally?
- What's the difference between preprocessing, compiling, assembling, and linking?
- What does the preprocessor do? (Hint: try `gcc -E`)
- What does the compiler produce? (Hint: try `gcc -S`)
- What does the assembler produce? (Hint: try `gcc -c`)
- What does the linker do? Why do you need it?

### Object Files and Linking

- You compile with `gcc -c file.c` — what do you get?
- What's inside a `.o` file? How is it different from an executable?
- You have `main.c` and `utils.c` — how do you compile them into one program?
- What are "undefined references"? When do you see them?
- What's the difference between static and dynamic linking?

### Header Files

- Why do C programs have both `.c` and `.h` files?
- What goes in a header file? What goes in a source file?
- What does `#include` actually do?
- You `#include "myfile.h"` in three different files. Is the code copied three times?
- What are "header guards"? Why do you need them?

### Libraries

- What's a static library? (`.a` file)
- What's a shared/dynamic library? (`.so` or `.dylib`)
- How do you link against a library?
- What does `-l` flag do in `gcc -lm`?
- What does `-L` flag do?

### Make and Build Systems

- You have 10 files. One changes. Do you need to recompile all 10?
- What does `make` do? How does it know what to rebuild?
- What's a `Makefile`? What's the basic structure?
- What are targets, prerequisites, and recipes?
- How does Make determine if something needs rebuilding?

### Compiler Flags

- What does `-Wall` do? Why use it?
- What does `-O2` or `-O3` do?
- What does `-g` do? When do you use it?
- What does `-std=c99` or `-std=c11` do?
- What's the difference between warnings and errors?

### Build It: Multi-File Project with Makefile

Build a project split across multiple files:

**Requirements:**

1. Create three files:

**math_utils.h:**

```c
#ifndef MATH_UTILS_H
#define MATH_UTILS_H

int add(int a, int b);
int multiply(int a, int b);

#endif
```

**math_utils.c:**

```c
#include "math_utils.h"

int add(int a, int b) {
    return a + b;
}

int multiply(int a, int b) {
    return a * b;
}
```

**main.c:**

```c
#include <stdio.h>
#include "math_utils.h"

int main(void) {
    printf("5 + 3 = %d\n", add(5, 3));
    printf("5 * 3 = %d\n", multiply(5, 3));
    return 0;
}
```

2. Compile manually:

```bash
gcc -c math_utils.c
gcc -c main.c
gcc math_utils.o main.o -o program
```

3. Create a `Makefile`:

```makefile
CC = gcc
CFLAGS = -Wall -g

program: main.o math_utils.o
	$(CC) $(CFLAGS) main.o math_utils.o -o program

main.o: main.c math_utils.h
	$(CC) $(CFLAGS) -c main.c

math_utils.o: math_utils.c math_utils.h
	$(CC) $(CFLAGS) -c math_utils.c

clean:
	rm -f *.o program
```

4. Build with: `make`
5. Clean with: `make clean`

**Experiments:**

- Remove the header guard from `math_utils.h` and include it twice — what error?
- Change only `math_utils.c` — run `make` — what gets recompiled?
- Run `make` twice without changes — what happens?
- Use `gcc -E main.c` — see how `#include` expands
- Try `gcc -S math_utils.c` — examine the assembly
- Use different optimization levels — compare binary sizes

### Reflection Questions

1. **Process Understanding:**

   - Why separate compilation and linking?
   - What problem do object files solve?
   - Why not compile everything every time?

2. **Header Files:**

   - Why separate declarations and definitions?
   - What happens if you forget header guards?
   - Can you put function bodies in headers?

3. **Build Systems:**
   - How does Make save compilation time?
   - What determines dependency order?
   - When would you use other build systems?

---

# 🟡 PART 2: MEMORY FUNDAMENTALS

---

## Section 3: Variables, Types & Memory Layout

### The Problem

You declare `int x = 5`. Where does this value live? How much memory does it use? What happens when you assign it to another variable? Why do different types take different amounts of space?

**Understanding memory layout is fundamental to C.** Everything maps directly to machine memory.

### Understanding Memory

- What is RAM? How is it organized?
- What's a memory address? How is it represented?
- Your computer has 8GB of RAM. Can your program access all of it?
- What's a byte? Why do we measure memory in bytes?
- How is memory like a giant array?

### Types and Sizes

- Why does `char` exist if you have `int`?
- How many bytes is an `int`? Is it always the same?
- What's the difference between `int`, `long`, and `short`?
- Why does C have `signed` and `unsigned`?
- What values can `unsigned char` hold? What about `signed char`?
- How do you find the size of a type? (Hint: `sizeof`)

### Variable Storage

- You write `int x = 5` — where does this live in memory?
- What's the "stack"? What gets stored there?
- You declare `int x` in a function. What happens when the function returns?
- What's a "stack frame"?
- Why do local variables disappear after a function ends?

### Memory Layout of a Program

- Your compiled program has `.text`, `.data`, `.bss` sections. What are they?
- Where do global variables live?
- Where do string literals like `"hello"` live?
- Where does your code (instructions) live?
- What's the difference between initialized and uninitialized global variables?

### Type Conversions

- You assign `int x = 3.7` — what happens?
- You assign `char c = 300` — what's stored in `c`?
- What's "integer overflow"? When does it happen?
- What's the difference between implicit and explicit casting?
- Why might `int x = 1000000 * 1000000` overflow?

### Undefined Behavior

- You read an uninitialized variable. What value does it have?
- You write `int x; printf("%d", x);` — what prints?
- What is "undefined behavior"? Why is it dangerous?
- Why doesn't C initialize variables for you?
- What happens with undefined behavior — does it crash?

### Build It: Type Exploration Tool

Build a program to explore types and memory:

**Requirements:**

```c
#include <stdio.h>
#include <limits.h>

int main(void) {
    // 1. Print sizes of all basic types
    printf("Size of char: %zu bytes\n", sizeof(char));
    printf("Size of short: %zu bytes\n", sizeof(short));
    printf("Size of int: %zu bytes\n", sizeof(int));
    printf("Size of long: %zu bytes\n", sizeof(long));
    printf("Size of float: %zu bytes\n", sizeof(float));
    printf("Size of double: %zu bytes\n", sizeof(double));
    printf("Size of pointer: %zu bytes\n", sizeof(void*));

    // 2. Print ranges of types
    printf("\nchar range: %d to %d\n", CHAR_MIN, CHAR_MAX);
    printf("unsigned char range: 0 to %u\n", UCHAR_MAX);
    printf("int range: %d to %d\n", INT_MIN, INT_MAX);

    // 3. Experiment with addresses
    int x = 42;
    int y = 100;
    printf("\nAddress of x: %p\n", (void*)&x);
    printf("Address of y: %p\n", (void*)&y);
    printf("Difference: %ld bytes\n", (char*)&y - (char*)&x);

    // 4. Test overflow
    unsigned char c = 255;
    printf("\nBefore: %u\n", c);
    c = c + 1;
    printf("After +1: %u\n", c);

    // 5. Test uninitialized memory
    int uninitialized;
    printf("\nUninitialized value: %d\n", uninitialized);

    return 0;
}
```

**Experiments:**

- Declare variables in different orders — do addresses change?
- Print addresses of global vs local variables — what do you notice?
- Overflow an `int` — what happens?
- Compare `signed` vs `unsigned` overflow
- Use different optimization levels (`-O0` vs `-O3`) — does uninitialized behavior change?
- Print addresses of string literals — where do they live?

### Reflection Questions

1. **Memory Understanding:**

   - How do variables map to actual RAM?
   - Why do types have different sizes?
   - What determines variable addresses?

2. **Type System:**

   - Why does C need so many integer types?
   - When should you use `unsigned`?
   - What problems does undefined behavior cause?

3. **Deeper Questions:**
   - How does the compiler know where to put variables?
   - What's on the stack vs in registers?
   - Why is stack space limited?

---

## Section 4: Pointers - The Heart of C

### The Problem

You want to write a function that modifies its argument. You want to create a linked list. You want to return multiple values. You want to allocate memory dynamically. **All of these require pointers.**

Pointers are C's most powerful and most dangerous feature.

### Understanding Pointers

- What is a pointer?
- How is a pointer different from a regular variable?
- You write `int x = 5; int *p = &x;` — what do `&` and `*` mean?
- What does `p` contain? What does `*p` give you?
- What's the difference between the value and the address?

### Pointer Syntax

- What does `int *p` declare?
- What does `*p` (with existing pointer) do?
- What does `&x` do?
- How do you read `int *p` — "pointer to int" or "int star p"?
- What's the type of `&x` if `x` is `int`?

### Pointers and Functions

- You write `void func(int x)` and call it — does it modify the original?
- You write `void func(int *x)` — now what?
- Why do you need `scanf("%d", &x)` with the `&`?
- How do you return multiple values from a function?
- What's "pass by value" vs "pass by reference"?

### NULL Pointers

- What is `NULL`? Why does it exist?
- What happens if you dereference `NULL`?
- Why initialize pointers to `NULL`?
- How do you check if a pointer is valid?
- What's a "segmentation fault"? When does it happen?

### Pointer Arithmetic

- You have `int *p` pointing to an array. What does `p + 1` mean?
- Does `p + 1` add 1 byte or more?
- What's the relationship between pointers and arrays?
- How do you iterate through an array with a pointer?
- What happens if you go past the array bounds?

### Common Pointer Mistakes

- You return a pointer to a local variable. What goes wrong?
- You forget to initialize a pointer. What happens when you dereference it?
- You access freed memory. What's the danger?
- What's a "dangling pointer"?
- What's a "wild pointer"?

### Build It: Pointer Playground

Explore pointer behavior through experimentation:

**Requirements:**

```c
#include <stdio.h>

void modify_value(int x) {
    x = 100;
}

void modify_pointer(int *x) {
    *x = 100;
}

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main(void) {
    // 1. Basic pointer usage
    int x = 42;
    int *p = &x;

    printf("x = %d\n", x);
    printf("address of x = %p\n", (void*)&x);
    printf("p = %p\n", (void*)p);
    printf("*p = %d\n", *p);

    // 2. Modifying through pointer
    *p = 100;
    printf("After *p = 100, x = %d\n", x);

    // 3. Pass by value vs pointer
    int a = 10;
    modify_value(a);
    printf("After modify_value: %d\n", a);

    modify_pointer(&a);
    printf("After modify_pointer: %d\n", a);

    // 4. Swap function
    int m = 5, n = 10;
    printf("Before swap: m=%d, n=%d\n", m, n);
    swap(&m, &n);
    printf("After swap: m=%d, n=%d\n", m, n);

    // 5. NULL pointer
    int *null_ptr = NULL;
    if (null_ptr == NULL) {
        printf("null_ptr is NULL\n");
    }
    // Don't do this: *null_ptr = 5; // SEGFAULT!

    return 0;
}
```

**Experiments:**

- Try to dereference `NULL` — what happens?
- Return `&x` from a function and use it — undefined behavior!
- Use an uninitialized pointer — what happens?
- Make `p` point to an address you type manually like `0x1234` — crash!
- Compare pointer addresses — are they consistent?

### Reflection Questions

1. **Pointer Fundamentals:**

   - Why does C need pointers?
   - How are pointers different from references in other languages?
   - What problems do pointers solve?

2. **Common Pitfalls:**

   - Why are dangling pointers dangerous?
   - How do you avoid null pointer dereferences?
   - What causes segfaults?

3. **Deeper Understanding:**
   - What's actually in a pointer variable?
   - How does pointer arithmetic work at the bit level?
   - Why can pointers be so dangerous?

---

## Section 5: Arrays & Pointer Arithmetic

### The Problem

You need to store 1000 integers. Creating 1000 variables is insane. You need arrays. But in C, arrays and pointers are deeply related — understanding this relationship is critical.

### Arrays Basics

- What is an array?
- You write `int arr[5]` — how much memory is allocated?
- How do you access the first element? The last?
- Arrays start at index 0. Why?
- What happens if you access `arr[5]` in an array of size 5?

### Arrays and Pointers

- You write `int arr[5]`. What's the type of `arr`?
- What's the relationship between `arr` and `&arr[0]`?
- You write `int *p = arr` — is this valid?
- What's the difference between an array and a pointer?
- Why can you use `p[2]` even though `p` is a pointer?

### Pointer Arithmetic

- You have `int *p` pointing to `arr[0]`. What does `p + 1` point to?
- Why does `p + 1` move by 4 bytes (on most systems)?
- What's the relationship between `p[i]` and `*(p + i)`?
- How do you iterate through an array using only pointer arithmetic?
- What happens if your pointer goes past the array end?

### Array Decay

- You pass an array to a function. What actually gets passed?
- Why can't you return an array from a function?
- What does "array decay to pointer" mean?
- Can you do `sizeof(arr)` inside a function that receives an array?
- How do you pass array size to functions?

### Multi-Dimensional Arrays

- What is `int arr[3][4]`?
- How is it laid out in memory?
- How do you access element at row 1, column 2?
- What's the difference between `int arr[3][4]` and `int *arr[3]`?
- How do multi-dimensional arrays decay to pointers?

### Strings as Character Arrays

- What is a string in C?
- How is `"hello"` stored in memory?
- What's the null terminator `\0`?
- What's the difference between `char s[] = "hello"` and `char *s = "hello"`?
- Can you modify a string literal?

### Build It: Array and Pointer Operations

Implement common array operations using pointers:

**Requirements:**

```c
#include <stdio.h>
#include <string.h>

// Find sum using array indexing
int sum_array(int arr[], int size) {
    int sum = 0;
    for (int i = 0; i < size; i++) {
        sum += arr[i];
    }
    return sum;
}

// Find sum using pointer arithmetic
int sum_pointer(int *p, int size) {
    int sum = 0;
    int *end = p + size;
    while (p < end) {
        sum += *p;
        p++;
    }
    return sum;
}

// Reverse array in place
void reverse(int arr[], int size) {
    int *left = arr;
    int *right = arr + size - 1;
    while (left < right) {
        int temp = *left;
        *left = *right;
        *right = temp;
        left++;
        right--;
    }
}

// Copy string manually (like strcpy)
void my_strcpy(char *dest, const char *src) {
    while (*src != '\0') {
        *dest = *src;
        dest++;
        src++;
    }
    *dest = '\0';
}

// String length manually (like strlen)
int my_strlen(const char *s) {
    int len = 0;
    while (*s != '\0') {
        len++;
        s++;
    }
    return len;
}

int main(void) {
    // Test array operations
    int nums[] = {1, 2, 3, 4, 5};
    int size = sizeof(nums) / sizeof(nums[0]);

    printf("Sum (array): %d\n", sum_array(nums, size));
    printf("Sum (pointer): %d\n", sum_pointer(nums, size));

    reverse(nums, size);
    printf("Reversed: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", nums[i]);
    }
    printf("\n");

    // Test string operations
    char str1[50] = "Hello";
    char str2[50];

    my_strcpy(str2, str1);
    printf("Copied: %s\n", str2);
    printf("Length: %d\n", my_strlen(str1));

    // Demonstrate array decay
    printf("sizeof(nums) in main: %zu\n", sizeof(nums));
    // Inside functions, you can't do this!

    return 0;
}
```

**Experiments:**

- Access `nums[100]` — what happens? (Undefined behavior!)
- Print pointer addresses while iterating — see the pattern
- Try to modify a string literal — what happens?
- Compare your `my_strlen` with the standard `strlen`
- Use `sizeof` on arrays vs pointers — see the difference
- Create a 2D array and iterate with pointer arithmetic

### Reflection Questions

1. **Arrays and Pointers:**

   - Why does array indexing work on pointers?
   - What gets lost when an array decays to a pointer?
   - When should you use `[]` vs pointer arithmetic?

2. **Memory Layout:**

   - How are arrays stored in contiguous memory?
   - How does the compiler know where `arr[3]` is?
   - Why is `*(arr + i)` the same as `arr[i]`?

3. **Strings:**
   - Why do strings need the null terminator?
   - What problems arise from missing `\0`?
   - How do string functions know when to stop?

---

# 🔵 PART 3: MANUAL MEMORY MANAGEMENT

---

## Section 6: Dynamic Memory Allocation

### The Problem

You write `int arr[1000]` but you only need 10 elements. Waste! Or you need 10000 elements but declared 1000. Not enough! **You need memory that can grow and shrink at runtime.**

That's what `malloc` and `free` are for.

### Understanding Dynamic Memory

- What's the difference between stack and heap memory?
- Why can't you just declare arrays of any size?
- What is the heap? How is it different from the stack?
- Who manages heap memory?
- Why do you need to manually free heap memory?

### malloc and free

- What does `malloc(10)` do?
- What does `malloc` return?
- Why do you cast the return value: `(int*)malloc(10 * sizeof(int))`?
- What happens if `malloc` fails?
- What does `free(ptr)` do?
- What happens if you forget to `free`?

### Common Memory Functions

- What's the difference between `malloc`, `calloc`, and `realloc`?
- When should you use `calloc` instead of `malloc`?
- How do you resize allocated memory?
- What does `realloc` return? Can it fail?
- How do you free memory allocated by `realloc`?

### Memory Leaks

- What is a memory leak?
- You `malloc` in a loop but never `free`. What happens?
- How do you detect memory leaks?
- What's the impact of a memory leak on a long-running program?
- Can memory leaks crash your program?

### Double Free and Use-After-Free

- What's a "double free"? What happens?
- What's "use-after-free"? Why is it dangerous?
- How do you prevent double free?
- Should you set pointers to `NULL` after freeing?

### Memory Debugging Tools

- What is Valgrind? How do you use it?
- How do you detect memory leaks with Valgrind?
- What's AddressSanitizer?
- How do you enable it: `gcc -fsanitize=address`?
- What errors can these tools catch?

### Build It: Dynamic Array

Build a growable array like `std::vector` in C++:

**Requirements:**

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct {
    int *data;
    int size;
    int capacity;
} DynamicArray;

DynamicArray* create_array(int initial_capacity) {
    DynamicArray *arr = malloc(sizeof(DynamicArray));
    if (!arr) return NULL;

    arr->data = malloc(initial_capacity * sizeof(int));
    if (!arr->data) {
        free(arr);
        return NULL;
    }

    arr->size = 0;
    arr->capacity = initial_capacity;
    return arr;
}

void push(DynamicArray *arr, int value) {
    if (arr->size == arr->capacity) {
        int new_capacity = arr->capacity * 2;
        int *new_data = realloc(arr->data, new_capacity * sizeof(int));
        if (!new_data) {
            printf("Realloc failed!\n");
            return;
        }
        arr->data = new_data;
        arr->capacity = new_capacity;
        printf("Resized to capacity: %d\n", new_capacity);
    }
    arr->data[arr->size++] = value;
}

int get(DynamicArray *arr, int index) {
    if (index < 0 || index >= arr->size) {
        printf("Index out of bounds!\n");
        return -1;
    }
    return arr->data[index];
}

void destroy_array(DynamicArray *arr) {
    free(arr->data);
    free(arr);
}

int main(void) {
    DynamicArray *arr = create_array(2);

    // Add elements, watch it grow
    for (int i = 0; i < 10; i++) {
        printf("Pushing %d\n", i);
        push(arr, i * 10);
    }

    // Print all elements
    printf("\nArray contents:\n");
    for (int i = 0; i < arr->size; i++) {
        printf("%d ", get(arr, i));
    }
    printf("\n");

    printf("Size: %d, Capacity: %d\n", arr->size, arr->capacity);

    destroy_array(arr);
    return 0;
}
```

**Experiments:**

- Forget to `free` — run with Valgrind — see the leak!
- Double-free the array — what happens?
- Access freed memory — use AddressSanitizer
- Don't check if `malloc` returns `NULL` — cause allocation failure
- Forget to update `capacity` after `realloc`
- Add a `pop` function that removes the last element

### Reflection Questions

1. **Dynamic Memory:**

   - Why can't everything be on the stack?
   - When should you use heap allocation?
   - What's the cost of `malloc` and `free`?

2. **Memory Safety:**

   - How do you avoid memory leaks?
   - How do you avoid use-after-free?
   - Why are these bugs so dangerous?

3. **Tool Usage:**
   - How does Valgrind detect leaks?
   - What can AddressSanitizer catch?
   - Should you always use these tools?

---

## Section 7: Memory Leaks & Debugging

### The Problem

Your program runs fine for 10 minutes, then slows down, then crashes. You're leaking memory. Or you get a random crash — use-after-free. Or corrupted data — buffer overflow. **Memory bugs are the hardest to debug.**

### Identifying Memory Problems

- Your program's memory usage keeps growing. What's happening?
- What tools show memory usage? (`top`, `ps`, `htop`)
- You get a segfault. What are the possible causes?
- How do you create a minimal test case?
- What information does a core dump provide?

### Using Valgrind

- How do you run Valgrind on your program?
- What does "definitely lost" mean in Valgrind output?
- What does "possibly lost" mean?
- How do you track the origin of leaked memory?
- What are "invalid reads" and "invalid writes"?

### Using AddressSanitizer

- How do you compile with AddressSanitizer?
- What errors does it catch at runtime?
- How is it different from Valgrind?
- Which is faster? Which catches more?
- Can you use both?

### Common Memory Bug Patterns

- Buffer overflow: `arr[10]` when size is 10
- Off-by-one: `for (i = 0; i <= size; i++)`
- Returning stack address: `return &local_var;`
- Use-after-free: access after `free(ptr)`
- Double-free: calling `free(ptr)` twice
- Memory leak: allocate but never free

### Defensive Programming

- How do you check if `malloc` succeeded?
- Should you initialize allocated memory?
- Should you set pointers to `NULL` after free?
- How do you validate pointer arguments?
- What's an assertion? When should you use `assert`?

### Build It: Memory Leak Detector

Create a simple memory tracking system:

**Requirements:**

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct Allocation {
    void *ptr;
    size_t size;
    const char *file;
    int line;
    struct Allocation *next;
} Allocation;

Allocation *allocations = NULL;
int total_allocated = 0;
int total_freed = 0;

void* tracked_malloc(size_t size, const char *file, int line) {
    void *ptr = malloc(size);
    if (!ptr) return NULL;

    Allocation *alloc = malloc(sizeof(Allocation));
    alloc->ptr = ptr;
    alloc->size = size;
    alloc->file = file;
    alloc->line = line;
    alloc->next = allocations;
    allocations = alloc;

    total_allocated += size;
    printf("[ALLOC] %zu bytes at %s:%d\n", size, file, line);
    return ptr;
}

void tracked_free(void *ptr, const char *file, int line) {
    if (!ptr) return;

    Allocation **current = &allocations;
    while (*current) {
        if ((*current)->ptr == ptr) {
            Allocation *to_free = *current;
            *current = (*current)->next;

            total_freed += to_free->size;
            printf("[FREE] %zu bytes at %s:%d\n", to_free->size, file, line);

            free(to_free);
            free(ptr);
            return;
        }
        current = &(*current)->next;
    }

    printf("[ERROR] Freeing untracked pointer at %s:%d\n", file, line);
}

void print_leaks(void) {
    printf("\n=== Memory Report ===\n");
    printf("Total allocated: %d bytes\n", total_allocated);
    printf("Total freed: %d bytes\n", total_freed);
    printf("Leaked: %d bytes\n", total_allocated - total_freed);

    if (allocations) {
        printf("\nMemory leaks detected:\n");
        for (Allocation *a = allocations; a; a = a->next) {
            printf("  %zu bytes at %s:%d\n", a->size, a->file, a->line);
        }
    } else {
        printf("\nNo memory leaks! ✓\n");
    }
}

#define MALLOC(size) tracked_malloc(size, __FILE__, __LINE__)
#define FREE(ptr) tracked_free(ptr, __FILE__, __LINE__)

// Test program
int main(void) {
    int *a = MALLOC(10 * sizeof(int));
    int *b = MALLOC(20 * sizeof(int));
    char *s = MALLOC(100);

    FREE(a);
    // Intentionally leak b and s

    print_leaks();
    return 0;
}
```

**Experiments:**

- Run without freeing anything — see all leaks
- Free everything properly — see "No leaks"
- Try double-freeing — see the error message
- Add more tracking info (timestamps, stack traces)
- Track peak memory usage
- Add a check for memory usage limits

### Reflection Questions

1. **Debugging Skills:**

   - How do you systematically find memory bugs?
   - What's your debugging workflow?
   - When should you use which tool?

2. **Prevention:**

   - How do you write leak-free code?
   - What coding patterns prevent bugs?
   - How do you review code for memory safety?

3. **Trade-offs:**
   - Should you always use tracking?
   - What's the performance cost?
   - When is manual management worth it?

---

## Section 8: Stack vs Heap - Understanding the Trade-offs

### The Problem

You can allocate on the stack (automatic) or heap (manual). Stack is fast but limited. Heap is flexible but requires management. **Choosing wrong can cause stack overflow or memory fragmentation.**

### Understanding Stack Allocation

- What happens when you declare `int x = 5` in a function?
- How fast is stack allocation compared to heap?
- Why is stack allocation automatic?
- What's the typical stack size limit? (1-8MB)
- What causes a stack overflow?

### Understanding Heap Allocation

- Why use heap when stack is faster?
- What problems can heap allocation solve that stack can't?
- What's memory fragmentation?
- How does the heap allocator manage free memory?
- What's the performance cost of `malloc`?

### Stack Overflow

- You write a recursive function with no base case. What happens?
- You declare `int huge[10000000]`. What happens?
- How do you detect stack overflow?
- Can you increase stack size?
- How do you avoid stack overflow?

### When to Use Each

- You need to store 1MB of data. Stack or heap?
- You need data to persist after function returns. Stack or heap?
- You need maximum performance. Stack or heap?
- You don't know the size at compile time. Stack or heap?
- You're implementing recursion. What do you watch for?

### Variable-Length Arrays (VLAs)

- What's a VLA? How is `int arr[n]` different from `int arr[10]`?
- Are VLAs on stack or heap?
- Why are VLAs controversial?
- What are the dangers of VLAs?
- Should you use them?

### Build It: Stack vs Heap Benchmark

Compare performance and observe limits:

**Requirements:**

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define ITERATIONS 1000000

// Stack allocation benchmark
void stack_allocation_test(void) {
    clock_t start = clock();

    for (int i = 0; i < ITERATIONS; i++) {
        int arr[100];
        arr[0] = i; // Use it to prevent optimization
    }

    clock_t end = clock();
    double time = (double)(end - start) / CLOCKS_PER_SEC;
    printf("Stack allocation: %.4f seconds\n", time);
}

// Heap allocation benchmark
void heap_allocation_test(void) {
    clock_t start = clock();

    for (int i = 0; i < ITERATIONS; i++) {
        int *arr = malloc(100 * sizeof(int));
        arr[0] = i;
        free(arr);
    }

    clock_t end = clock();
    double time = (double)(end - start) / CLOCKS_PER_SEC;
    printf("Heap allocation: %.4f seconds\n", time);
}

// Recursive function that uses stack
int factorial_recursive(int n) {
    if (n <= 1) return 1;
    return n * factorial_recursive(n - 1);
}

// Demonstrate stack growth
void show_stack_addresses(int depth) {
    int x;
    printf("Depth %d: stack address = %p\n", depth, (void*)&x);
    if (depth < 5) {
        show_stack_addresses(depth + 1);
    }
}

int main(void) {
    printf("=== Performance Comparison ===\n");
    stack_allocation_test();
    heap_allocation_test();

    printf("\n=== Stack Growth ===\n");
    show_stack_addresses(0);

    printf("\n=== Recursion Test ===\n");
    printf("factorial(10) = %d\n", factorial_recursive(10));

    // Uncomment to cause stack overflow:
    // printf("factorial(100000) = %d\n", factorial_recursive(100000));

    return 0;
}
```

**Experiments:**

- Increase array sizes — when does heap become worth it?
- Try allocating massive arrays on stack — observe crash
- Enable recursion with large N — see stack overflow
- Use Valgrind to see heap allocations
- Compile with optimizations — see if results change
- Create a VLA and test its limits

### Reflection Questions

1. **Performance:**

   - Why is stack so much faster?
   - When is heap allocation acceptable?
   - What's the cost of malloc/free?

2. **Limits:**

   - How do you know if you'll overflow the stack?
   - What strategies avoid stack issues?
   - When must you use heap?

3. **Design Decisions:**
   - How do you choose between stack and heap?
   - What are the trade-offs?
   - When is performance critical enough to matter?

---

# 🟣 PART 4: STRUCTURED DATA

---

## Section 9: Structs & Custom Types

### The Problem

You need to represent a complex entity — a person with name, age, address. Using separate variables is messy. Arrays only work for same-type data. **You need custom compound types.**

That's what `struct` is for.

### Understanding Structs

- What is a struct?
- How is a struct different from an array?
- You have related data of different types. Why use a struct?
- What does "compound type" mean?
- How do structs compare to objects in other languages?

### Defining and Using Structs

- How do you define a struct?
- What's the difference between `struct Point` and `Point`?
- What's `typedef`? Why use it?
- How do you declare a struct variable?
- How do you access struct members?

### Struct Memory Layout

- You have `struct { char c; int x; }`. How many bytes does it take?
- What is "padding"? Why does the compiler add it?
- What's "memory alignment"?
- How do you find the size of a struct?
- Can you control struct packing?

### Structs and Pointers

- How do you create a pointer to a struct?
- What's the difference between `.` and `->`?
- Why does `->` exist?
- How do you pass structs to functions efficiently?
- Should you pass structs by value or pointer?

### Nested Structs

- Can you have structs inside structs?
- How do you access nested struct members?
- What are the memory implications?
- When should you nest vs have separate structs?

### Arrays of Structs

- How do you create an array of structs?
- How do you iterate through it?
- How much memory does an array of 100 structs take?
- Can you have variable-sized structs in an array?

### Build It: Student Database

Create a simple database using structs:

**Requirements:**

```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

#define MAX_NAME 50
#define MAX_STUDENTS 100

typedef struct {
    int id;
    char name[MAX_NAME];
    int age;
    float gpa;
} Student;

typedef struct {
    Student students[MAX_STUDENTS];
    int count;
} Database;

void init_database(Database *db) {
    db->count = 0;
}

void add_student(Database *db, int id, const char *name, int age, float gpa) {
    if (db->count >= MAX_STUDENTS) {
        printf("Database full!\n");
        return;
    }

    Student *s = &db->students[db->count];
    s->id = id;
    strncpy(s->name, name, MAX_NAME - 1);
    s->name[MAX_NAME - 1] = '\0';
    s->age = age;
    s->gpa = gpa;

    db->count++;
    printf("Added student: %s\n", name);
}

Student* find_student(Database *db, int id) {
    for (int i = 0; i < db->count; i++) {
        if (db->students[i].id == id) {
            return &db->students[i];
        }
    }
    return NULL;
}

void print_student(Student *s) {
    printf("ID: %d, Name: %s, Age: %d, GPA: %.2f\n",
           s->id, s->name, s->age, s->gpa);
}

void print_all(Database *db) {
    printf("\n=== All Students ===\n");
    for (int i = 0; i < db->count; i++) {
        print_student(&db->students[i]);
    }
}

float average_gpa(Database *db) {
    if (db->count == 0) return 0.0;

    float sum = 0.0;
    for (int i = 0; i < db->count; i++) {
        sum += db->students[i].gpa;
    }
    return sum / db->count;
}

int main(void) {
    Database db;
    init_database(&db);

    add_student(&db, 1, "Alice", 20, 3.8);
    add_student(&db, 2, "Bob", 21, 3.5);
    add_student(&db, 3, "Charlie", 19, 3.9);

    print_all(&db);

    printf("\nAverage GPA: %.2f\n", average_gpa(&db));

    Student *found = find_student(&db, 2);
    if (found) {
        printf("\nFound: ");
        print_student(found);
    }

    printf("\nSize of Student: %zu bytes\n", sizeof(Student));
    printf("Size of Database: %zu bytes\n", sizeof(Database));

    return 0;
}
```

**Experiments:**

- Add a `struct Address` with street, city, zip
- Make it a dynamic database with malloc
- Add sorting by GPA or name
- Add delete student functionality
- Measure padding in structs with different orderings
- Try different struct member arrangements — see size changes

### Reflection Questions

1. **Struct Basics:**

   - Why are structs essential in C?
   - How do they organize code?
   - What problems do they solve?

2. **Memory:**

   - Why does padding exist?
   - How does alignment affect performance?
   - Can you predict struct sizes?

3. **Design:**
   - When should you pass by value vs pointer?
   - How do you design good struct APIs?
   - What makes structs maintainable?

---

## Section 10: Building Data Structures from Scratch

### The Problem

C has no built-in linked lists, hash tables, or trees. You need these for real programs. **You must build them yourself using structs and pointers.**

### Linked Lists

- What is a linked list?
- Why use linked lists instead of arrays?
- What's a node? What does it contain?
- How do you insert at the head? The tail?
- How do you traverse a linked list?
- How do you delete a node?
- What's the time complexity of operations?

### Doubly Linked Lists

- What's the difference from singly linked?
- Why have `prev` and `next` pointers?
- What operations become easier?
- What's the memory cost?

### Stacks

- What is a stack? (LIFO)
- How do you implement it with an array?
- How do you implement it with a linked list?
- What's push? What's pop?
- What happens when you pop from empty?

### Queues

- What is a queue? (FIFO)
- How do you implement with a circular buffer?
- How do you implement with a linked list?
- What's enqueue? What's dequeue?
- What's the head? What's the tail?

### Build It: Linked List Implementation

Build a complete linked list from scratch:

**Requirements:**

```c
#include <stdio.h>
#include <stdlib.h>

typedef struct Node {
    int data;
    struct Node *next;
} Node;

typedef struct {
    Node *head;
    int size;
} LinkedList;

LinkedList* create_list(void) {
    LinkedList *list = malloc(sizeof(LinkedList));
    list->head = NULL;
    list->size = 0;
    return list;
}

void insert_head(LinkedList *list, int data) {
    Node *new_node = malloc(sizeof(Node));
    new_node->data = data;
    new_node->next = list->head;
    list->head = new_node;
    list->size++;
}

void insert_tail(LinkedList *list, int data) {
    Node *new_node = malloc(sizeof(Node));
    new_node->data = data;
    new_node->next = NULL;

    if (list->head == NULL) {
        list->head = new_node;
    } else {
        Node *current = list->head;
        while (current->next != NULL) {
            current = current->next;
        }
        current->next = new_node;
    }
    list->size++;
}

void delete_value(LinkedList *list, int data) {
    if (list->head == NULL) return;

    // Delete head if it matches
    if (list->head->data == data) {
        Node *temp = list->head;
        list->head = list->head->next;
        free(temp);
        list->size--;
        return;
    }

    // Find and delete
    Node *current = list->head;
    while (current->next != NULL) {
        if (current->next->data == data) {
            Node *temp = current->next;
            current->next = current->next->next;
            free(temp);
            list->size--;
            return;
        }
        current = current->next;
    }
}

int find(LinkedList *list, int data) {
    Node *current = list->head;
    int index = 0;
    while (current != NULL) {
        if (current->data == data) {
            return index;
        }
        current = current->next;
        index++;
    }
    return -1;
}

void print_list(LinkedList *list) {
    printf("List (%d elements): ", list->size);
    Node *current = list->head;
    while (current != NULL) {
        printf("%d -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");
}

void destroy_list(LinkedList *list) {
    Node *current = list->head;
    while (current != NULL) {
        Node *next = current->next;
        free(current);
        current = next;
    }
    free(list);
}

int main(void) {
    LinkedList *list = create_list();

    insert_head(list, 10);
    insert_head(list, 20);
    insert_tail(list, 5);
    insert_tail(list, 15);

    print_list(list);

    printf("Find 5: index %d\n", find(list, 5));
    printf("Find 99: index %d\n", find(list, 99));

    delete_value(list, 20);
    print_list(list);

    destroy_list(list);
    return 0;
}
```

**Experiments:**

- Add `insert_at_index(list, index, data)`
- Add `reverse()` to reverse the list
- Implement a doubly-linked list
- Build a stack using the linked list
- Build a queue using the linked list
- Add sorting functionality
- Check for memory leaks with Valgrind

### Reflection Questions

1. **Data Structures:**

   - Why are they fundamental?
   - What problems do they solve?
   - When do you use which structure?

2. **Implementation:**

   - What are the edge cases?
   - How do you prevent memory leaks?
   - What's the complexity of each operation?

3. **Trade-offs:**
   - Linked list vs array — when to use which?
   - Memory overhead of pointers?
   - Cache performance implications?

---

## Section 11: Function Pointers & Callbacks

### The Problem

You want to sort an array but allow custom comparison. You want to implement a generic filter. You want event handlers. **You need to pass functions as arguments.**

That's what function pointers are for.

### Understanding Function Pointers

- What is a function pointer?
- Functions are code. Where does code live in memory?
- How do you declare a function pointer?
- How do you assign a function to a pointer?
- How do you call through a function pointer?

### Syntax

- How do you read `void (*func)(int)` ?
- What's the difference between `void *func()` and `void (*func)()` ?
- How do you typedef a function pointer?
- Can you have arrays of function pointers?

### Callbacks

- What is a callback?
- Why pass functions as arguments?
- How do generic libraries use callbacks?
- What's `qsort` and how does it work?
- How do you pass extra data to callbacks?

### Function Pointers in Structs

- Can you store function pointers in structs?
- How is this like methods in OOP?
- How do you simulate polymorphism?
- What are virtual function tables?

### Build It: Generic Sorting with Callbacks

Implement sorting with custom comparisons:

**Requirements:**

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Function pointer type for comparison
typedef int (*CompareFunc)(const void*, const void*);

// Generic bubble sort with callback
void bubble_sort(void *array, int n, size_t size, CompareFunc compare) {
    char *arr = (char*)array;
    char *temp = malloc(size);

    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            void *a = arr + j * size;
            void *b = arr + (j + 1) * size;

            if (compare(a, b) > 0) {
                memcpy(temp, a, size);
                memcpy(a, b, size);
                memcpy(b, temp, size);
            }
        }
    }

    free(temp);
}

// Compare functions
int compare_ints(const void *a, const void *b) {
    return *(int*)a - *(int*)b;
}

int compare_ints_desc(const void *a, const void *b) {
    return *(int*)b - *(int*)a;
}

typedef struct {
    char name[50];
    int age;
} Person;

int compare_persons_by_age(const void *a, const void *b) {
    Person *p1 = (Person*)a;
    Person *p2 = (Person*)b;
    return p1->age - p2->age;
}

int compare_persons_by_name(const void *a, const void *b) {
    Person *p1 = (Person*)a;
    Person *p2 = (Person*)b;
    return strcmp(p1->name, p2->name);
}

// Generic filter
void filter(int *array, int n, int (*predicate)(int)) {
    printf("Filtered: ");
    for (int i = 0; i < n; i++) {
        if (predicate(array[i])) {
            printf("%d ", array[i]);
        }
    }
    printf("\n");
}

int is_even(int x) { return x % 2 == 0; }
int is_positive(int x) { return x > 0; }

int main(void) {
    // Sort integers
    int nums[] = {5, 2, 8, 1, 9};
    int n = sizeof(nums) / sizeof(nums[0]);

    printf("Original: ");
    for (int i = 0; i < n; i++) printf("%d ", nums[i]);
    printf("\n");

    bubble_sort(nums, n, sizeof(int), compare_ints);
    printf("Sorted ascending: ");
    for (int i = 0; i < n; i++) printf("%d ", nums[i]);
    printf("\n");

    bubble_sort(nums, n, sizeof(int), compare_ints_desc);
    printf("Sorted descending: ");
    for (int i = 0; i < n; i++) printf("%d ", nums[i]);
    printf("\n\n");

    // Sort persons
    Person people[] = {
        {"Alice", 30},
        {"Bob", 25},
        {"Charlie", 35}
    };
    int p = sizeof(people) / sizeof(people[0]);

    bubble_sort(people, p, sizeof(Person), compare_persons_by_age);
    printf("Sorted by age:\n");
    for (int i = 0; i < p; i++) {
        printf("  %s: %d\n", people[i].name, people[i].age);
    }

    bubble_sort(people, p, sizeof(Person), compare_persons_by_name);
    printf("Sorted by name:\n");
    for (int i = 0; i < p; i++) {
        printf("  %s: %d\n", people[i].name, people[i].age);
    }

    // Test filter
    int vals[] = {-2, 5, -1, 8, 0, 3};
    filter(vals, 6, is_even);
    filter(vals, 6, is_positive);

    return 0;
}
```

**Experiments:**

- Use standard library `qsort` — compare with yours
- Create a function dispatch table (array of function pointers)
- Build a simple calculator with operation selection
- Implement map/reduce with callbacks
- Create an event system with callbacks
- Build a plugin system

### Reflection Questions

1. **Function Pointers:**

   - Why are they powerful?
   - How do they enable generic code?
   - What's the syntax complexity?

2. **Callbacks:**

   - When should you use them?
   - How do they compare to other patterns?
   - What are the downsides?

3. **Design:**
   - How do you design callback APIs?
   - How do you pass context/state?
   - When is this pattern appropriate?

---

# 🟠 PART 5: STRINGS & FILE I/O

---

## Section 12: String Manipulation - The C Way

### The Problem

Other languages have string objects with methods. C has `char` arrays with a null terminator. **Every string operation requires manual memory management and careful bounds checking.**

### Understanding C Strings

- What is a C string?
- Why do strings need `\0`?
- What's the difference between `'a'` and `"a"`?
- How much memory does `"hello"` take?
- Can you modify string literals?

### String Functions

- What does `strlen` do? How does it work?
- What's the difference between `strcpy` and `strncpy`?
- Why is `strcpy` dangerous?
- What does `strcmp` return?
- How do you concatenate strings safely?

### Buffer Overflows

- You copy a 20-char string into a 10-char buffer. What happens?
- What's a buffer overflow?
- Why are they security vulnerabilities?
- How do you prevent them?
- What are "safe" string functions?

### String Manipulation

- How do you find a substring?
- How do you split a string by delimiter?
- How do you convert string to int?
- How do you format strings?
- What's the difference between `sprintf` and `snprintf`?

### Build It: Safe String Library

Build safer string functions:

**Requirements:**

```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

// Safe string copy with explicit size
void safe_strcpy(char *dest, const char *src, size_t dest_size) {
    if (dest_size == 0) return;

    size_t i;
    for (i = 0; i < dest_size - 1 && src[i] != '\0'; i++) {
        dest[i] = src[i];
    }
    dest[i] = '\0';
}

// Safe concatenation
void safe_strcat(char *dest, const char *src, size_t dest_size) {
    size_t dest_len = strlen(dest);
    if (dest_len >= dest_size - 1) return;

    safe_strcpy(dest + dest_len, src, dest_size - dest_len);
}

// Trim whitespace
void trim(char *str) {
    // Trim leading
    char *start = str;
    while (isspace(*start)) start++;

    if (start != str) {
        memmove(str, start, strlen(start) + 1);
    }

    // Trim trailing
    char *end = str + strlen(str) - 1;
    while (end > str && isspace(*end)) {
        *end = '\0';
        end--;
    }
}

// String tokenizer (like strtok but safer)
char* tokenize(char *str, const char *delim, char **saveptr) {
    if (str != NULL) {
        *saveptr = str;
    }

    if (*saveptr == NULL) return NULL;

    // Skip leading delimiters
    *saveptr += strspn(*saveptr, delim);
    if (**saveptr == '\0') return NULL;

    // Find end of token
    char *token_start = *saveptr;
    *saveptr += strcspn(*saveptr, delim);

    if (**saveptr != '\0') {
        **saveptr = '\0';
        (*saveptr)++;
    } else {
        *saveptr = NULL;
    }

    return token_start;
}

// Convert string to uppercase
void to_upper(char *str) {
    for (int i = 0; str[i]; i++) {
        str[i] = toupper(str[i]);
    }
}

// Count word occurrences
int count_words(const char *str) {
    int count = 0;
    int in_word = 0;

    while (*str) {
        if (isspace(*str)) {
            in_word = 0;
        } else if (!in_word) {
            in_word = 1;
            count++;
        }
        str++;
    }

    return count;
}

int main(void) {
    // Test safe copy
    char dest[10];
    safe_strcpy(dest, "Hello, World!", sizeof(dest));
    printf("Truncated: %s\n", dest);

    // Test safe concat
    char buffer[20] = "Hello";
    safe_strcat(buffer, " World", sizeof(buffer));
    printf("Concatenated: %s\n", buffer);

    // Test trim
    char str1[] = "  hello world  ";
    trim(str1);
    printf("Trimmed: '%s'\n", str1);

    // Test tokenize
    char str2[] = "one,two,three,four";
    char *saveptr;
    char *token = tokenize(str2, ",", &saveptr);
    printf("Tokens: ");
    while (token) {
        printf("%s ", token);
        token = tokenize(NULL, ",", &saveptr);
    }
    printf("\n");

    // Test uppercase
    char str3[] = "hello";
    to_upper(str3);
    printf("Uppercase: %s\n", str3);

    // Test word count
    printf("Words in 'hello world foo bar': %d\n",
           count_words("hello world foo bar"));

    return 0;
}
```

**Experiments:**

- Deliberately overflow a buffer — see the crash
- Use `strcpy` vs `strncpy` — understand the difference
- Modify string literals — see the error
- Parse CSV data with your tokenizer
- Build a simple text processor
- Implement `strstr` (find substring) yourself

### Reflection Questions

1. **C Strings:**

   - Why are they error-prone?
   - What makes them dangerous?
   - How do modern languages improve on this?

2. **Safety:**

   - How do you write safe string code?
   - What functions should you avoid?
   - How do you prevent overflows?

3. **Design:**
   - How do you design string APIs?
   - When should you return new strings vs modify?
   - How do you handle errors?

---

## Section 13: File Operations & Binary I/O

### The Problem

You need to persist data. Read configuration. Process large files. Log messages. **File I/O is essential but has many failure modes.**

### Understanding File I/O

- What's a file?
- What's a file descriptor?
- What's a `FILE*` pointer?
- How does buffering work?
- When is data actually written?

### Opening and Closing Files

- How do you open a file?
- What do "r", "w", "a" modes mean?
- What's the difference between "r" and "r+"?
- Why must you check if `fopen` succeeded?
- What happens if you forget to `fclose`?

### Reading and Writing Text

- How do you read a line from a file?
- What's the difference between `fgets`, `fscanf`, and `fread`?
- How do you write to a file?
- How do you append to a file?
- How do you read until EOF?

### Binary I/O

- What's the difference between text and binary mode?
- When should you use binary mode?
- How do you write structs to files?
- How do you read structs back?
- What are portability concerns?

### Error Handling

- How do you check for errors?
- What's `ferror` and `feof`?
- What's `perror` and `strerror`?
- How do you handle file not found?
- How do you handle permission denied?

### Build It: File Processing Utilities

Build practical file tools:

**Requirements:**

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Copy file
int copy_file(const char *src, const char *dest) {
    FILE *in = fopen(src, "rb");
    if (!in) {
        perror("fopen source");
        return -1;
    }

    FILE *out = fopen(dest, "wb");
    if (!out) {
        perror("fopen dest");
        fclose(in);
        return -1;
    }

    char buffer[4096];
    size_t bytes;
    while ((bytes = fread(buffer, 1, sizeof(buffer), in)) > 0) {
        if (fwrite(buffer, 1, bytes, out) != bytes) {
            perror("fwrite");
            fclose(in);
            fclose(out);
            return -1;
        }
    }

    fclose(in);
    fclose(out);
    return 0;
}

// Count lines in file
int count_lines(const char *filename) {
    FILE *f = fopen(filename, "r");
    if (!f) {
        perror("fopen");
        return -1;
    }

    int count = 0;
    char ch;
    while ((ch = fgetc(f)) != EOF) {
        if (ch == '\n') count++;
    }

    fclose(f);
    return count;
}

// Read entire file into string
char* read_entire_file(const char *filename) {
    FILE *f = fopen(filename, "r");
    if (!f) {
        perror("fopen");
        return NULL;
    }

    // Get file size
    fseek(f, 0, SEEK_END);
    long size = ftell(f);
    fseek(f, 0, SEEK_SET);

    // Allocate buffer
    char *content = malloc(size + 1);
    if (!content) {
        fclose(f);
        return NULL;
    }

    // Read file
    size_t read = fread(content, 1, size, f);
    content[read] = '\0';

    fclose(f);
    return content;
}

// Write array to binary file
typedef struct {
    int id;
    char name[50];
    float value;
} Record;

int write_records(const char *filename, Record *records, int count) {
    FILE *f = fopen(filename, "wb");
    if (!f) {
        perror("fopen");
        return -1;
    }

    size_t written = fwrite(records, sizeof(Record), count, f);
    fclose(f);

    return written == count ? 0 : -1;
}

int read_records(const char *filename, Record **records, int *count) {
    FILE *f = fopen(filename, "rb");
    if (!f) {
        perror("fopen");
        return -1;
    }

    // Get count
    fseek(f, 0, SEEK_END);
    *count = ftell(f) / sizeof(Record);
    fseek(f, 0, SEEK_SET);

    // Allocate and read
    *records = malloc(*count * sizeof(Record));
    size_t read = fread(*records, sizeof(Record), *count, f);

    fclose(f);
    return read == *count ? 0 : -1;
}

int main(void) {
    // Test file copy
    FILE *test = fopen("test.txt", "w");
    fprintf(test, "Line 1\nLine 2\nLine 3\n");
    fclose(test);

    copy_file("test.txt", "copy.txt");
    printf("Lines in test.txt: %d\n", count_lines("test.txt"));

    // Test read entire file
    char *content = read_entire_file("test.txt");
    if (content) {
        printf("File contents:\n%s", content);
        free(content);
    }

    // Test binary I/O
    Record records[] = {
        {1, "Alice", 3.8},
        {2, "Bob", 3.5},
        {3, "Charlie", 3.9}
    };

    write_records("data.bin", records, 3);

    Record *read_recs;
    int count;
    if (read_records("data.bin", &read_recs, &count) == 0) {
        printf("\nRead %d records:\n", count);
        for (int i = 0; i < count; i++) {
            printf("%d: %s (%.2f)\n",
                   read_recs[i].id,
                   read_recs[i].name,
                   read_recs[i].value);
        }
        free(read_recs);
    }

    return 0;
}
```

**Experiments:**

- Read a large file line by line
- Parse CSV files
- Build a simple database with binary files
- Implement file search (grep-like)
- Add error recovery
- Handle concurrent file access

### Reflection Questions

1. **File I/O:**

   - When should you use text vs binary?
   - What are buffering trade-offs?
   - How do you handle errors?

2. **Performance:**

   - How does buffer size affect speed?
   - When should you use mmap?
   - What about memory-mapped files?

3. **Design:**
   - How do you design file formats?
   - What makes formats portable?
   - How do you version file formats?

---

## Section 14: Command-Line Arguments & Environment

### The Problem

Your program needs input from the user. It needs configuration. It needs to act like a real Unix tool. **Understanding argv, argc, and environment is essential.**

### Command-Line Arguments

- What are `argc` and `argv`?
- Why is `main` defined as `int main(int argc, char *argv[])`?
- What's `argv[0]`? Why is it special?
- How do you iterate through arguments?
- How do you parse flags like `-o output.txt`?

### Environment Variables

- What are environment variables?
- How do you read them in C?
- What's `getenv`?
- How do you set them?
- What's `$PATH` and how does it work?

### Standard Streams

- What are `stdin`, `stdout`, `stderr`?
- How do you read from stdin?
- How do you write to stderr?
- What's piping? How does `|` work?
- What's redirection? (`>`, `<`, `>>`)

### Build It: Unix-like Utilities

Build practical command-line tools:

**Requirements:**

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Simple grep: search for pattern in files
void grep(const char *pattern, const char *filename) {
    FILE *f = fopen(filename, "r");
    if (!f) {
        perror("fopen");
        return;
    }

    char line[1024];
    int line_num = 0;
    while (fgets(line, sizeof(line), f)) {
        line_num++;
        if (strstr(line, pattern)) {
            printf("%s:%d:%s", filename, line_num, line);
        }
    }

    fclose(f);
}

// Word count: count lines, words, chars
void wc(const char *filename) {
    FILE *f = filename ? fopen(filename, "r") : stdin;
    if (!f) {
        perror("fopen");
        return;
    }

    int lines = 0, words = 0, chars = 0;
    int in_word = 0;
    int ch;

    while ((ch = fgetc(f)) != EOF) {
        chars++;
        if (ch == '\n') lines++;

        if (ch == ' ' || ch == '\n' || ch == '\t') {
            in_word = 0;
        } else if (!in_word) {
            in_word = 1;
            words++;
        }
    }

    printf("%d %d %d %s\n", lines, words, chars,
           filename ? filename : "");

    if (filename) fclose(f);
}

// Cat: concatenate and print files
void cat(int argc, char *argv[]) {
    for (int i = 1; i < argc; i++) {
        FILE *f = fopen(argv[i], "r");
        if (!f) {
            fprintf(stderr, "cat: %s: ", argv[i]);
            perror("");
            continue;
        }

        int ch;
        while ((ch = fgetc(f)) != EOF) {
            putchar(ch);
        }

        fclose(f);
    }
}

int main(int argc, char *argv[]) {
    // Example: simple argument parsing
    if (argc < 2) {
        fprintf(stderr, "Usage: %s <command> [args...]\n", argv[0]);
        fprintf(stderr, "Commands:\n");
        fprintf(stderr, "  grep <pattern> <file>\n");
        fprintf(stderr, "  wc <file>\n");
        fprintf(stderr, "  cat <files...>\n");
        return 1;
    }

    if (strcmp(argv[1], "grep") == 0) {
        if (argc < 4) {
            fprintf(stderr, "Usage: %s grep <pattern> <file>\n", argv[0]);
            return 1;
        }
        grep(argv[2], argv[3]);
    }
    else if (strcmp(argv[1], "wc") == 0) {
        if (argc < 3) {
            wc(NULL); // Read from stdin
        } else {
            wc(argv[2]);
        }
    }
    else if (strcmp(argv[1], "cat") == 0) {
        if (argc < 3) {
            fprintf(stderr, "Usage: %s cat <files...>\n", argv[0]);
            return 1;
        }
        cat(argc - 1, argv + 1);
    }
    else {
        fprintf(stderr, "Unknown command: %s\n", argv[1]);
        return 1;
    }

    return 0;
}
```

**Experiments:**

- Add more flags (like `-v` for invert grep)
- Read from stdin when no file given
- Support piping: `cat file.txt | ./program wc`
- Parse options like `--help` or `-h`
- Use environment variables for configuration
- Build a proper option parser (like getopt)

### Reflection Questions

1. **Command-Line:**

   - How do Unix tools compose?
   - What makes a good CLI?
   - How do you design intuitive interfaces?

2. **Streams:**

   - Why separate stdout and stderr?
   - How does piping work?
   - What's the benefit of stdin/stdout?

3. **Design:**
   - What makes tools reusable?
   - How do you follow Unix philosophy?
   - When should tools be flexible vs simple?

---

# 🔴 PART 6: PREPROCESSOR & COMPILATION CONTROL

---

## Section 15: Preprocessor Directives & Macros

### The Problem

You need constants. You need conditional compilation. You need to avoid repeating code. The preprocessor runs before compilation and can transform your code. **Understanding it is essential but also dangerous.**

### Understanding the Preprocessor

- What is the preprocessor?
- When does it run?
- How do you see preprocessor output? (`gcc -E`)
- What's the difference between preprocessor and compiler?
- Why is it "dumb" text replacement?

### #define and Constants

- What does `#define PI 3.14159` do?
- How is it different from `const double pi = 3.14159`?
- Should you use `#define` or `const` for constants?
- What are the dangers of `#define`?
- Why use UPPER_CASE for macros?

### Macros with Arguments

- How do you create a macro with parameters?
- What's wrong with `#define SQUARE(x) x * x`?
- Why must you parenthesize macro arguments?
- What's the correct way: `#define SQUARE(x) ((x) * (x))`?
- What's a multi-line macro? (Use `\` for continuation)

### Conditional Compilation

- What does `#ifdef`, `#ifndef`, `#if` do?
- How do you compile code only on certain platforms?
- What's `#elif` and `#else`?
- How do you use `#if defined()`?
- What are predefined macros like `__LINE__`, `__FILE__`?

### Common Macro Pitfalls

- You write `#define MAX(a,b) a > b ? a : b` and use it: `x = MAX(y, z) + 1`. What goes wrong?
- Why do side effects in macros fail? (e.g., `MAX(x++, y++)`)
- What's the difference between macros and inline functions?
- When should you use macros vs functions?

### Build It: Useful Macro Library

Create a collection of safe, useful macros:

**Requirements:**

```c
#include <stdio.h>

// Safe min/max macros
#define MIN(a, b) ({ \
    typeof(a) _a = (a); \
    typeof(b) _b = (b); \
    _a < _b ? _a : _b; \
})

#define MAX(a, b) ({ \
    typeof(a) _a = (a); \
    typeof(b) _b = (b); \
    _a > _b ? _a : _b; \
})

// Array size
#define ARRAY_SIZE(arr) (sizeof(arr) / sizeof((arr)[0]))

// Swap macro (no temp variable pollution)
#define SWAP(a, b) do { \
    typeof(a) _tmp = (a); \
    (a) = (b); \
    (b) = _tmp; \
} while(0)

// Debug printing
#ifdef DEBUG
    #define DEBUG_PRINT(fmt, ...) \
        fprintf(stderr, "DEBUG %s:%d: " fmt "\n", \
                __FILE__, __LINE__, ##__VA_ARGS__)
#else
    #define DEBUG_PRINT(fmt, ...) ((void)0)
#endif

// Assert macro
#define ASSERT(condition) do { \
    if (!(condition)) { \
        fprintf(stderr, "Assertion failed: %s, file %s, line %d\n", \
                #condition, __FILE__, __LINE__); \
        abort(); \
    } \
} while(0)

// Stringify
#define STRINGIFY(x) #x
#define TOSTRING(x) STRINGIFY(x)

// Container of
#define container_of(ptr, type, member) \
    ((type *)((char *)(ptr) - offsetof(type, member)))

int main(void) {
    int a = 10, b = 20;
    printf("MIN(%d, %d) = %d\n", a, b, MIN(a, b));
    printf("MAX(%d, %d) = %d\n", a, b, MAX(a, b));

    int arr[] = {1, 2, 3, 4, 5};
    printf("Array size: %zu\n", ARRAY_SIZE(arr));

    printf("Before swap: a=%d, b=%d\n", a, b);
    SWAP(a, b);
    printf("After swap: a=%d, b=%d\n", a, b);

    DEBUG_PRINT("This is a debug message: %d", 42);

    int x = 5;
    ASSERT(x > 0);
    // ASSERT(x < 0); // This would fail

    printf("PI is defined as: %s\n", TOSTRING(3.14159));

    return 0;
}
```

**Experiments:**

- Compile with `-DDEBUG` to enable debug prints
- Try macros with side effects — see failures
- Use `gcc -E` to see macro expansion
- Create dangerous macros intentionally
- Build a logging system with macros
- Make platform-specific code with `#ifdef`

### Reflection Questions

1. **Preprocessor:**

   - When should you use it?
   - What are the dangers?
   - How is it different from the language?

2. **Macros:**

   - When are macros better than functions?
   - How do you write safe macros?
   - What are the trade-offs?

3. **Best Practices:**
   - When should you use macros?
   - How do you avoid common pitfalls?
   - What belongs in macros vs code?

---

## Section 16: Header Files & Modular Design

### The Problem

Your program grows to thousands of lines. Everything in one file is unmaintainable. You need to organize code into modules. **Header files are C's mechanism for code organization.**

### Understanding Header Files

- What's the purpose of header files?
- What goes in `.h` files vs `.c` files?
- How do declarations differ from definitions?
- Why separate interface from implementation?
- What happens when you `#include` a header?

### Header Guards

- What are header guards?
- Why do you need them?
- What's `#ifndef`, `#define`, `#endif` pattern?
- What happens without header guards?
- What's `#pragma once`? Should you use it?

### Modular Design

- How do you split a program into modules?
- What makes a good module interface?
- How do you hide implementation details?
- What's the difference between public and private?
- How do you minimize coupling?

### Static Functions and Variables

- What does `static` mean for functions?
- What does `static` mean for global variables?
- How does `static` help encapsulation?
- When should you make functions static?
- What's the scope of `static`?

### extern and Linkage

- What does `extern` do?
- How do you share global variables across files?
- What's internal vs external linkage?
- When do you need `extern`?
- What are linkage errors?

### Build It: Multi-Module Project

Build a properly organized multi-file project:

**Requirements:**

Create a module-based calculator:

**math_ops.h:**

```c
#ifndef MATH_OPS_H
#define MATH_OPS_H

// Public interface
int add(int a, int b);
int subtract(int a, int b);
int multiply(int a, int b);
int divide(int a, int b);

#endif
```

**math_ops.c:**

```c
#include "math_ops.h"
#include <stdio.h>

// Private helper (static = file-local)
static int validate_divisor(int divisor) {
    return divisor != 0;
}

int add(int a, int b) {
    return a + b;
}

int subtract(int a, int b) {
    return a - b;
}

int multiply(int a, int b) {
    return a * b;
}

int divide(int a, int b) {
    if (!validate_divisor(b)) {
        fprintf(stderr, "Error: Division by zero\n");
        return 0;
    }
    return a / b;
}
```

**history.h:**

```c
#ifndef HISTORY_H
#define HISTORY_H

void history_init(void);
void history_add(const char *operation);
void history_print(void);
void history_cleanup(void);

#endif
```

**history.c:**

```c
#include "history.h"
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_HISTORY 10

// Private module data
static char *history[MAX_HISTORY];
static int count = 0;

void history_init(void) {
    count = 0;
    for (int i = 0; i < MAX_HISTORY; i++) {
        history[i] = NULL;
    }
}

void history_add(const char *operation) {
    if (count < MAX_HISTORY) {
        history[count] = strdup(operation);
        count++;
    }
}

void history_print(void) {
    printf("\n=== History ===\n");
    for (int i = 0; i < count; i++) {
        printf("%d: %s\n", i + 1, history[i]);
    }
}

void history_cleanup(void) {
    for (int i = 0; i < count; i++) {
        free(history[i]);
    }
}
```

**main.c:**

```c
#include <stdio.h>
#include <stdlib.h>
#include "math_ops.h"
#include "history.h"

int main(void) {
    history_init();

    char operation[100];
    int a, b, result;

    printf("Simple Calculator\n");
    printf("Commands: add, sub, mul, div, history, quit\n\n");

    while (1) {
        printf("> ");
        if (scanf("%s", operation) != 1) break;

        if (strcmp(operation, "quit") == 0) {
            break;
        } else if (strcmp(operation, "history") == 0) {
            history_print();
            continue;
        }

        if (scanf("%d %d", &a, &b) != 2) {
            printf("Invalid input\n");
            continue;
        }

        if (strcmp(operation, "add") == 0) {
            result = add(a, b);
            printf("%d + %d = %d\n", a, b, result);
            snprintf(operation, sizeof(operation), "%d + %d = %d", a, b, result);
        } else if (strcmp(operation, "sub") == 0) {
            result = subtract(a, b);
            printf("%d - %d = %d\n", a, b, result);
            snprintf(operation, sizeof(operation), "%d - %d = %d", a, b, result);
        } else if (strcmp(operation, "mul") == 0) {
            result = multiply(a, b);
            printf("%d * %d = %d\n", a, b, result);
            snprintf(operation, sizeof(operation), "%d * %d = %d", a, b, result);
        } else if (strcmp(operation, "div") == 0) {
            result = divide(a, b);
            printf("%d / %d = %d\n", a, b, result);
            snprintf(operation, sizeof(operation), "%d / %d = %d", a, b, result);
        } else {
            printf("Unknown operation\n");
            continue;
        }

        history_add(operation);
    }

    history_cleanup();
    return 0;
}
```

**Makefile:**

```makefile
CC = gcc
CFLAGS = -Wall -Wextra -g

OBJS = main.o math_ops.o history.o
TARGET = calc

$(TARGET): $(OBJS)
	$(CC) $(CFLAGS) $(OBJS) -o $(TARGET)

main.o: main.c math_ops.h history.h
	$(CC) $(CFLAGS) -c main.c

math_ops.o: math_ops.c math_ops.h
	$(CC) $(CFLAGS) -c math_ops.c

history.o: history.c history.h
	$(CC) $(CFLAGS) -c history.c

clean:
	rm -f $(OBJS) $(TARGET)
```

**Experiments:**

- Remove header guards — see errors
- Try to call a `static` function from another file
- Use `extern` to access module-private data (bad practice!)
- Add more modules (config, logging)
- Organize into subdirectories
- Create a library (.a file) from modules

### Reflection Questions

1. **Organization:**

   - What makes good module boundaries?
   - How do you design clean interfaces?
   - When should you split into modules?

2. **Encapsulation:**

   - How does `static` provide privacy?
   - What should be hidden vs exposed?
   - How do you prevent coupling?

3. **Maintenance:**
   - How do modules help maintenance?
   - What makes code easy to change?
   - How do you document modules?

---

## Section 17: Conditional Compilation & Portability

### The Problem

Your code needs to run on Linux, macOS, and Windows. It needs to work on 32-bit and 64-bit. It needs debug and release builds. **Conditional compilation enables platform-specific code.**

### Platform Detection

- How do you detect the operating system?
- What are `__linux__`, `__APPLE__`, `_WIN32`?
- How do you detect the compiler?
- How do you detect architecture (32 vs 64 bit)?
- What are predefined macros?

### Debug vs Release Builds

- How do you enable/disable debug code?
- What's the difference between debug and release?
- How do you optimize for release?
- What debugging info should you compile in?
- How do you use `NDEBUG`?

### Feature Detection

- How do you check if a feature is available?
- What's `#if defined(FEATURE)`?
- How do you provide fallbacks?
- How do you handle missing functions?
- What's feature testing macros?

### Portability Considerations

- What's endianness? How does it affect you?
- What's the size of `int` on different platforms?
- How do you write portable code?
- What are fixed-width types? (`int32_t`, etc.)
- When should you use them?

### Build It: Cross-Platform Utility Library

Create portable code with platform detection:

**Requirements:**

```c
#include <stdio.h>
#include <stdint.h>

// Platform detection
#if defined(_WIN32) || defined(_WIN64)
    #define PLATFORM "Windows"
    #define PATH_SEP '\\'
    #include <windows.h>
#elif defined(__linux__)
    #define PLATFORM "Linux"
    #define PATH_SEP '/'
    #include <unistd.h>
#elif defined(__APPLE__)
    #define PLATFORM "macOS"
    #define PATH_SEP '/'
    #include <unistd.h>
#else
    #define PLATFORM "Unknown"
    #define PATH_SEP '/'
#endif

// Compiler detection
#if defined(__GNUC__)
    #define COMPILER "GCC"
#elif defined(__clang__)
    #define COMPILER "Clang"
#elif defined(_MSC_VER)
    #define COMPILER "MSVC"
#else
    #define COMPILER "Unknown"
#endif

// Architecture detection
#if defined(__x86_64__) || defined(_M_X64)
    #define ARCH "x64"
    #define PTR_SIZE 8
#elif defined(__i386) || defined(_M_IX86)
    #define ARCH "x86"
    #define PTR_SIZE 4
#elif defined(__aarch64__) || defined(_M_ARM64)
    #define ARCH "ARM64"
    #define PTR_SIZE 8
#else
    #define ARCH "Unknown"
    #define PTR_SIZE sizeof(void*)
#endif

// Debug/Release
#ifdef NDEBUG
    #define BUILD_TYPE "Release"
    #define LOG(msg) ((void)0)
#else
    #define BUILD_TYPE "Debug"
    #define LOG(msg) printf("[DEBUG] %s\n", msg)
#endif

// Portable sleep function
void portable_sleep(int milliseconds) {
#if defined(_WIN32)
    Sleep(milliseconds);
#else
    usleep(milliseconds * 1000);
#endif
}

// Endianness detection
int is_little_endian(void) {
    uint32_t num = 1;
    return *(uint8_t*)&num == 1;
}

// Safe type sizes
void print_type_sizes(void) {
    printf("=== Type Sizes ===\n");
    printf("char: %zu bytes\n", sizeof(char));
    printf("short: %zu bytes\n", sizeof(short));
    printf("int: %zu bytes\n", sizeof(int));
    printf("long: %zu bytes\n", sizeof(long));
    printf("long long: %zu bytes\n", sizeof(long long));
    printf("float: %zu bytes\n", sizeof(float));
    printf("double: %zu bytes\n", sizeof(double));
    printf("pointer: %zu bytes\n", sizeof(void*));
    printf("\n");

    printf("=== Fixed-Width Types ===\n");
    printf("int8_t: %zu bytes\n", sizeof(int8_t));
    printf("int16_t: %zu bytes\n", sizeof(int16_t));
    printf("int32_t: %zu bytes\n", sizeof(int32_t));
    printf("int64_t: %zu bytes\n", sizeof(int64_t));
}

int main(void) {
    printf("=== Build Information ===\n");
    printf("Platform: %s\n", PLATFORM);
    printf("Compiler: %s\n", COMPILER);
    printf("Architecture: %s\n", ARCH);
    printf("Build Type: %s\n", BUILD_TYPE);
    printf("Path Separator: %c\n", PATH_SEP);
    printf("Endianness: %s\n\n",
           is_little_endian() ? "Little Endian" : "Big Endian");

    print_type_sizes();

    LOG("This only prints in debug builds");

    printf("\nSleeping for 1 second...\n");
    portable_sleep(1000);
    printf("Done!\n");

    return 0;
}
```

**Experiments:**

- Compile with and without `-DNDEBUG`
- Test on different platforms if available
- Add more platform-specific features
- Handle compiler differences
- Write portable file I/O
- Create a portable threading abstraction

### Reflection Questions

1. **Portability:**

   - What makes code portable?
   - What are common portability pitfalls?
   - When is platform-specific code necessary?

2. **Compilation:**

   - How do you manage multiple builds?
   - What belongs in conditional code?
   - How do you test all platforms?

3. **Design:**
   - How do you abstract platform differences?
   - What's the cost of portability?
   - When should you use abstraction layers?

---

# ⚫ PART 7: SYSTEMS PROGRAMMING

---

## Section 18: System Calls & OS Interface

### The Problem

You need to create files, spawn processes, handle signals, and interact with the operating system. **System calls are the interface between your program and the kernel.**

### Understanding System Calls

- What is a system call?
- How is it different from a library function?
- What happens when you make a syscall?
- Why are syscalls slower than regular functions?
- How do you check for syscall errors?

### File Operations (Low-Level)

- What's the difference between `open` and `fopen`?
- What are file descriptors 0, 1, 2?
- How do `read` and `write` work?
- What's `close` and why is it important?
- How do you set file permissions?

### Process Creation

- What is a process?
- What's the difference between program and process?
- How do you create a new process?
- What does `fork()` do?
- What's the return value of `fork`?
- What's `exec` family of functions?

### Process Termination

- How does a process exit?
- What's an exit status?
- What's a zombie process?
- What's an orphan process?
- How do you wait for child processes?

### Build It: Process Manager

Build tools to manage processes:

**Requirements:**

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/wait.h>
#include <string.h>

// Execute a command in a child process
int execute_command(const char *command) {
    pid_t pid = fork();

    if (pid < 0) {
        perror("fork");
        return -1;
    }

    if (pid == 0) {
        // Child process
        printf("[Child %d] Executing: %s\n", getpid(), command);

        // Parse command (simple version)
        char *args[10];
        char cmd_copy[256];
        strncpy(cmd_copy, command, sizeof(cmd_copy) - 1);

        int i = 0;
        char *token = strtok(cmd_copy, " ");
        while (token && i < 9) {
            args[i++] = token;
            token = strtok(NULL, " ");
        }
        args[i] = NULL;

        // Execute
        execvp(args[0], args);

        // If we get here, exec failed
        perror("execvp");
        exit(1);
    } else {
        // Parent process
        printf("[Parent %d] Created child %d\n", getpid(), pid);

        int status;
        waitpid(pid, &status, 0);

        if (WIFEXITED(status)) {
            printf("[Parent] Child exited with status %d\n",
                   WEXITSTATUS(status));
        }

        return 0;
    }
}

// Demonstrate zombie process
void create_zombie(void) {
    pid_t pid = fork();

    if (pid == 0) {
        // Child exits immediately
        printf("[Child %d] Exiting...\n", getpid());
        exit(0);
    } else {
        printf("[Parent] Child %d created\n", pid);
        printf("[Parent] Sleeping (child becomes zombie)...\n");
        sleep(5);

        // Check zombie with: ps aux | grep Z
        printf("[Parent] Reaping zombie...\n");
        wait(NULL);
    }
}

// Fork bomb protection demo (BE CAREFUL!)
void controlled_fork_test(int max_depth) {
    printf("Starting controlled fork test (max depth: %d)\n", max_depth);

    for (int i = 0; i < max_depth; i++) {
        pid_t pid = fork();

        if (pid < 0) {
            perror("fork");
            break;
        }

        if (pid == 0) {
            // Child
            printf("  [Level %d] Process %d created\n", i, getpid());
            sleep(1);
            exit(0);
        } else {
            // Parent waits
            wait(NULL);
        }
    }
}

int main(int argc, char *argv[]) {
    printf("=== Process Manager Demo ===\n");
    printf("Current Process ID: %d\n", getpid());
    printf("Parent Process ID: %d\n\n", getppid());

    if (argc > 1 && strcmp(argv[1], "zombie") == 0) {
        create_zombie();
    } else if (argc > 1 && strcmp(argv[1], "fork") == 0) {
        controlled_fork_test(3);
    } else {
        // Execute some commands
        execute_command("ls -l");
        printf("\n");
        execute_command("echo Hello from child process");
        printf("\n");
        execute_command("pwd");
    }

    return 0;
}
```

**Experiments:**

- Create a zombie and observe it with `ps`
- Make parent exit before child (orphan)
- Implement a simple shell
- Redirect stdout to a file
- Build a pipeline (connect processes)
- Handle signals (SIGINT, SIGTERM)

### Reflection Questions

1. **System Calls:**

   - When should you use them directly?
   - How do they differ from library functions?
   - What's the performance impact?

2. **Processes:**

   - How does fork work internally?
   - What gets copied, what gets shared?
   - When should you create processes?

3. **Design:**
   - How do you structure multi-process programs?
   - What are the trade-offs?
   - When should you use threads instead?

---

## Section 19: Process Control & Signals

### The Problem

Your program needs to handle Ctrl+C gracefully. Clean up on unexpected termination. Respond to system events. **Signals are asynchronous notifications from the OS.**

### Understanding Signals

- What is a signal?
- How are signals delivered?
- What's the default action for signals?
- What's SIGINT? SIGTERM? SIGKILL?
- Can you catch all signals?

### Signal Handlers

- How do you install a signal handler?
- What can you safely do in a signal handler?
- Why are signal handlers restricted?
- What's async-signal-safe?
- What's a race condition with signals?

### Common Signals

- SIGINT (Ctrl+C) - What does it do?
- SIGTERM - How is it different from SIGINT?
- SIGKILL - Why can't you catch it?
- SIGSEGV - What causes it?
- SIGCHLD - When is it sent?

### Build It: Signal Handling System

Create robust signal handling:

**Requirements:**

```c
#include <stdio.h>
#include <stdlib.h>
#include <signal.h>
#include <unistd.h>
#include <string.h>

// Flag for signal handler (atomic)
volatile sig_atomic_t quit_flag = 0;
volatile sig_atomic_t signal_count = 0;

// Signal handler for SIGINT (Ctrl+C)
void sigint_handler(int signum) {
    (void)signum; // Unused

    // Only async-signal-safe operations!
    signal_count++;

    if (signal_count >= 3) {
        // Force quit after 3 signals
        const char msg[] = "\nForce quitting...\n";
        write(STDOUT_FILENO, msg, sizeof(msg) - 1);
        _exit(1);
    } else {
        const char msg[] = "\nCaught SIGINT. Press Ctrl+C 2 more times to quit.\n";
        write(STDOUT_FILENO, msg, sizeof(msg) - 1);
        quit_flag = 1;
    }
}

// Signal handler for SIGTERM
void sigterm_handler(int signum) {
    (void)signum;
    const char msg[] = "Caught SIGTERM. Cleaning up...\n";
    write(STDOUT_FILENO, msg, sizeof(msg) - 1);
    quit_flag = 1;
}

// Demonstrate signal blocking
void demonstrate_signal_blocking(void) {
    printf("\n=== Signal Blocking Demo ===\n");

    sigset_t mask, oldmask;

    // Block SIGINT temporarily
    sigemptyset(&mask);
    sigaddset(&mask, SIGINT);
    sigprocmask(SIG_BLOCK, &mask, &oldmask);

    printf("SIGINT blocked. Press Ctrl+C (won't work)...\n");
    sleep(5);

    // Unblock
    sigprocmask(SIG_SETMASK, &oldmask, NULL);
    printf("SIGINT unblocked.\n");
}

// Cleanup function
void cleanup(void) {
    printf("\nPerforming cleanup...\n");
    // Close files, free memory, etc.
    printf("Cleanup complete.\n");
}

int main(void) {
    printf("=== Signal Handling Demo ===\n");
    printf("Process ID: %d\n", getpid());
    printf("Press Ctrl+C to trigger SIGINT\n");
    printf("Use 'kill %d' from another terminal for SIGTERM\n\n", getpid());

    // Install cleanup function
    atexit(cleanup);

    // Install signal handlers
    struct sigaction sa_int, sa_term;

    // SIGINT handler
    memset(&sa_int, 0, sizeof(sa_int));
    sa_int.sa_handler = sigint_handler;
    sigemptyset(&sa_int.sa_mask);
    sa_int.sa_flags = 0;
    sigaction(SIGINT, &sa_int, NULL);

    // SIGTERM handler
    memset(&sa_term, 0, sizeof(sa_term));
    sa_term.sa_handler = sigterm_handler;
    sigemptyset(&sa_term.sa_mask);
    sa_term.sa_flags = 0;
    sigaction(SIGTERM, &sa_term, NULL);

    // Main loop
    int counter = 0;
    while (!quit_flag) {
        printf("Working... %d\r", counter++);
        fflush(stdout);
        sleep(1);
    }

    printf("\nExiting gracefully...\n");
    return 0;
}
```

**Experiments:**

- Send different signals with `kill`
- Try catching SIGKILL (spoiler: you can't)
- Create a signal race condition
- Implement timeout with SIGALRM
- Handle SIGCHLD for zombies
- Build an alarm system

### Reflection Questions

1. **Signals:**

   - When should you use them?
   - What are the limitations?
   - How do they affect program flow?

2. **Safety:**

   - Why are signal handlers restricted?
   - What's async-signal-safe?
   - How do you avoid race conditions?

3. **Design:**
   - How do you structure signal-aware programs?
   - When are signals the right tool?
   - What are alternatives?

---

## Section 20: Inter-Process Communication

### The Problem

Multiple processes need to communicate. Share data. Coordinate work. **IPC mechanisms enable cooperation between processes.**

### Types of IPC

- What's a pipe?
- What's a named pipe (FIFO)?
- What's shared memory?
- What's a message queue?
- What are sockets?

### Pipes

- How do pipes work?
- What's the difference between read and write end?
- How do you create a pipe?
- How do you use pipes with fork?
- When does a pipe close?

### Named Pipes (FIFOs)

- How are they different from pipes?
- When should you use them?
- How do you create a FIFO?
- How do multiple processes use one?

### Shared Memory

- What is shared memory?
- How do you create it?
- What are the dangers?
- How do you synchronize access?
- What's better: shared memory or pipes?

### Build It: IPC Examples

Build practical IPC applications:

**Requirements:**

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <string.h>
#include <sys/wait.h>

// === PIPES ===

void pipe_example(void) {
    printf("\n=== Pipe Example ===\n");

    int pipefd[2];
    if (pipe(pipefd) == -1) {
        perror("pipe");
        return;
    }

    pid_t pid = fork();

    if (pid == 0) {
        // Child: writes to pipe
        close(pipefd[0]); // Close read end

        const char *msg = "Hello from child process!";
        write(pipefd[1], msg, strlen(msg) + 1);
        close(pipefd[1]);

        exit(0);
    } else {
        // Parent: reads from pipe
        close(pipefd[1]); // Close write end

        char buffer[100];
        read(pipefd[0], buffer, sizeof(buffer));
        printf("Parent received: %s\n", buffer);
        close(pipefd[0]);

        wait(NULL);
    }
}

// === PIPELINE (ls | wc) ===

void pipeline_example(void) {
    printf("\n=== Pipeline Example (ls | wc -l) ===\n");

    int pipefd[2];
    pipe(pipefd);

    if (fork() == 0) {
        // First child: runs ls
        close(pipefd[0]); // Close read end
        dup2(pipefd[1], STDOUT_FILENO); // Redirect stdout to pipe
        close(pipefd[1]);

        execlp("ls", "ls", NULL);
        perror("execlp");
        exit(1);
    }

    if (fork() == 0) {
        // Second child: runs wc
        close(pipefd[1]); // Close write end
        dup2(pipefd[0], STDIN_FILENO); // Redirect stdin from pipe
        close(pipefd[0]);

        execlp("wc", "wc", "-l", NULL);
        perror("execlp");
        exit(1);
    }

    // Parent closes both ends and waits
    close(pipefd[0]);
    close(pipefd[1]);
    wait(NULL);
    wait(NULL);
}

// === BIDIRECTIONAL COMMUNICATION ===

void bidirectional_example(void) {
    printf("\n=== Bidirectional Pipe Example ===\n");

    int pipe1[2], pipe2[2]; // Two pipes for bidirectional comm
    pipe(pipe1); // Parent -> Child
    pipe(pipe2); // Child -> Parent

    pid_t pid = fork();

    if (pid == 0) {
        // Child
        close(pipe1[1]); // Close write end of pipe1
        close(pipe2[0]); // Close read end of pipe2

        // Read from parent
        char buffer[100];
        read(pipe1[0], buffer, sizeof(buffer));
        printf("Child received: %s\n", buffer);

        // Send response
        const char *response = "Message received!";
        write(pipe2[1], response, strlen(response) + 1);

        close(pipe1[0]);
        close(pipe2[1]);
        exit(0);
    } else {
        // Parent
        close(pipe1[0]); // Close read end of pipe1
        close(pipe2[1]); // Close write end of pipe2

        // Send to child
        const char *msg = "Hello, child!";
        write(pipe1[1], msg, strlen(msg) + 1);

        // Read response
        char buffer[100];
        read(pipe2[0], buffer, sizeof(buffer));
        printf("Parent received: %s\n", buffer);

        close(pipe1[1]);
        close(pipe2[0]);
        wait(NULL);
    }
}

int main(void) {
    pipe_example();
    pipeline_example();
    bidirectional_example();

    return 0;
}
```

**Experiments:**

- Build a client-server with FIFOs
- Implement shared memory example
- Create a message queue
- Build a simple chat program
- Implement producer-consumer with pipes
- Add error handling and timeouts

### Reflection Questions

1. **IPC Mechanisms:**

   - When should you use each type?
   - What are the trade-offs?
   - What's the performance?

2. **Design:**

   - How do you structure IPC systems?
   - How do you handle errors?
   - What about synchronization?

3. **Real-World:**
   - When is IPC necessary?
   - What are alternatives?
   - How do systems scale?

---

# ⚪ PART 8: ADVANCED MEMORY & OPTIMIZATION

---

## Section 21: Memory Alignment & Padding

### The Problem

Your struct is larger than expected. Your program is slower than it should be. Memory layout affects performance. **Understanding alignment is crucial for optimization.**

### Understanding Alignment

- What is memory alignment?
- Why do CPUs prefer aligned access?
- What happens with unaligned access?
- How does the compiler decide alignment?
- What's natural alignment?

### Struct Padding

- Why does `struct {char c; int x;}` take 8 bytes, not 5?
- Where does the compiler add padding?
- How do you minimize padding?
- What's `__attribute__((packed))`?
- Should you always pack structs?

### Cache Lines

- What is a cache line? (Typically 64 bytes)
- What's cache alignment?
- What's false sharing?
- How does alignment affect cache performance?
- When should you care about cache lines?

### Build It: Alignment Explorer

Explore memory layout and alignment:

**Requirements:**

```c
#include <stdio.h>
#include <stddef.h>
#include <stdint.h>

// Different struct layouts
struct Unoptimized {
    char a;     // 1 byte + 3 padding
    int b;      // 4 bytes
    char c;     // 1 byte + 3 padding
    int d;      // 4 bytes
    char e;     // 1 byte + 7 padding
    double f;   // 8 bytes
}; // Total: 32 bytes

struct Optimized {
    double f;   // 8 bytes
    int b;      // 4 bytes
    int d;      // 4 bytes
    char a;     // 1 byte
    char c;     // 1 byte
    char e;     // 1 byte + 5 padding
}; // Total: 24 bytes

struct __attribute__((packed)) Packed {
    char a;
    int b;
    char c;
    int d;
    char e;
    double f;
}; // Total: 19 bytes (no padding)

// Demonstrate offsetof
void print_layout(void) {
    printf("=== Unoptimized Layout ===\n");
    printf("Size: %zu bytes\n", sizeof(struct Unoptimized));
    printf("  a at offset %zu\n", offsetof(struct Unoptimized, a));
    printf("  b at offset %zu\n", offsetof(struct Unoptimized, b));
    printf("  c at offset %zu\n", offsetof(struct Unoptimized, c));
    printf("  d at offset %zu\n", offsetof(struct Unoptimized, d));
    printf("  e at offset %zu\n", offsetof(struct Unoptimized, e));
    printf("  f at offset %zu\n", offsetof(struct Unoptimized, f));

    printf("\n=== Optimized Layout ===\n");
    printf("Size: %zu bytes (saved %zu bytes!)\n",
           sizeof(struct Optimized),
           sizeof(struct Unoptimized) - sizeof(struct Optimized));

    printf("\n=== Packed Layout ===\n");
    printf("Size: %zu bytes (but may be slower!)\n",
           sizeof(struct Packed));
}

// Test alignment performance
void alignment_performance_test(void) {
    printf("\n=== Alignment Performance ===\n");

    // Aligned access
    int aligned[1000] __attribute__((aligned(64)));

    // Potentially unaligned
    char buffer[4000];
    int *unaligned = (int*)(buffer + 1);

    printf("Aligned address: %p (%%64 = %ld)\n",
           (void*)aligned, (long)aligned % 64);
    printf("Unaligned address: %p (%%4 = %ld)\n",
           (void*)unaligned, (long)unaligned % 4);

    // Note: Actual performance testing requires timing
    printf("(Run with performance counters to measure difference)\n");
}

int main(void) {
    print_layout();
    alignment_performance_test();

    printf("\n=== Type Alignment Requirements ===\n");
    printf("char:   %zu bytes alignment\n", _Alignof(char));
    printf("short:  %zu bytes alignment\n", _Alignof(short));
    printf("int:    %zu bytes alignment\n", _Alignof(int));
    printf("long:   %zu bytes alignment\n", _Alignof(long));
    printf("double: %zu bytes alignment\n", _Alignof(double));
    printf("pointer: %zu bytes alignment\n", _Alignof(void*));

    return 0;
}
```

**Experiments:**

- Reorder struct members — see size change
- Use packed structs — measure performance impact
- Align to cache line boundaries
- Test unaligned access on different architectures
- Measure cache miss rates

### Reflection Questions

1. **Alignment:**

   - Why does it matter?
   - When should you optimize for it?
   - What's the cost of packing?

2. **Performance:**

   - How much difference does alignment make?
   - When is it critical?
   - How do you measure impact?

3. **Design:**
   - How do you order struct members?
   - When should you pack?
   - What about portability?

---

## Section 22: Cache-Friendly Code & Performance

### The Problem

Your algorithm is correct but slow. The CPU spends time waiting for memory. Cache misses dominate runtime. **Writing cache-friendly code can 10x your performance.**

### Understanding Cache

- What is CPU cache?
- What are L1, L2, L3 caches?
- What's a cache miss?
- What's spatial locality?
- What's temporal locality?

### Array Traversal

- Row-major vs column-major order
- Why does traversal order matter?
- How do you write cache-friendly loops?
- What's the impact of stride?
- How does prefetching work?

### Data Structure Design

- How does linked list perform vs array?
- Why are pointer-chasing operations slow?
- What's structure of arrays (SoA)?
- What's array of structures (AoS)?
- When should you use each?

### Build It: Cache Performance Tests

Measure cache impact:

**Requirements:**

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <string.h>

#define SIZE 1000

// Structure of Arrays (SoA) - cache friendly
typedef struct {
    int *ids;
    float *values;
    int count;
} SoA;

// Array of Structures (AoS) - less cache friendly for partial access
typedef struct {
    int id;
    float value;
} Element;

typedef struct {
    Element *elements;
    int count;
} AoS;

// Test: Sum all values
double test_soa(SoA *soa) {
    clock_t start = clock();

    float sum = 0;
    for (int iter = 0; iter < 10000; iter++) {
        for (int i = 0; i < soa->count; i++) {
            sum += soa->values[i];
        }
    }

    clock_t end = clock();
    double time = (double)(end - start) / CLOCKS_PER_SEC;
    printf("SoA time: %.4f seconds (sum: %f)\n", time, sum);
    return time;
}

double test_aos(AoS *aos) {
    clock_t start = clock();

    float sum = 0;
    for (int iter = 0; iter < 10000; iter++) {
        for (int i = 0; i < aos->count; i++) {
            sum += aos->elements[i].value;
        }
    }

    clock_t end = clock();
    double time = (double)(end - start) / CLOCKS_PER_SEC;
    printf("AoS time: %.4f seconds (sum: %f)\n", time, sum);
    return time;
}

// Matrix traversal
void matrix_row_major(int rows, int cols) {
    int **matrix = malloc(rows * sizeof(int*));
    for (int i = 0; i < rows; i++) {
        matrix[i] = malloc(cols * sizeof(int));
    }

    clock_t start = clock();
    long long sum = 0;

    // Row-major order (cache friendly)
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            sum += matrix[i][j];
        }
    }

    clock_t end = clock();
    printf("Row-major time: %.4f seconds\n",
           (double)(end - start) / CLOCKS_PER_SEC);

    for (int i = 0; i < rows; i++) {
        free(matrix[i]);
    }
    free(matrix);
}

void matrix_column_major(int rows, int cols) {
    int **matrix = malloc(rows * sizeof(int*));
    for (int i = 0; i < rows; i++) {
        matrix[i] = malloc(cols * sizeof(int));
    }

    clock_t start = clock();
    long long sum = 0;

    // Column-major order (cache unfriendly!)
    for (int j = 0; j < cols; j++) {
        for (int i = 0; i < rows; i++) {
            sum += matrix[i][j];
        }
    }

    clock_t end = clock();
    printf("Column-major time: %.4f seconds\n",
           (double)(end - start) / CLOCKS_PER_SEC);

    for (int i = 0; i < rows; i++) {
        free(matrix[i]);
    }
    free(matrix);
}

int main(void) {
    printf("=== Cache Performance Tests ===\n\n");

    // Test SoA vs AoS
    printf("Structure of Arrays vs Array of Structures:\n");

    SoA soa;
    soa.count = SIZE;
    soa.ids = malloc(SIZE * sizeof(int));
    soa.values = malloc(SIZE * sizeof(float));
    for (int i = 0; i < SIZE; i++) {
        soa.ids[i] = i;
        soa.values[i] = i * 1.5f;
    }

    AoS aos;
    aos.count = SIZE;
    aos.elements = malloc(SIZE * sizeof(Element));
    for (int i = 0; i < SIZE; i++) {
        aos.elements[i].id = i;
        aos.elements[i].value = i * 1.5f;
    }

    double soa_time = test_soa(&soa);
    double aos_time = test_aos(&aos);
    printf("SoA is %.2fx faster\n\n", aos_time / soa_time);

    // Test matrix traversal
    printf("Matrix Traversal (1000x1000):\n");
    matrix_row_major(1000, 1000);
    matrix_column_major(1000, 1000);

    free(soa.ids);
    free(soa.values);
    free(aos.elements);

    return 0;
}
```

**Experiments:**

- Test with different array sizes
- Measure cache misses with `perf`
- Compare linked list vs array iteration
- Test different stride lengths
- Optimize a real algorithm
- Profile with cachegrind

### Reflection Questions

1. **Cache:**

   - How much does it matter?
   - When should you optimize for it?
   - How do you measure impact?

2. **Design:**

   - How do you structure data for cache?
   - When is cache optimization worth it?
   - What about code complexity?

3. **Real-World:**
   - Where does this apply?
   - What algorithms benefit most?
   - How do modern CPUs help?

---

## Section 23: Bit Manipulation & Low-Level Tricks

### The Problem

You need to pack data tightly. Set hardware flags. Implement cryptography. Create efficient data structures. **Bit manipulation is essential for systems programming.**

### Understanding Bits

- How do you represent numbers in binary?
- What's two's complement?
- How do signed integers work?
- What are bitwise operators?
- How do shifts work?

### Bit Operations

- What's AND, OR, XOR, NOT?
- How do you set a bit?
- How do you clear a bit?
- How do you toggle a bit?
- How do you check if a bit is set?

### Bit Tricks

- How do you swap without temp variable?
- How do you count set bits?
- How do you find the lowest set bit?
- How do you check if power of 2?
- How do you align to power of 2?

### Bit Fields

- What are bit fields in structs?
- When should you use them?
- Are they portable?
- What's the memory layout?
- What are the alternatives?

### Build It: Bit Manipulation Library

Create useful bit manipulation tools:

**Requirements:**

```c
#include <stdio.h>
#include <stdint.h>
#include <stdbool.h>

// Set bit at position
#define BIT_SET(num, pos) ((num) |= (1U << (pos)))

// Clear bit at position
#define BIT_CLEAR(num, pos) ((num) &= ~(1U << (pos)))

// Toggle bit at position
#define BIT_TOGGLE(num, pos) ((num) ^= (1U << (pos)))

// Check if bit is set
#define BIT_CHECK(num, pos) (((num) >> (pos)) & 1U)

// Print binary representation
void print_binary(uint32_t num) {
    for (int i = 31; i >= 0; i--) {
        printf("%d", (num >> i) & 1);
        if (i % 8 == 0 && i != 0) printf(" ");
    }
    printf("\n");
}

// Count set bits (population count)
int popcount(uint32_t num) {
    int count = 0;
    while (num) {
        count += num & 1;
        num >>= 1;
    }
    return count;
}

// Fast popcount using Brian Kernighan's algorithm
int fast_popcount(uint32_t num) {
    int count = 0;
    while (num) {
        num &= num - 1; // Clear lowest set bit
        count++;
    }
    return count;
}

// Check if power of 2
bool is_power_of_2(uint32_t num) {
    return num && !(num & (num - 1));
}

// Find position of lowest set bit
int lowest_bit_position(uint32_t num) {
    if (num == 0) return -1;
    int pos = 0;
    while (!(num & 1)) {
        num >>= 1;
        pos++;
    }
    return pos;
}

// Swap two numbers without temp variable
void swap_xor(int *a, int *b) {
    if (a != b) { // Check for same address
        *a ^= *b;
        *b ^= *a;
        *a ^= *b;
    }
}

// Round up to next power of 2
uint32_t next_power_of_2(uint32_t num) {
    num--;
    num |= num >> 1;
    num |= num >> 2;
    num |= num >> 4;
    num |= num >> 8;
    num |= num >> 16;
    num++;
    return num;
}

// Bit field example
struct Flags {
    unsigned int flag1 : 1;  // 1 bit
    unsigned int flag2 : 1;  // 1 bit
    unsigned int value : 6;  // 6 bits
    unsigned int mode : 2;   // 2 bits
    // Total: 10 bits (padded to 16 bits = 2 bytes)
};

int main(void) {
    printf("=== Bit Manipulation Library ===\n\n");

    uint32_t num = 0b10110100; // 180
    printf("Original: ");
    print_binary(num);

    BIT_SET(num, 0);
    printf("After SET bit 0: ");
    print_binary(num);

    BIT_CLEAR(num, 2);
    printf("After CLEAR bit 2: ");
    print_binary(num);

    BIT_TOGGLE(num, 5);
    printf("After TOGGLE bit 5: ");
    print_binary(num);

    printf("\nBit 3 is %s\n", BIT_CHECK(num, 3) ? "SET" : "CLEAR");

    printf("\nPopcount: %d\n", popcount(num));
    printf("Fast popcount: %d\n", fast_popcount(num));

    printf("\nIs 16 power of 2? %s\n", is_power_of_2(16) ? "yes" : "no");
    printf("Is 15 power of 2? %s\n", is_power_of_2(15) ? "yes" : "no");

    printf("\nLowest bit position of %u: %d\n", num, lowest_bit_position(num));

    int a = 5, b = 10;
    printf("\nBefore swap: a=%d, b=%d\n", a, b);
    swap_xor(&a, &b);
    printf("After swap: a=%d, b=%d\n", a, b);

    printf("\nNext power of 2 after 100: %u\n", next_power_of_2(100));

    // Bit fields
    struct Flags flags = {.flag1 = 1, .flag2 = 0, .value = 42, .mode = 3};
    printf("\nBit field size: %zu bytes\n", sizeof(flags));
    printf("Flags: flag1=%u, flag2=%u, value=%u, mode=%u\n",
           flags.flag1, flags.flag2, flags.value, flags.mode);

    return 0;
}
```

**Experiments:**

- Implement a bloom filter
- Create a bitmap for tracking used/free items
- Build a bitset data structure
- Implement compression with bit packing
- Create efficient boolean arrays
- Optimize with SIMD operations

### Reflection Questions

1. **Bit Operations:**

   - When are they useful?
   - What problems do they solve?
   - What's the performance benefit?

2. **Design:**

   - When should you use bit manipulation?
   - What about readability?
   - Are there safer alternatives?

3. **Applications:**
   - Where is this common?
   - What systems rely on it?
   - How does hardware use bits?

---

# 🟤 PART 9: PRODUCTION-QUALITY C

---

## Section 24: Error Handling Patterns

### The Problem

Functions fail. Resources are unavailable. Input is invalid. **Robust programs handle errors gracefully rather than crashing.**

### Understanding Error Handling in C

- How do you return errors in C?
- What's the errno convention?
- What are error codes vs error values?
- How do you clean up on error?
- What's the goto cleanup pattern?

### Return Value Conventions

- Return -1 on error, 0 on success?
- Return NULL on error?
- Return error code directly?
- Use out parameters for results?
- Which pattern is best?

### errno and perror

- What is errno?
- When is it set?
- How do you use perror?
- What's strerror?
- Is errno thread-safe?

### Resource Management

- How do you ensure cleanup happens?
- What's RAII (in C++ terms)?
- How do you handle multiple resources?
- What if cleanup itself fails?
- How do you avoid leaks on error paths?

### Build It: Robust File Processor

Create production-quality error handling:

**Requirements:**

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <errno.h>
#include <stdbool.h>

// Error codes
typedef enum {
    ERR_OK = 0,
    ERR_INVALID_ARG,
    ERR_FILE_OPEN,
    ERR_FILE_READ,
    ERR_FILE_WRITE,
    ERR_MEMORY,
    ERR_UNKNOWN
} ErrorCode;

// Error to string
const char* error_string(ErrorCode err) {
    switch (err) {
        case ERR_OK: return "Success";
        case ERR_INVALID_ARG: return "Invalid argument";
        case ERR_FILE_OPEN: return "Failed to open file";
        case ERR_FILE_READ: return "Failed to read file";
        case ERR_FILE_WRITE: return "Failed to write file";
        case ERR_MEMORY: return "Memory allocation failed";
        default: return "Unknown error";
    }
}

// Process file with proper error handling
ErrorCode process_file(const char *input, const char *output) {
    FILE *in = NULL;
    FILE *out = NULL;
    char *buffer = NULL;
    ErrorCode result = ERR_OK;

    // Validate inputs
    if (!input || !output) {
        result = ERR_INVALID_ARG;
        goto cleanup;
    }

    // Open input file
    in = fopen(input, "r");
    if (!in) {
        fprintf(stderr, "Error opening %s: %s\n", input, strerror(errno));
        result = ERR_FILE_OPEN;
        goto cleanup;
    }

    // Get file size
    fseek(in, 0, SEEK_END);
    long size = ftell(in);
    fseek(in, 0, SEEK_SET);

    if (size < 0) {
        result = ERR_FILE_READ;
        goto cleanup;
    }

    // Allocate buffer
    buffer = malloc(size + 1);
    if (!buffer) {
        fprintf(stderr, "Memory allocation failed\n");
        result = ERR_MEMORY;
        goto cleanup;
    }

    // Read file
    size_t read = fread(buffer, 1, size, in);
    if (read != size) {
        fprintf(stderr, "Read error: expected %ld, got %zu\n", size, read);
        result = ERR_FILE_READ;
        goto cleanup;
    }
    buffer[size] = '\0';

    // Open output file
    out = fopen(output, "w");
    if (!out) {
        fprintf(stderr, "Error opening %s: %s\n", output, strerror(errno));
        result = ERR_FILE_WRITE;
        goto cleanup;
    }

    // Process and write (convert to uppercase as example)
    for (size_t i = 0; i < size; i++) {
        if (buffer[i] >= 'a' && buffer[i] <= 'z') {
            buffer[i] -= 32;
        }
    }

    size_t written = fwrite(buffer, 1, size, out);
    if (written != size) {
        fprintf(stderr, "Write error\n");
        result = ERR_FILE_WRITE;
        goto cleanup;
    }

cleanup:
    // Clean up resources (in reverse order)
    if (out) {
        if (fclose(out) != 0 && result == ERR_OK) {
            result = ERR_FILE_WRITE;
        }
    }
    if (in) {
        fclose(in); // Ignore errors on input file close
    }
    free(buffer); // safe to call on NULL

    return result;
}

// Example: Safe string duplication with error handling
char* safe_strdup(const char *str, ErrorCode *err) {
    if (!str) {
        *err = ERR_INVALID_ARG;
        return NULL;
    }

    char *dup = malloc(strlen(str) + 1);
    if (!dup) {
        *err = ERR_MEMORY;
        return NULL;
    }

    strcpy(dup, str);
    *err = ERR_OK;
    return dup;
}

int main(int argc, char *argv[]) {
    if (argc != 3) {
        fprintf(stderr, "Usage: %s <input> <output>\n", argv[0]);
        return 1;
    }

    ErrorCode err = process_file(argv[1], argv[2]);

    if (err != ERR_OK) {
        fprintf(stderr, "Error: %s\n", error_string(err));
        return 1;
    }

    printf("File processed successfully\n");
    return 0;
}
```

**Experiments:**

- Remove cleanup code — use Valgrind to see leaks
- Cause errors at different points
- Test all error paths
- Add logging for debugging
- Implement retry logic
- Create an error context system

### Reflection Questions

1. **Error Handling:**

   - What makes error handling robust?
   - How do you avoid resource leaks?
   - What's the cost of thorough checking?

2. **Patterns:**

   - When should you use goto cleanup?
   - How do you structure error paths?
   - What about nested errors?

3. **Design:**
   - How do you design error-tolerant systems?
   - What makes APIs easy to use correctly?
   - How do you prevent misuse?

---

## Section 25: Writing Testable & Maintainable C

### The Problem

Your code works now but breaks when you change it. Others can't understand it. Tests are impossible. **Production code needs structure, documentation, and testability.**

### Code Organization

- How do you structure large projects?
- What's a good directory layout?
- How do you separate concerns?
- What's a module boundary?
- How do you minimize dependencies?

### Documentation

- What should you document?
- How do you write good comments?
- What's self-documenting code?
- When are comments necessary?
- How do you document APIs?

### Testing in C

- How do you write unit tests?
- What's a test framework?
- How do you mock dependencies?
- How do you test error paths?
- What's integration testing?

### Code Style

- Why does style matter?
- What's a coding standard?
- How do you enforce style?
- What tools help? (clang-format, etc.)
- What makes code readable?

### Build It: Testable Module Example

Create well-structured, testable code:

**Requirements:**

```c
// === string_utils.h ===
#ifndef STRING_UTILS_H
#define STRING_UTILS_H

#include <stddef.h>
#include <stdbool.h>

/**
 * @brief Reverses a string in place
 * @param str String to reverse (must not be NULL)
 * @return true on success, false if str is NULL
 */
bool string_reverse(char *str);

/**
 * @brief Counts words in a string
 * @param str String to analyze (may be NULL)
 * @return Number of words, or 0 if str is NULL
 */
int string_count_words(const char *str);

/**
 * @brief Removes leading and trailing whitespace
 * @param str String to trim (modified in place)
 * @return Pointer to trimmed string, or NULL if str is NULL
 */
char* string_trim(char *str);

#endif

// === string_utils.c ===
#include "string_utils.h"
#include <string.h>
#include <ctype.h>

bool string_reverse(char *str) {
    if (!str) return false;

    size_t len = strlen(str);
    for (size_t i = 0; i < len / 2; i++) {
        char temp = str[i];
        str[i] = str[len - 1 - i];
        str[len - 1 - i] = temp;
    }

    return true;
}

int string_count_words(const char *str) {
    if (!str) return 0;

    int count = 0;
    bool in_word = false;

    while (*str) {
        if (isspace(*str)) {
            in_word = false;
        } else if (!in_word) {
            in_word = true;
            count++;
        }
        str++;
    }

    return count;
}

char* string_trim(char *str) {
    if (!str) return NULL;

    // Trim leading
    while (isspace(*str)) str++;

    // Trim trailing
    char *end = str + strlen(str) - 1;
    while (end > str && isspace(*end)) {
        *end = '\0';
        end--;
    }

    return str;
}

// === test_string_utils.c ===
#include "string_utils.h"
#include <stdio.h>
#include <string.h>
#include <assert.h>

#define TEST(name) void test_##name(void)
#define RUN_TEST(name) do { \
    printf("Running test_%s...", #name); \
    test_##name(); \
    printf(" PASSED\n"); \
} while(0)

TEST(reverse_basic) {
    char str[] = "hello";
    assert(string_reverse(str));
    assert(strcmp(str, "olleh") == 0);
}

TEST(reverse_empty) {
    char str[] = "";
    assert(string_reverse(str));
    assert(strcmp(str, "") == 0);
}

TEST(reverse_null) {
    assert(!string_reverse(NULL));
}

TEST(count_words_basic) {
    assert(string_count_words("hello world") == 2);
    assert(string_count_words("one two three") == 3);
}

TEST(count_words_empty) {
    assert(string_count_words("") == 0);
    assert(string_count_words("   ") == 0);
}

TEST(count_words_null) {
    assert(string_count_words(NULL) == 0);
}

TEST(trim_basic) {
    char str1[] = "  hello  ";
    assert(strcmp(string_trim(str1), "hello") == 0);

    char str2[] = "world";
    assert(strcmp(string_trim(str2), "world") == 0);
}

TEST(trim_null) {
    assert(string_trim(NULL) == NULL);
}

int main(void) {
    printf("=== Running String Utils Tests ===\n");

    RUN_TEST(reverse_basic);
    RUN_TEST(reverse_empty);
    RUN_TEST(reverse_null);
    RUN_TEST(count_words_basic);
    RUN_TEST(count_words_empty);
    RUN_TEST(count_words_null);
    RUN_TEST(trim_basic);
    RUN_TEST(trim_null);

    printf("\nAll tests passed!\n");
    return 0;
}
```

**Experiments:**

- Add more test cases
- Use a real test framework (Check, Unity)
- Add code coverage measurement
- Write tests first (TDD)
- Add integration tests
- Set up CI/CD

### Reflection Questions

1. **Testability:**

   - What makes code testable?
   - How do you test C code?
   - What are the challenges?

2. **Maintainability:**

   - What makes code maintainable?
   - How do you structure for change?
   - What's the role of documentation?

3. **Process:**
   - How do you ensure quality?
   - What tools help?
   - How do you prevent regressions?

---

## Section 26: Debugging Tools & Techniques

### The Problem

Your program crashes mysteriously. Memory is corrupted. Performance is poor. **Professional debugging requires systematic techniques and tools.**

### Core Debugging Tools

- What is GDB?
- How do you use breakpoints?
- How do you inspect variables?
- How do you step through code?
- What's a backtrace?

### Memory Debugging

- What is Valgrind?
- How do you detect memory leaks?
- How do you find use-after-free?
- What's AddressSanitizer?
- How do you detect buffer overflows?

### Performance Profiling

- What's profiling?
- What's gprof?
- What's perf?
- How do you find bottlenecks?
- How do you measure cache performance?

### Static Analysis

- What's static analysis?
- What tools exist? (clang-tidy, cppcheck)
- What can they catch?
- Should you use them?
- How do you integrate them?

### Build It: Debugging Workflow

Practice systematic debugging:

**Requirements:**

```c
// buggy_program.c - Contains various bugs to find
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Bug 1: Memory leak
char* create_string(const char *src) {
    char *str = malloc(strlen(src) + 1);
    strcpy(str, src);
    return str;
    // Missing: caller must free!
}

// Bug 2: Buffer overflow
void copy_data(char *dest, const char *src, int size) {
    // Should use strncpy or check length!
    strcpy(dest, src);
}

// Bug 3: Use after free
void use_after_free_bug(void) {
    int *data = malloc(sizeof(int) * 10);
    free(data);
    data[0] = 42; // BUG: use after free
}

// Bug 4: Double free
void double_free_bug(void) {
    int *data = malloc(sizeof(int));
    free(data);
    free(data); // BUG: double free
}

// Bug 5: Null pointer dereference
void null_deref_bug(char *str) {
    // Should check if str is NULL
    printf("Length: %zu\n", strlen(str));
}

// Bug 6: Off-by-one
void off_by_one_bug(void) {
    int arr[10];
    for (int i = 0; i <= 10; i++) { // BUG: should be < 10
        arr[i] = i;
    }
}

// Correct version for comparison
void correct_usage(void) {
    char *str = create_string("hello");
    printf("Created: %s\n", str);
    free(str); // Correctly freed

    char buffer[20];
    strncpy(buffer, "safe copy", sizeof(buffer) - 1);
    buffer[sizeof(buffer) - 1] = '\0';
    printf("Safe: %s\n", buffer);
}

int main(int argc, char *argv[]) {
    if (argc < 2) {
        printf("Usage: %s <test_number>\n", argv[0]);
        printf("Tests: 1=leak, 2=overflow, 3=use-after-free, ");
        printf("4=double-free, 5=null-deref, 6=off-by-one, 7=correct\n");
        return 1;
    }

    int test = atoi(argv[1]);

    switch (test) {
        case 1: {
            char *s = create_string("leak");
            printf("%s\n", s);
            // Bug: never freed
            break;
        }
        case 2: {
            char small[5];
            copy_data(small, "This is too long!", sizeof(small));
            break;
        }
        case 3:
            use_after_free_bug();
            break;
        case 4:
            double_free_bug();
            break;
        case 5:
            null_deref_bug(NULL);
            break;
        case 6:
            off_by_one_bug();
            break;
        case 7:
            correct_usage();
            break;
        default:
            printf("Unknown test\n");
    }

    return 0;
}
```

**Debugging Exercises:**

1. **Memory Leaks:**

   ```bash
   gcc -g buggy_program.c -o buggy
   valgrind --leak-check=full ./buggy 1
   ```

2. **Use-After-Free:**

   ```bash
   gcc -g -fsanitize=address buggy_program.c -o buggy_asan
   ./buggy_asan 3
   ```

3. **GDB Session:**

   ```bash
   gdb ./buggy
   (gdb) break main
   (gdb) run 6
   (gdb) print arr[10]
   (gdb) backtrace
   ```

4. **Static Analysis:**
   ```bash
   clang-tidy buggy_program.c -- -I.
   cppcheck buggy_program.c
   ```

**Experiments:**

- Fix all bugs systematically
- Use GDB to step through code
- Practice with Valgrind
- Enable all compiler warnings (-Wall -Wextra)
- Try different sanitizers
- Create your own buggy code to practice

### Reflection Questions

1. **Debugging:**

   - What's your debugging process?
   - How do you isolate bugs?
   - What tools do you reach for first?

2. **Prevention:**

   - How do you prevent bugs?
   - What role do tools play?
   - How do you catch bugs early?

3. **Skills:**
   - What makes a good debugger?
   - How do you improve debugging skills?
   - What's the most important skill?

---

# 🎓 Congratulations!

You've completed the **C Programming Self-Mastery Workbook**!

### What You've Mastered

✅ **Part 1: Foundations & Compilation** - How C works, compilation process  
✅ **Part 2: Memory Fundamentals** - Pointers, arrays, memory layout  
✅ **Part 3: Manual Memory Management** - malloc/free, debugging leaks  
✅ **Part 4: Structured Data** - Structs, data structures, function pointers  
✅ **Part 5: Strings & File I/O** - Safe string handling, file operations  
✅ **Part 6: Preprocessor** - Macros, headers, conditional compilation  
✅ **Part 7: Systems Programming** - System calls, processes, IPC  
✅ **Part 8: Advanced Memory** - Alignment, cache optimization, bit manipulation  
✅ **Part 9: Production Quality** - Error handling, testing, debugging

### You Now Have Deep C Mastery

You understand C at a level where:

- ✅ You can read and understand operating system code
- ✅ You write memory-safe, performant code
- ✅ You debug complex issues systematically
- ✅ You understand what's happening at the machine level
- ✅ You can build production-quality systems software

### What's Next?

#### Option 1: Specialize in Systems

- **Operating Systems** - Build schedulers, file systems, device drivers
- **Embedded Systems** - Program microcontrollers, real-time systems
- **Network Programming** - Sockets, protocols, high-performance servers
- **Game Engine Development** - Graphics, physics, entity systems
- **Database Internals** - Storage engines, query optimization

#### Option 2: Advanced Topics

- **Concurrent Programming** - Threads, mutexes, lock-free data structures
- **Compiler Development** - Lexers, parsers, code generation
- **Performance Engineering** - SIMD, cache optimization, profiling
- **Security** - Exploit prevention, cryptography, secure coding

#### Option 3: Contribute to Real Projects

- **Linux Kernel** - Device drivers, subsystems
- **Redis** - Data structures, networking
- **SQLite** - Database engine
- **Git** - Version control internals
- **Any major C project** - You're now ready!

### Keep Growing

- **Build projects** - Apply what you learned
- **Read source code** - Study great C codebases
- **Contribute to open source** - Give back
- **Teach others** - Best way to solidify knowledge
- **Stay curious** - Keep exploring and asking "why?"

---

**You're now a C master. The world of systems programming is open to you. Go build something amazing! 🚀**
