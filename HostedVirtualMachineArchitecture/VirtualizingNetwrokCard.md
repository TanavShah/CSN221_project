# Virtualizing a Network Card

An excellent example of a device that requires both high sustained throughput and low latency is a network interface card (NIC). 

![](virtualizing_network_card.png?raw=true )



VMware’s network subsystem provides virtual Ethernet adapters, hubs and bridges. A hub can be either be bridged to a physical Ethernet adapter, or connected to a virtual network interface in the host OS. The virtual bridge and hub are implemented via a VMNet driver that is loaded into the host OS.

The NIC emulation can be connected to the host in two ways– it can be bridged to the same physical network as a physical NIC or it can be connected to a virtual network created on the host. In both cases, the connection is implemented by a VMware VMNet driver that is loaded in the host operating system. A virtual NIC that is bridged to a physical NIC is a true Ethernet bridge in the strictest sense. Its packets are sent on the wire with its own unique MAC address. The VMNet driver runs the bridged physical NIC in promiscuous mode so that replies to that MAC address are picked up. The virtual NIC appears on the local Ethernet segment indistinguishably from any real machine. As a result, a virtual machine with a bridged virtual NIC can fully participate in accessing and providing network services.

A virtual NIC that is connected to a virtual network does not require an Ethernet interface on the host. Unlike the bridged case, the virtual network is completely private within the host and any participating virtual machines. If desired, the host OS can perform routing or IP masquerading to connect a virtual network to any type of external network, even to a non-Ethernet network. 
