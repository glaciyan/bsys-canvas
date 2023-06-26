There are 2 Phases to this improved Direct Execution Protocol.

1. The Kernel initializes the **Trap Table**
2. When running a process, the Kernel sets up a few things (e.g., allocating a node on the process list, allocating memory) before using `return-from-trap` to switch to user mode and start running the program.

|OS @ Boot|Hardware|
|-|-|
|initialize trap table||
||remember address of syscall handler|

|OS @ run (kernel mode)|Hardware|Program (user mode)|
|-|-|-|
|Create entry for process list|||
|Allocate memory for program|||
|Load program into memory|||
|Setup user stack with argv|||
|Fill kernel stack with reg/PC|||
|`return-from-trap`|||
||restore regs
||(from kernel stack)
||move to user mode
||jump to main
|||Run main()
|||...
|||Call system call
|||`trap` into OS
||save regs
||(to kernel stack)
||move to kernel mode
||jump to trap handler
|Handle trap|||
|Do work of syscall|||
|`return-from-trap`|||
||restore regs
||(from kernel stack)
||move to user mode
||jump to PC after trap
|||...
|||return from main
|||`trap` (via `exit()`)
|Free memory of process|||
|Remove from process list|||