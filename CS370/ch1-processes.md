# Chapter 4 - Processes

- [Chapter 4 - Processes](#chapter-4---processes)
  - [Important Terms and Concepts](#important-terms-and-concepts)
  - [Process API](#process-api)

## Important Terms and Concepts

> The fundamental and informal definition of a process is a program in execution.
- By running one process and stopping it, we can run another process and stop it, and so on. This is done so by the virtualization of the CPU. **Virtualization** implies that there are multiple CPUs when in reality there is only one or few physical CPUs. This sharing of CPUs is known as **time sharing**.
- Policies in an operating system are policies that decide what process to run next. The **scheduler** is the part of the operating system that makes the decision of what process to run next. A **scheduling policy** is likely to make this decision based on historical information (e.g., which program has run more over the last minute), performance metrics, etc to make this decision.

> The abstraction provided by the OS of a running program is something we will call a **process**.

- To understand what constitutes a process, we thus have to understand
its **machine state**. 

> A machine state is what a program can read or update when it is running.

- Program instructions and the data needed by the instructions reside in the memory, so *memory* is an important component that comprises a process.
- The memory that a process can address is known as the **address space**.
- Processes read or update **registers**. 

> Many instructions explicitly read or update registers and thus clearly they are important to
the execution of the process.

- The **program counter** is a register that contains the address of the next instruction to be executed. It is also known as the **instruction pointer**.
- A **stack pointer** and a **frame pointer** are registers that are used to keep track of the stack. The stack is used to store local variables and function parameters. The frame pointer is used to keep track of the current stack frame. The stack pointer is used to keep track of the top of the stack.

## Process API

