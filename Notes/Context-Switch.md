Context switch is the process of storing the state of a process or thread, so that it can be restored and resume execution at a later point, and then restoring a different, previously saved, state.

This **time-sharing** mechanism is employed by all modern OSes.

> [!NOTE]
> Deciding which process should run next is done by a **scheduler**.

- The hardware **saves a few register values** for the current process onto its kernel stack and switches to kernel mode and jumps to the trap handler
	- General purpose registers
	- PC
	- kernel stack pointer
- The OS decides which process to run (**scheduler**)
- `switch()` routine called, saving current register values into the PCB
- `switch()` then loads the PCB register values of the soon-to-be-executing
- We **switch context** by changing the SP to the other **Kernel stack**
- `return-from-trap` now **restores the Kernel stack** in the hardware of the other process and runs it correctly

> [!example] Example Context Switch

Bilder auf den Folien (6) S. 22-32

1. We start **running in User mode** Stack Pointer (SP) points to **User stack**
2. Take an exception, syscall, or interrupt, and we switch to the **kernel stack**
3. We push a trapframe (exception frame, user-level context) on the stack. This includes the PC and SP.
4. We execute the code to process a syscall, exception, or interrupt
5. Results in a "C activation stack" building up, since code of the OS is executed.
6. After the Kernel choose a process it pushes the remaining kernel context onto the stack

![[Pasted image 20230327180031.png]]

 7. Save the SP into the PCB
 8. Point the SP to the next target.

![[Pasted image 20230327180256.png]]

9. Load Kernel State, "C activation stack" where we left it off and user-level context.
10. Point SP back to User stack

![[Pasted image 20230327180646.png]]
