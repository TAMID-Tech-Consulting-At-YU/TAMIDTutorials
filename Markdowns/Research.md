# Research
I am writing this while researching Node.js. It's most definitely not required reading. It's more for my quick references, but I chose to put it on here for those that want to delve into depth on this topic. If you see that I misunderstood something, please let me know. I don't want to be passing misinformation. 
## Node.js Architecture

Road map for understanding Node.js architecture: 
1. We must understand how Virtual Machines (VM) can emulate operating systems and processes to utilize a computer's physical hardware.
2. We can then understand how WebAssembly uses a VM to (compile) parse and execute JavaScript in a web browser.
3. Steps 1 and 2 will make it easy to understand how Google's V8 engine parses, compiles, and executes JavaScript in Node.js.
4. After these steps, we will take a small dive into the C++ library libuv, which will explain how Node.js achieves its parallel performance.


### Virtual Machines (VMs)
In computer science, a [Virtual Machine](https://en.wikipedia.org/wiki/Virtual_machine) (VM) is a virtualization/emulation of a computer system. Some virtual machines emulate entire operating systems, while others emulate individual processes. 

Functions of virtual machines that run systems include running multiple operating systems on the same computer, consolidating servers, and much more. 

Virtual machines are also known as Managed Runtime Environments (MRE), which run and manage a single process inside an OS. The advantage of an MRE is to allow a platform-independent programming environment that abstracts away any underlying architecture (Operating Systems).

A popular VM is one most of us are familiar with, the Java Virtual Machine (JVM), which compiles and runs Java code. See the [Java Development Kit](https://www.geeksforgeeks.org/differences-jdk-jre-jvm/) for more info.
### WebAssembly

WebAssembly is an instruction set ([Assembly Language](https://en.wikipedia.org/wiki/Assembly_language)), similar to the one running on your computer right now to interpret code and communicate with your computer's hardware. However, it communicates with a VM inside the web browser.

"WebAssembly is a new type of code that can be run in modern web browsers — it is a low-level assembly-like language with a compact binary format that runs with near-native performance and provides languages such as C/C++, C# and Rust with a compilation target so that they can run on the web. It is also designed to run alongside JavaScript, allowing both to work together." - [MDN Web Docs](https://developer.mozilla.org/en-US/docs/WebAssembly)

### Googles V8 Engine
[V8](https://www.geeksforgeeks.org/how-v8-compiles-javascript-code/) is an open-source JavaScript WebAssembly engine that parses, compiles, and executes code. 
1. Parsing: The code is parsed and converted to an [Abstract Syntax Tree](https://en.wikipedia.org/wiki/Abstract_syntax_tree) (AST). 
2. Compiling: The V8 uses an interpreter to read code line by line to turn into byte code. It also uses a compiler to scan the entire document and optimize the byte code. [Compiler vs Interpreter](https://www.geeksforgeeks.org/compiler-vs-interpreter-2/). 
3. "Execution Phase: The byte code is executed by using the Memory heap and the Call Stack of the V8 engine’s runtime environment. Memory Heap is the place where all the variables and functions are assigned memory. Call Stack is the place where each individual functions, when called are pushed to the stack, and popped out after their execution. When the interpreter interprets the code, using an object structure, where the keys are the byte code and the values the functions which handle the corresponding byte code. The V8 engine orders the values in the form of a list in memory, which is saved into a Map thereby saving a lot of memory."
4. Garbage Collection: Uses a [Mark and Sweep Algorithm](https://www.geeksforgeeks.org/mark-and-sweep-garbage-collection-algorithm/) 

### Event Loop
[This](https://nodejs.org/en/docs/guides/event-loop-timers-and-nexttick/) is a great article about the call stack and schedule of events in the event loop.  
