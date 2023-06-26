The OS creates an abstraction for a running programs memory. Each program has its own view of some memory. So **every address you see in a user-level program is just virtual** and only the OS knowns the **true physical address**.

It's **transparent (invisible)** to make it easier for the programmer to use memory.

> [!example] Generally
> The memory contains:
> - The code of the program
> - A Stack, for local vars, function call chains, paramters, and return values
> - A Heap for dynamically allocated and long living memory (`malloc`)
> - static variables, and so on...

The illusion is that the programs code starts at 0, **but it's just at some arbitrary physical address(es)**. So when the program wants to start at address 0, **the OS with some hardware help (MMU)** will make sure it loads the correct physical address.

Because program code doesn't change (is static) it's very easy to place into memory. The heap and stack are another story, they both want to grow. This is why we put **the heap at the top** and **let it grow positively**, and the **stack is put at the bottom** and **grows negatively**.

When threads come into play there isn't a nice way for this to work in an address space.

![[Pasted image 20230330115947.png]]

