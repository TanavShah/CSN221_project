In today's world, virtualization is not only limited to home computers and data centers but is also spreading to *embeded* systems. Currently, majority of the ARM processors support **Para virtualization**(which is the modification of an OS before it is installed on the virtual machine) rather than a **Trap-and-Emulate virtualization**(in which hypervisor traps all of guest os instructions and executes them making the guest OS think it is running in privileged mode) As we know, the dominant processor used in the embeded systems are the **ARM** processors. **ARM** has started launching virtualization extensions for their architecture.

# Introduction and Overview

- ARM is a 32 bit RISC based processor having 16 general purpose registers.
- The architecture has 6 *privileged kernel*(for handling of different kinds of interrupts) modes and 1 *non-privileged user mode*. The architecture also has a *secure mode* in which the underlying hardware of the system becomes accessible. 
![Virtual support for ARM](ARM\_virtualization.png?raw=true)

# Entensions for Virtualization

The new extensions for ARM architecture are quite similar to the x86 one. Addition of a new processor mode *hyp mode* ha been done. It can only be entered throught the kernel mode and has banked registers as well as hypervisor-only registers. The hypervisor mode, when interpreting an instructio, also has a VMID(Virtual Machine Identifier) bit attached which tells it which VM the request is coming from. Also, the hypervisor mode has it's own Pointer Tables for interpretation of hypervisor's virtual and guest's physical addresses. 

- **Configurable Traps** - Many exceptions can be configured to trap either into hypervisor or guest kernel. Interrupt traps are configures such that either all interrupts are handled by hypervisor or all by guest OS.

- **Emulation Support** - MOst of the instructions which are high privileged are trapped by the hypervisor and emulated. e.g load and store instruction which include device registers.

- **Second-stage Emulation** - ARM now supports two-staged address translation, from *guest virtual* to *guest physical*, then from *guest physical* to *physical*. 

- **Virtual Interrupts** - In order to avoid emulation interrupt controller, ARN introduced to new hardware component *virtual CPU*(VCPU). This is mapped into the guest as *GIC CPU* interface and can allow guest to clear interrupts without going into the hypervisor mode.
