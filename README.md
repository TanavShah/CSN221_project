# The technology of Virtual Machine Monitors and Architectural support for VM Operating Systems

### Instructions to collaborate on this repository

* Add work related to papers in branch `papers/{your_name}`
* All the work related to one heading should be put in a folder of name same as that of heading.
* A markdown file for the content in folder.
* After you have complete a part submit pull request to master

_Please refer to `papers/amish` for an example regarding above part_

* Add work related to implementation in branch `implementation`

### Abstract

A virtual-machine monitor (VMM) enables creation. management and governance of Virtual Machines on top of a physical host machine. VMM manages the backend operation of VMs by allocating the nescessary computing, memory, storage and other I/O resorces. A few simple extensions to a host operating system can make it a mush faster platform for running a VMM.
This project deals with the architectural support for  **virtualization** running over a **host OS**. Virtualization today is mainly handled by hypervisor technology. Here we look at how the architecture of a system can support the *security of a virtual machine*, *memory isloation* for the VM and *hybrid virtualization* of the VMs.
