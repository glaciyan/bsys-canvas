Holds the addresses of corresponding interrupt or exception handlers. This table is crucial for handling various events like hardware interrupts, software exceptions, and system calls.

When the machine boots up (in Kernel mode) the OS uses a special priviledged instruction (only for OS) which tells the hardware where the **Trap Table** is in memory. The hardware will remember this location until the next restart.

> [!danger]
> If anyone can set the location of the **Trap Table** you can make the OS run any kind of code.

The table has entries for System Call Number, Address to a System call function like `sys_read()`.