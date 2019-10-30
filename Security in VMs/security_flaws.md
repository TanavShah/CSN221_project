# Security Challenges in VM

The Virtual Machine has it's advantages in hardware maintainnce, OS mobility and transience etc, but in order to implement this feature, sometimes security issues are raised in the VM infrastructure.

These are:
- **VM Sprawl**: The biggest vulnerability of VMs is due to the ease in creation of new Virtual Machines, which makes the monitoring of VMs veryproblematic. Since host OS and VM OS might be different. This means that each security path needs to be manually updated to each VM for the system to be secure, this needs to be done regularly or an obsolete VM might become the entry point for an attacker.

- **State Restore**: One of the key features of VM is it's ability to periodically store the state of current VM as a file and restore it to a previous state if needed. This can also become a serious security flaw if an attacker can restore the state of a Virtual Machine to a previous unsecured one(one in which a certain security patch wasn't applied). Or if a VM was once infected with virus which was removed. If the attacker then restores the VM to an earlier state of virus infection, the system becomes quite vulnerable.

