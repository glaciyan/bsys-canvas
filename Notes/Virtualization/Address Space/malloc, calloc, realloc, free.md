[docs](https://man7.org/linux/man-pages/man3/malloc.3.html)

allocate and free dynamic memory

`calloc` allocates and zeros the memory
`realloc` make a new larger region of memory and copy the old region over

> [!bug] Not Allocating Enough Memory
> 
> ```c
> char *src = "hello";
char *dst = (char *) malloc(strlen(src)); // too small!
strcpy(dst, src); // work properly
> ```

> [!bug] Forgetting to Initialize Allocated Memory
> When you `malloc` and forget to set it to a value and read it. If you do forget, your program will eventually encounter an **uninitialized read**, where it reads from the heap some data of unknown value. Something random and harmful might happen.

> [!bug] Forgetting To Free Memory
> A **Memory Leak**. Memory leaks will collect over time for long running programs (e.g. OSes) and will eventually lead to running out of memory.

> [!bug] Freeing Memory Before You Are Done With It
> Sometimes you might free memory before you are done using it. This is called a **dangling pointer**. Might crash your program or overwrite valid memory (if some other `malloc` now owns this memory).

> [!bug] Double Free
> When you call `free` more than once on the same memory. The MAL might get confused by this and sometimes crash your program or do other weird things. One tactic would be to set your pointers to `NULL` after you freed them.

> [!bug] Invalid frees
> When you call `free` with something that is not a pointer or e.g. the middle of an array. These error is dangerous.

