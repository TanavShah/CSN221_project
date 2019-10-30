The experiments were performed on two Intel-based PCs that are physically connected to each other via Intel Ether-
Express 100 Mb/s Ethernet NICs and a direct, crossover cable:

**PC-350** – a 350 MHz Pentium II system with 128 MBytes of RAM running a Linux 2.2.13 kernel

**PC-733** – a 733 MHz Pentium III system with 256 MBytes of RAM running a Linux 2.2.17 kernel.

A virtual machine is configured with a virtual AMD Lance NIC bridged to the native Intel EtherExpress NIC.

The virtual machine runs a standard RedHat 6.2 Linux guest OS plus the 2.2.17-14 kernel update and uses the
standard Linux pcnet32 driver to communicate over the virtual network. This virtual machine is hosted in two configurations on VMware Workstation 2.0:

**VM/PC-350** – the virtual machine with 64 MBytes of RAM hosted by PC-350.

**VM/PC-733** – the virtual machine with 128 MBytes of RAM hosted by PC-733.