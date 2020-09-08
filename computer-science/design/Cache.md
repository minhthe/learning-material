1. Cache stampede
- a type of failure that can occur when a system with
cache mechanism come under high load.
- request => cache miss => re-compute, it takes long time =>
a massive number of other requests come and see the cache miss
=> massive number of re-compute requests => system down
- Solution:
1. Using lock
- If cache miss
- Create a global lock
    - if can create => recompute => update the cache => release the lock, return the value
    - else: => there is a recompute process ongoing =>
        - return error `or`
        - wait for the recompute complete `or`
        - return a default value
        
        
2. Write policy
- Write through
    - write both to cache and DB
    - wait for both success => return to the client
- Write back        
    - write only to cache => return to the client
    - update the DB async: can use a queue
