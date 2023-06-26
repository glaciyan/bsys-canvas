Wait for system calls. Then decide to run something else.

The OS trusts the processes to behave reasonably.

Most processes transfer control of the CPU to the OS quite frequently by making:
1. system calls
2. `yield` instruction (sometimes in cooperative systems)
3. Doing something illegal (devide by zero, illegal memory access). This will generate a `trap` and transfer control to OS.

Examples of this kinda of system are:
- Early versions of the Macintosh OS
- The old Xerox Alto system

> [!attention]
> But what if a process never gives up control and runs in a loop? You will have to reboot.

