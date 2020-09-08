##### Concept
- Thread is unit of CPU utilization
- Thread creation is cheaper than process creation
- Thread context switching is cheaper than process's 
- Kernel thread: thread created and managed by OS
- User thread: thread created and managed by programing languague

##### Thread pool
- create a fixed number of thread at the process startup and put them into
a pool
- when server receives a request, it awakens a thread from this pool if 
one is available
- once the thread completes its service, it returns to the pool
##### Amdahl law

```
speedup = 1 / (S + P/n)
S: portion of app that must be executed serially
P: portion of app that can be executed in parallel
```


