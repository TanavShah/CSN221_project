### UMLinux

**UMLinux** is Type II VMM, the guest operating system and the guest applications all run as a single process on a host Linux OS. It provides a higher-level interface to the guest OS that is similar to underlying hardware.

UMLinux uses functionality from the host operating-system that maps naturally to the virtual hardware.The
guest-machine process serves as a virtual CPU; host files and devices serve as virtual I/O devices; a host
TUN/TAP device serves as a virtual network; host signals serve as virtual interrupts; and host memory mapping and protection serve as a virtual MMU. The virtual machine’s memory is provided by a host file that is mapped into different parts of the guest-machine process’s address space. We store this host file in a memory file system (ramfs) to avoid needlessly writing to disk the virtual machine’s transient state.
