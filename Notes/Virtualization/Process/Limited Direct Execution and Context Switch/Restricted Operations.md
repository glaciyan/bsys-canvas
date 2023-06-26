The process has no limits on **restricted operations** (I/O, resource access)

## Solution

Using **protected control transfer** with different **processor modes**:

1. **User mode:** Applications do not have full access to hardware resources.
2. **Kernel mode:** The OS has access to the full resources of the machine.

The Kernel can carefully expose certain features which the User can then use with **System calls**.

> [!note]
> This allows for something like a File System with Permissions.