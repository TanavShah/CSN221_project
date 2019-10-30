# Virtualizing I/O Devices

Every VMware virtual machine is configured from the same set of potential virtual devices. In order to virtualize an I/O device, the VMM must be able to intercept all I/O operations issued by the guest operating system. On a PC, those accesses are generally done via special privileged IA-32 IN and OUT instructions. These are trapped by the VMM and emulated either in the VMM or the VMApp by software that understands the semantics of the specific I/O port accessed. Any accesses that interact with the physical I/O hardware must be handled in the VMApp, but the VMM can potentially handle accesses that do not interact with the hardware. 

Restricting virtual devices to only a subset of available PC hardware greatly reduces the number of I/O ports that must be handled and the breadth of possibilities that handlers need to understand.

Virtualizing I/O devices with the hosted architecture can incur overhead from world switches between the VMM and the host, and even from the expense of handling the privileged instructions used to communicate with the hardware. However, these overheads matter only for devices with either high sustained throughput or low latency. The keyboard, for example, is perfectly suited to hosted virtualization.
