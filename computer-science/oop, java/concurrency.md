1. Volatile
- ensure that when a thread access a variable, it accesses directly from 
the memory, not form the thread local storage (cache)
- side effect: when a thread set a value to a variable, this change is
visible immediately to all other threads
- Volatile only ensure access atomicity not operation atomicity
- Usage: to make reading double, long atomic: both double and long are 64 bits
wide they are read in 2 parts: first 32 bit first time and last 32 bit second time

2. wait() and notify()
- wait() tell the current thread to release the lock and turns to waiting state
- notify() is used to wake up waiting thread by communicating that waiting condition is over
- a thread can be wake up without notify() so always call wait() in a loop

3. Thread-safe Singleton
```java
    public class Singleton { 
        private static Singleton instance;
        private Singleton() {}
        public static Singleton getInstance() {
            if (instance == null) {
                synchronized(Singleton.class) {
                    if (instance == null) {
                        instance = new Singleton();
                    }
                }
            }
            return instance;
        }
    }
```
