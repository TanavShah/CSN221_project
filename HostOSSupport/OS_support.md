### Host OS suppport for Type II VMMs

#### Bottlenecks:

1. UMLinux’s system structure with two separate host processes causes an inordinate number of context switches on the host.

2. Switching between the guest kernel and the guest user space generates a large number of memory protection operations.

3. Switching between two guest application processes generates a large number of memory mapping operations.

**These three bottlenecks are solved through simple changes to the host OS.**

![Figure 1: Guest Application Call system](guest_app_call_system.png?raw=true "Figure 1: Guest Application Call system")
