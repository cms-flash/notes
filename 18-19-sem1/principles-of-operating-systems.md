# Principles of Operating Systems

# Introduction

- An operating system is a program that controls and serves the execution of other programs.

- Functions of an OS:

  - Process management;

  - Memory management;

  - Concurrency;

  - Persistence.

- An OS should aim to provide a reliable and easy-to-use interface to applications over a diverse range of hardware backends in an efficient and protected manner.

- Layers of programs:

  - Kernel layer;

  - Service layer;

  - Command layer and application layer.

- Modes of a CPU:

  - Kernel mode;

  - User mode.

- OS architectures:

  - Monolithic;

  - Layered;

  - Microkernel;

  - Modularized monolithic.

# Processes

- A process is a running instance of a program.

- A single-thread process is characterized by:

  - A memory space;

  - A register context.

- Structure of a memory space:

  - Text segment;

  - Data segment;

  - Heap;

  - Stack.

- Life cycle of a process:

  - New;

  - Ready;

  - Running;

  - Blocked;

  - Suspended ready;

  - Suspended blocked;

  - Terminated.

- Process management data structures:

  - Process control block:

    - Process ID;

    - Execution state;

    - Register context;

    - Scheduling information;

    - Credentials;

    - Memory management information;

    - Accounting information;

    - Pointer to parent;

    - Pointers to children;

    - Pointers to resources.

  - Process table, which maps a PID to a PCB;

  - Process queues:

    - Ready queue;

    - Blocked queue;

    - Running pointer.

- Signals:

  - A signal is an inter-process message with a predefined intention.

  - Synchronicity of a signal:

    - Synchronous;

    - Asynchronous.

  - Actions upon a signal:

    - Catching;

    - Ignoring;

    - Masking.

  - A caught signal triggers the registered signal handler for its type.

  - Actions upon SIGKILL and SIGSTOP cannot be overridden.

# CPU Virtualization

- An OS virtualizes the CPU by context switches, serves processes via system calls, and preempts non-cooperative applications through interrupts.

- System calls:

  - A system call is an applications request to the OS for a kernel service.

  - Life cycle of a syscall:

    - Trap instruction;

    - Mode switch;

    - Invocation of syscall function;

    - Un-trap instruction;

    - Mode switch.

  - Common syscalls:

    - Fork, that duplicates the current process under a new PID.

    - Exec, that loads a new program image into the current process;

    - Wait, that waits for the termination of child processes.

- Context switch:

  - A context switch swaps the context of the current application process with that of another application process.

  - Life cycle of a context switch:

    - Context saving;

    - State update of the current process;

    - Queue replacement of the current process;

    - Selection of the new process;

    - Context loading;

    - State update of the new process;

    - Mode switch.

  - Overheads of a context switch:

    - Explicit overheads;

    - Implicit overheads:

      - Cache misses;

      - Memory misses.

- Interrupts:

  - An interrupt is a hardware message delivered to the processor.

  - Types of interrupts:

    - Hardware interrupts;

    - Synchronous self-interrupts;

    - Asynchronous self-interrupts;

    - Software interrupts.

- OS reclamation of the processor:

  - Voluntarily via syscalls;

  - Involuntarily via interrupts.

# Scheduling

- Scheduling refers to the temporal allocation of processor resources to processes.

- Levels of scheduling:

  - High level scheduling, which manages process creation;

  - Middle level scheduling, which manages process suspension and resumption;

  - Low level scheduling, which manages process scheduling onto and de-scheduling from processors.

- Related definitions of scheduling:

  - Turnaround time, time between arrival and completion;

  - Wait time, difference between turnaround time and service time;

  - Response time, time between arrival and initial execution;

  - Response ratio, ratio between projected turnaround time and service time.

- Basic scheduling algorithms:

  - First in first out;

  - Shortest job first;

  - Highest response ratio first;

  - Shortest time to completion first;

  - Round robin.

- Multi-level feedback queues:

  - There are multiple queues with descending priorities;

  - Higher-priority jobs prevail;

  - Jobs with the same priority are scheduled in a round-robin fashion;

  - New jobs enter with the highest priority and get demoted if using up a quantum or total time quota at the level;

  - The time quantum size grows exponentially as priority lowers;

  - All jobs get boosted to the highest priority periodically.

- Fair share scheduling:

  - Fair share scheduling aims to allocate a predefined fair share of CPU resources to each process.

  - Fair share scheduling though lottery:

    - A fixed number of tickets are created;

    - Each process gets some tickets, indicating its fair share;

    - At each scheduling point, a lottery is performed, and the owner of the drawn ticket is scheduled.

  - Completely fair scheduling by Linux:

    - The runtime of each process is recorded, normalized by its weight;

    - At each scheduling point, the process with the least normalized runtime is scheduled.

