When a *timer Interrupt* occurs the **user registers** are being saved to the *kernel stack* before switching into the OS. This is done by the *hardware*.

The other type of save/restore is when the OS does a [[Context-Switch]]. This time the **kernel registers** are all being saved *by the software* into the PCB of the process. This moves the system from running one process into running another.