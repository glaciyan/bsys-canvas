|OS @ Boot|Hardware|
|-|-|
|initialize trap table||
||remember address of syscall handler|
|start interrupt timer||
||start timer
||interrupt CPU in X ms

|OS @ run (kernel mode)|Hardware|Program (user mode)|
|-|-|-|
|||Process A
|||...
||**timer interrupt**
||save regs(A) → k-stack(A)
||move to kernel mode
||jump to trap handler
|Handle the trap||
|Call switch() routine||
|save regs(A) → proc t(A)||
|(includes SP to kernel stack)||
|restore regs(B) ← proc t(B)||
|switch to k-stack(B) (by loading PCB)||
|**return-from-trap (into B)**||
||restore regs(B) ← k-stack(B)
||move to user mode
||jump to B’s PC
|||Process B
|||...