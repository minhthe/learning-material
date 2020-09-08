##### Concepts
- process is a program in execution
- 1 process per processor
- states:
    - new
    - running
    - waiting
    - ready
    - terminated
- context switching: the task happens when OS switch the CPU
from a process to another: save the context of old process to its PCB
and load saved context of new process to run.  
- **address space**: the set of memory addresses that the process can use without error.    
##### Interprocess communication

![](../images/process.png)

1. Shared memory
- establish a region of shared memory
- processes are responsible for data, location and read/write control
- fast

2. Message passing
- useful in distributed system
- slower than shared mem

##### Process operation
- creation
    - fork() create a new process with identical address space as the parent process
    - both processes will continue to execute the next line of instruction (because they have 
    the same address space)
- termination
    - exit(): ask OS to delete it
    - process becomes zombie
    - parent process call wait() to resume, child process entry in process table is released
    
##### System call
- the way a process can request service from kernel
- kernel: 
    - interface between software and hardware
    - the core part of OS
    - task management, memory management, disk management, process management

##### Process synchronization
- **Race condition**: the situation in which multiple processes access and manipulate the same
data concurrently and the outcome depends on the order in which the access take place.
- **Critical section**: each process has a segment of code in which it can change
common variables, updating table, writing to a file ... When a process is executing
its critical section, no other processes is executing in their critical section.

- Locks:
    - Mutex
        - lock based approach
        - spinlock
        ```
            acquire() {
                while (!avai);
                avai = false;
            }
            
            release() {
                avai = true;
            }
        ```
        - disadvantage:
            - busy waiting
    - Semaphore
        - signaling approach
        - Semaphore S is an integer can be access by wait() and signal() 
        as number of available resource
        
        ```
            wait() {
                while (S <= 0);
                S--;
            }
            
            signal() {
                S++;
            }
        ```
        - Binary semaphore: S can be 0 or 1 <=> mutex
        - Counting semaphore: unrestricted domain for S
##### COW
- Copy on Write
- a technique allow child process and parent process to initially share
same pages
- whenever a process modify a page, a copy of that page is created and mapped
to address space of the process.

![](../images/process.png)