# Concurrency

- Threading:

  - A thread is a running sequence of instructions.

  - A thread is characterized by a register context, a stack, and its membership in a process.

  - A multi-thread process is characterized by a memory space and a set of member threads.

  - Life cycle of a thread:

    - Creation;

    - Execution;

    - Termination;

    - Joining.

  - Linux implements threads as light-weight processes, which are spawned by cloning instead of forking.

- Concurrency issues:

  - A race condition is when the final value of a datum depends on the execution order of several processes that updates it concurrently.

  - A critical section is a minimal section of code that updates a shared datum.

  - An atomic operation is one that is guaranteed to finish without preemption once started.

- Locks:

  - A lock is a flag indicating whether any thread is in a critical section for a datum.

  - Properties of a lock:

    - It can be acquired by at most one thread at any time.

    - A thread cannot enter a critical section for a datum without acquiring the lock.

  - Implementations of a lock:

    - Interrupt masking:

      - Interrupts are marked during the atomic;

      - This does not work on multi-core systems and is vulnerable to non-cooperation.

    - Atomic instructions:

      - The test-and-set instruction returns the current value of a variable and updates it with a new one atomically.

      - The compare-and-swap instruction tests if the variable is equal to a given expectation, updates it with a new value if equal, and returns the original value atomically.

    - Mutexes:

      - The mutex is the POSIX implementation of the lock.

      - The OS blocks a thread attempting to acquire a locked lock.

- Synchronization:

  - Synchronization is the guarantee of execution order between or among a set of statements across threads.

  - Condition variables:

    - A conditional variable sets up a pool for resource distribution;

    - A wait adds a process to the pool and blocks it;

    - A signal pops a process from the pool and unblocks it.

  - Semaphores:

    - A semaphore sets up a queue for resource distribution and an integer flag;

    - A wait decrements the flag, and adds a process to the queue and blocks it if the flag is now negative;

    - A post increments that flag, pops the head of the queue, and unblocks it.

- Deadlocks:

  - Necessary conditions for a deadlock:

    - Mutual exclusion;

    - Hold-and-wait;

    - No preemption;

    - Circular wait.

  - Dealing with deadlocks:

    - Prevention:

      - Atomic request bags;

      - Preemption;

      - Resource ordering;

    - Avoidance:

      - Avoidance by scheduling;

      - Banker's algorithm, i.e. avoidance by granting;

    - Detection and recovery:

      - Abort-all;

      - Abort-till-success.

# Memory Virtualization

- Purposes of memory virtualization:

  - Memory sharing among applications;

  - Accomodation of oversided memory spaces;

  - Memory integrity protection.

- Each application sees a contiguous memory space starting from 0 through its virtual addresses.

- Memory address translation:

  - The memory management unit:

    - Translates virtual addresses to physical addresses;

    - Checks for segmentation faults.

  - The OS:

    - Manages address space profiles;

    - Maintains memory allocation records.

- Segmentation:

  - Segmentation divides an address space to fixed-length segments and allocates them memory independently and contiguously per their used sized.

  - With segmentation, the first few bits of a logical address represent the segment id, and the remainder stores the offset.

  - Organization of a segment descriptor:

    - Base;

    - Bound;

    - Flags:

      - Grow bit;

      - Read bit;

      - Write bit;

      - Execute bit;

      - Valid bit.

  - The segment table of a process holds the descriptors for all segments of it.

  - Memory organization with segmentation:

    - A segment is a minimal contiguous unit for memory allocation.

    - A segment is alloted memory per its used size, rather than maximum size.

  - Fragmentation with segmentation:

    - Memory fragmentation is the phenonmenon that the free space is scattered in small pieces, characterized by the situation when no single piece can accomodate an incoming segment while the total free space can.
      - Combating fragmentation:
        - Memory allocation algorithms:

          - Best fit;

          - Worst fit;

          - First fit;

          - Next fit.

        - Coalesing;

        - Compacting.

- Paging:

  - Paging divides an address space into fixed-length pages and allocates them memory independently and contiguously in fixed frames of the same length.

  - With paging, the first few bits of a logcial address represents the page number, while the remainder stores the offset.

  - Organization of a page descriptor:

    - Frame id;

    - Flags:

      - Read bit;

      - Write bit;

      - Execute bit;

      - Valid bit;

      - Present bit;

      - Reference bit.

  - With paging, each present page is allocated to a frame.

  - The page table of a process holds the descriptors for all pages of it.

- Practical paging:

  - With naive paging, each logical memory access incurs two physical accesses, and the page table is exceedingly large in a modern architecture.

  - Elements of practical paging:

    - Page table buffer;

    - Hierarchical page tables.

  - Page table buffer:

    - Page table buffer is a dedicated cache for page tables in the MMU.
