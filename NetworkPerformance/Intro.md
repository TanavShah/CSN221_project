A hosted virtualization strategy for I/O devices offers excellent flexibility and portability but at a potential tradeoff
in performance for high throughput devices. Due to its

nature, the hosted architecture incurs the following over-
heads: i) a world switch from the VMM to the host is re-
quired whenever the virtual machine needs to access real

hardware, ii) I/O interrupt handling potentially involves
the VMM, host OS, and guest OS interrupt handlers, iii)
a packet transmission by the guest OS involves two device

drivers - one in the guest and one on the host, and iv) there
is an extra copy from the guest OS’s physical memory to
the host OS’s kernel buffers on a packet transmit. Since

these overheads consume CPU cycles, a system that is na-
tively capable of saturating a high performance Ethernet

link might instead become CPU bound when run within a
virtual machine.