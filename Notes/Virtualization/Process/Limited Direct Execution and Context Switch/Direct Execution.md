Just give the Program the CPU and run it directly.

|OS|Program|
|-|-|
|1. Create entry for process list||
|2. Allocate memory for program||
|3. Load program into memory||
|4. Set up stack with `argc / argv`||
|5. Clear registers||
|6. Execute call `main()`||
||7. Run `main()`|
||8. Execute return from `main()`|
|9. Free memory of process||
|10. Remove from process list||

## The problems

Without any *limits* on the running program the OS wouldn't be in control of anything (e.g. kill the program). "Just a library"
