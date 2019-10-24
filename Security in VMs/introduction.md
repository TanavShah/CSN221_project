# Security issues and features in a VM

The VM is a *relatively* new project. So, it is quite understandable that it might have some security issues like every other system. As we know VMs are implemented using the hypervisor or VMM technology which acts as a layer between the virtual OS and the underlying hardware. Now, this provides a lot of security features such as **isolation, state recording, transience and mobility.**.
- **Isolation**: Isolation refers to the encapsulation of each guest OS and
abstraction from the hardware, so that each user accesses separate file systems and memory blocks. This means that a compromised VM won't affect the host OS.
- **State Recording**: The host OS has the ability to *record* the state of the VM. THis means that he can roll back the VM to a previous state of (ideally an uncompromised one) so that control is restored.
- **Transience**: The VMs haver the ability to be created and disabled at any point of time. Thus, the resource management of the underlying system is taken care of tby this aspect and DOS attacks(Denial Of Service) can be controlled.
- **Mobility**: The VMs created are in the form of an *image* or a file which can be shared between various systems as a single entity. Thus, they are very mobile in nature.
