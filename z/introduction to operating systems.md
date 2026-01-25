
>[!question] What happens when a program runs

- It executes instructions. In each instruction cycle, the processor **fetches** an instruction from memory, **decodes** it and **executes** it.


**Operating System**

The body of the software that makes it easy for us to run programs (even allowing us to run many at the same time), allowing program to share a memory, enabling programs to interact with devices, and other fun stuff like that.


**OS as Virtual Machine**

The OS takes a **physical** resource (such as the processor, or memory, or a disk) and transforms it into a more general, powerful, and easy-to-use **virtual** form of itself. Thus, we sometimes refer to the operating system as a **virtual machine**.


**OS as Standard Library**

A typical OS, in fact, exports a few hundred **system calls** that are available to applications. Because the OS provides these calls to run programs, access memory and devices, and other related actions, we also sometimes say that the OS provides a **standard library** to applications.


**OS as Resource Manager**

Finally, because virtualization allows many programs to run (thus sharing the CPU), and many programs to concurrently access their own instructions and data (thus sharing memory), and many programs to access devices (thus sharing disks and so forth), the OS is sometimes known as a **resource manager**.


---
## virtualizing the cpu

Turning a single CPU (or a small set of them) into a seemingly infinite number of CPUs and thus allowing many programs to seemingly run at once is what we call **virtualizing the CPU**.

## virtualizing the memory

Memory is just an array of bytes.

A program data structure and instructions lie in memory. Hence memory is accessed on each instruction fetch and to access or update the data.

**Process Identifier (PID)** : unique id of a running process

Each process accesses its own private **virtual address space** (sometimes just called its **address space**), which the OS somehow maps onto the physical memory of the machine. A memory reference within one running program does not affect the address space of other processes (or the OS itself);

## concurrency

Suppose there are two threads which increments the value of a variable **a** by 1. There's also a variable **loops** which determine how many times we'll increment a.

**Case-1** : If **loops** is set to 1000 then we get the final value of a = 2000 (which is what we expected)
**Case-2** : If **loops** is set to 100000 then we get the final value of a = 137911 (which will be different each time we execute the program)

The reason for these odd and unusual outcomes relate to how instructions are executed, which is one at a time. Unfortunately, a key part of the program above, where the shared counter is incremented, takes three instructions: one to load the value of the counter from memory into a register, one to increment it, and one to store it back into memory. Because these three instructions do not execute **atomically** (all at once), strange things can happen.


## persistence

DRAM is **volatile**, hence we need **hard drive** or **SSDs** to store data **persistently**.

The software in the operating system that usually manages the disk is called the **file system**.

Unlike the abstractions provided by the OS for the CPU and memory, the OS does not create a private, virtualized disk for each application. Rather, it is assumed that oftentimes, users will want to **share** information that is in files. For example, when writing a C program, you might first use an editor (e.g., Emacs) to create and edit the C file (`emacs -nw main.c`). Once done, you might use the compiler to turn the source code into an executable (e.g., `gcc -o main main.c`). When you’re finished, you might run the new executable (e.g., `./main`). Thus, you can see how files are shared across different processes.

## design goals

1. **Abstraction** : to make the system convenient and easy to use
2. **High performance and minimum cost** : Virtualization shouldn't come at any cost. These cost arise in extra time (more instructions) and extra space (in memory or on disk)
3. **Protection** : **provide** protection between applications, as well as between the OS and applications.
4. **Reliability** : The operating system must also run non-stop; when it fails, _all_ applications running on the system fail as well.
5. **Energy efficient**


## some history

### early operating systems: just libraries

For example, instead of having each programmer of the system write low-level I/O handling code, the “OS” would provide such APIs, and thus make life easier for the developer.

Usually, on these old mainframe systems, one program ran at a time, as controlled by a human operator. This mode of computing was known as **batch** processing, as a number of jobs were set up and then run in a “batch” by the operator.

![[batch-processing.png]]


## beyond libraries: protection

Idea of **system call** was invented to make the transition into OS a more formal, controlled process. The key difference between a system call and a procedure call is that a system call transfers control (i.e., jumps) into the OS while simultaneously raising the **hardware privilege level**.

![[user-kernel-mode.png]]


## the era of multiprogramming

computers became cheaper because of the introduction of **minicomputer** and now a small collection of people in the organization could get their own computer.

**multiprogramming** became commonplace due to the desire to make better use of machine resources.

Instead of just running one job at a time, the OS would load a number of jobs into memory and switch rapidly between them, thus improving CPU utilization. This switching was particularly important because I/O devices were slow; having a program wait on the CPU while its I/O was being serviced was a waste of CPU time.


## the modern era

**personal computer** by Apple and IBM lead to one machine per desktop instead of a shared minicomputer per workgroup.


