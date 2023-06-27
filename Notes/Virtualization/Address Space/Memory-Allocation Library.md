The **management of memory is done by the library** ***NOT the OS*** this is why **they are not system calls**. But when there is no more memory to allocate the library will use system calls to request for more. The syscalls are:

- `brk` - change the location of the programs **break**: the location of the end of the heap. This will either decrease or increase the size of the heap.
- `sbrk` - uses an increment but serves a similar purpose

> [!warning]
> You should never call `brk` or `sbrk` by yourself. They are used by the MAL, this will confuse it!

