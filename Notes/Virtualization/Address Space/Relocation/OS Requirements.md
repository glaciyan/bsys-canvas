|OS Requirements|Notes|
|-|-|
|Memory management|Need to allocate memory for new processes; Reclaim memory from terminated processes; Generally manage memory via free list|
|Base/bounds management|Must set base/bounds properly upon [[Context-Switch]]|
|Exception handling|Code to run when exceptions arise; likely action is to terminate offending process; Setting the [[Trap (System Call) Table]]|

- When a process is terminated the OS has to reclaim all of its memory for use in other processes or the OS
- **Save and restore** **base and limit** registers on **context switch**, maybe on the PCB. It can also happen that the OS moves the address space to another location.