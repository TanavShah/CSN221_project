#### Introduction

As defined by IBM, a “Virtual Machine” is a fully protected and isolated copy of the underlying physical machine’s hardware. A virtual machine can be used in place of having a dedicated physical machine to write and test programs without crashing physical machine.

![Figure 1: Represents traditional organisation of virtual machine.](virtual_machine_organisation.png?raw=true "Figure 1: Represents traditional organisation of virtual machine.")

<u> Figure 1: Represents traditional organisation of virtual machine. </u>

A software layer called a _virtual machine monitor (VMM)_ controls the machine hardware. Every virtual machine is created by the VMM and behaves like a complete physical machine having its own dedicated operating system.


The monitor is the interaction layer between the Virtual Machines and Physical Machine. It gets out of the way whenever possible to allow virtual machine to interact directly with the hardware consequently maximizing performance. This direct execution property allows mainframe-class virtual machines to achieve close to native performance and sets the technology apart from machine emulators that always impose an extra layer of terpretatuin on the emulated machine.

###### Virtualization for PC platforms

Popek and Goldberg showed that an architecture can support virtual machines only if all instructions that can inspect or modify privileged machine state
will trap when executed from any but the most privileged mode.

The Intel IA-32 processor cannot be virtualized.

VMware Workstation has a hosted architecture that allows it to co-exist with a pre-existing host operating system, and rely upon that operating system for device support.

![Figure 2: Represents VMware's hosted virtual machine model](vmware_hosted.png?raw=true "Figure 2: Represents VMware's hosted virtual machine model")

Figure 2: Represents VMware's hosted virtual machine model

