1. Deadlock
- each member of a group is waiting for some other member to release a 
resource

```java
    void method1() {
        synchronized(Integer.class) {
            synchronized(String.class) {
                
            }
        }
    }
    
    void method2() {
        synchronized(String.class) {
            synchronized(Integer.class) {
            
            }
        }
    }
    
    Thread t1 = new Thread(() => method1());
    Thread t2 = new Thread(() => method2());
    
    t1.start();
    t2.start();
    
```

- detect:
    - look for nested synchronized block, synchronized block calling other
    - analyze the thread dump
2. Livelock
- 2 or more process continually repeat the same interaction in response to changes
in other process without doing any useful work.
- Example: 
    - T1 acquired R1, T2 acquired R2.
    - T1 tries to acquire R2 but cannot => T1 release R1
    - T2 tries to acquire R1 but cannot => T2 release R2
- Avoid livelock
    - let thread retry acquire lock at random intervals    

