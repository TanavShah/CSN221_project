### Reducing Network Virtualization Overheads

A set of optimizations aimed at reducing the number of world switches dramatically without departing from the hosted I/O architecture.   

**Handling I/O ports in the VMM** 

Those accesses merely modify the state of the virtual Lance data port, which can be easily done directly in the VMM without a world switch.
Even though the instructions to access it are privileged instructions, the VMM can treat them as simple MOV instructions that happen to store to a special location. This allows the VMM to strip away several layers of virtualization and reduce the handling of the accesses to a handful of instructions.

**Send combining**

I/O intensive workloads have a high interrupt rate and the VMM must switch to the host whenever it takes a host IRQ. In VMware Workstation 2.0, each packet sent on the Lance adapter causes a world switch to the host to send the packet over the bridged network. Since part of the Lance data port emulation is now performed in the VMM, the VMM can delay the actual transmission until the next interrupt-induced switch to the host world. Send combining also benefits both guest and host IRQs.
Since the guest continues executing as soon as the packets are queued, there is a high probability that the guest will transmit multiple packets before the next mandatory world switch.
