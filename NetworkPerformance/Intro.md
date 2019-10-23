A hosted virtualization strategy for I/O devices offers excellent flexibility and portability but at a potential tradeoff
in performance for high throughput devices. Due to its nature, the hosted architecture incurs the following overheads: 

1. A world switch from the VMM to the host is required whenever the virtual machine needs to access real hardware 
2. I/O interrupt handling potentially involves the VMM, host OS, and guest OS interrupt handlers 
3. A packet transmission by the guest OS involves two device drivers - one in the guest and one on the host
4. there is an extra copy from the guest OS’s physical memory to the host OS’s kernel buffers on a packet transmit. 

Since these overheads consume CPU cycles, a system that is natively capable of saturating a high performance Ethernet link might instead become CPU bound when run within a virtual machine.