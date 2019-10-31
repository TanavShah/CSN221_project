# Storage in MIPS

The only way CPU can access the memory in MIPS is through load and store instructions. There is only one
addressing mode (base+displacement). Having just one addressing mode is part of the RISC philosophy to
keep instructions simple thus allowing for a simple control structure and efficient pipelining.

The kernel space cannot be directly accessed by user programs, and it is reserved for the use of the operating system.
Note that the kernel space is half of the address space (it contains those addresses that have the most
significant bit 1). The kernel space may be organized the same way as the user space (with a text segment,
data segment, stack).
The text segment contains the user code the system is executing. The data segment has two sections:
- static data, which contains the space for static and global variables; generally speaking this is the storage place for data object whose life is the same as the program’s
- dynamic data, where space is allocated for data objects at run time (typically using malloc)
The stack segment grows towards small addresses and is used for the call/return mechanism as well as to hold
local variables (those defined inside a block and which are not declared to be static).
In base+displacement addressing, a register (the base) is used together with an offset (displacement) to create
the address used to accress the memory. The displacement is an immediate value supplied in the instruction.
