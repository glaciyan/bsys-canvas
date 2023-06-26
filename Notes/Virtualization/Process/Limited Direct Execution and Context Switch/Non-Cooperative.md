## Timer interrupt

A timer device hardware can be programmed to *raise an interrupt every so many milliseconds*; when the interrupt is raised, the currently running process is halted, and a pre-configured **interrupt handler** in the OS runs.

Usually an **interrupt handler** does this:
1. The currently running process is halted.
2. Save enough of the state of the program.
3. A pre-configured interrupt handler in the OS runs.

> [!success]
> A timer interrupt gives OS the ability to run again on a CPU.

> [!note]
> The OS has to start this timer.

> [!warning]
> The interrupts are non-deterministic and feel random. Because of the interrupts, normal processes get interrupted (and maybe there isn't anything else to run), and it doesn't run for a little bit -> longer (and sometimes different) runtime.