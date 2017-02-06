### Advantage of thread pool over original thread
* Too much parallelism causes [thrashing](https://en.wikipedia.org/wiki/Thrashing_(computer_science)), excessive switching,
 lower performance.
* Thread pool can limit the amount of parallelism by adjusting pool size. Useful when a server is serving a large amount of clients.

### Difference between thread & thread pool
* In original threading model, the server creates per thread for each incoming client (connection).
  * The main program keeps calling `accept()` in an infinite loop, spawns a thread for each accepted connection.
  * Each thread handles the connection then exits.
  * Each thread calls `detach()` by itself, its resource will be collected by OS upon termination.
* With threadpool, the server pre-spawns a set of N threads, sharing the common server socket (listening socket).
  * The main program set up the thread pool, then calls `join()`
  * Each thread keeps calling `accpet()` then handles the incoming connection in an infinite loop
  * Threads don't call `detach()` by itself, instead, its resource is `free()`ed by the main program.



##### Reference
* [UCSD CSE 124](http://cseweb.ucsd.edu/~gmporter/classes/wi17/cse124/)
