Basically the API of the OS. Calls like `open()` or `read()` look like normal procedure calls in C, this is because *they are procedures*. But hidden inside them is the `trap` instruction. The `trap` instruction is provided by the hardware.

The library which defines calls like `open()` uses an **agreed-upon calling convention with the Kernel**.
1. It puts the *arguments of the call into well-known locations* (e.g., on the stack, or in specific registers).
2. It pust the **system-call number** (code) into a well-known location as well.
3. Execute the `trap` instruction.
4. Handle return from `trap`.
5. Give control back to the program.

> [!success]
> This is **more secure** because the program has to **request** a particular service (here system-call) via number.

The parts of the C library that make system calls are hand-coded in assembly because they need to execute the hardware-specific trap instruction.