### Host OS suppport for Type II VMMs

#### Bottlenecks:

1. UMLinux’s system structure with two separate host processes causes an inordinate number of context switches on the host.

2. Switching between the guest kernel and the guest user space generates a large number of memory protection operations.

3. Switching between two guest application processes generates a large number of memory mapping operations.

**These three bottlenecks are solved through simple changes to the host OS.**



![Figure 1: Guest Application Call system](guest_app_call_system.png?raw=true "Figure 1: Guest Application Call system")

**Figure 1: Guest Application Call system**

1. guest application issues system call; intercepted by VMM process via `ptrace`
2. VMM process changes system call to no-op (getpid)
3. `getpid` returns; intercepted by VMM process
4. VMM process sends `SIGUSR1` signal to guest `SIGUSR1` handler
5. guest SIGUSR1 handler calls `mmap` to allow access to guest kernel data; intercepted by VMM process
6. VMM process allows `mmap` to pass through
7. `mmap` returns to VMM process
8. VMM process returns to guest SIGUSR1 handler, which handles the guest application’s system call
