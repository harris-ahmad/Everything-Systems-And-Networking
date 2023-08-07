# Chapter 4 - Processes

- [Chapter 4 - Processes](#chapter-4---processes)
  - [Important Terms and Concepts](#important-terms-and-concepts)
  - [Process API](#process-api)
  - [How are process created?](#how-are-process-created)
  - [What are the different states of a running process?](#what-are-the-different-states-of-a-running-process)

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

The following are the functions that are used to create and manage processes.

- **Create**: An operating system must include a mechanism to create a new process. For example, opening a new program in Windows or Linux creates a new process.
- **Destory**: Similar to opening a new process, there should be a way to forcefully forfeit a process. This is done by the `kill` command in Linux.
- **Wait**: A process may need to wait for another process to finish before it can continue. This is done by the `wait` command in Linux.
- **Status**: A process may need to know the status of another process. This is done by the `status` command in Linux.

## How are process created?

The first thing that the OS must do is to load its code and any static data into the address space (memory) of the process. Programs reside in the persistance storage as executables. Now, modern OS load the programs into the memory *lazily* meaning that they only load the parts of the program that are needed. To understand how *lazy loading* works, it's important to dig deeper into concepts such as **paging** and **swapping** - we will get to those later.

Before running a process, the OS allocates some memory to the run-time stack. C programs depend on the stack for local variables, function parameters, and return addresses. 

The OS will also likely initialize the stack with arguments; specifically, it will fill in the parameters to the `main()` function, i.e., `argc` and the `argv` array.

The OS will also initialize the heap. The heap is used for dynamic memory allocation. The OS will also initialize the heap with the `malloc()` function. The allocated memory is explicitly freed by the `free()` function.

The OS will also initialize the file descriptors. The file descriptors are used to read and write to files. There are descriptors for standard input, standard output, and standard error. The standard input is used to read from the keyboard. The standard output is used to write to the screen. The standard error is used to write error messages to the screen.

## What are the different states of a running process?

In this section, we talk about the different states a running process can be in. In a simplified view, a process can be in one of the following states:
- **Running**: The process is running on a processor meaning it's executing instructions.
- **Ready**: The process is ready to run but is waiting for the processor to become available.
- **Blocked**: The process is waiting for some event to occur (e.g., waiting for a file to be read from the disk).