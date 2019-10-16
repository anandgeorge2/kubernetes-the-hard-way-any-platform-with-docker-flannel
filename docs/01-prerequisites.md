# Prerequisites


## Machines and network requrements.


This tutorial uses 6 machines ( not including the load balancer and the client ) which can run Ubuntu 18.x.x. These machines should be routable to each other with no firewalls in between, although it is fine all these machines are behind a firewall. Another requirement we have for these machines is that they should connect to the Internet, as there will be binary downloads from GitHub and container images pulls from docker hub etc to these machines.

Below are the details of the machines which has been used to prepare this document. Please note below are not requirements but feel free to change as and what fits in your specific case.

hostname=controller1, ip address=10.0.0.32
hostname=controller2, ip address=10.0.0.22
hostname=controller3, ip address=10.0.0.29
hostname=worker1, ip address=10.0.0.25
hostname=worker2, ip address=10.0.0.30
hostname=worker3, ip address=10.0.0.27
hostname=LB1, ip address=10.0.0.26
hostname=client1, ip address=10.0.0.23

In this case above are VMs running in VirtualBox with a Bridge Network to the physical Router (TP-LINK 300Mbps Wireless Router). In the router settings, the DHCP has been configured to obtain static IP addresses.
Which means if the mac address of the Virtual NICs of above VMs remains the same their IP address too will be same which are obtained from DHCP server of the router. One way or the other you need a static IP address for the above VMs or you should not restart/re-DHCP ( action which can potentially change the IP if it not static) the VMs during this setup. The entire set up is running on a custom-built, Windows 10 bare metal box with 32 GB ram and 8 core CPU (AMD FX(tm)-8300 Eight-Core Processor) with virtualization enabled and with a 1 TB SSD. The ethernet port of the motherboard is physically connected to the wifi router with an Ethernet cable, and the router WAN port is connected to the NBN access point ( Source of Internet ).

All the VMs above are 1 VCPU and 1 GRAM with 60GB thin provisioned Virtual Disk.



## Running Commands in Parallel with tmux

[tmux](https://github.com/tmux/tmux/wiki) can be used to run commands on multiple compute instances at the same time. Labs in this tutorial may require running the same commands across multiple compute instances, in those cases consider using tmux and splitting a window into multiple panes with synchronize-panes enabled to speed up the provisioning process.

> The use of tmux is optional and not required to complete this tutorial.

![tmux screenshot](images/tmux-screenshot.png)

> Enable synchronize-panes by pressing `ctrl+b` followed by `shift+:`. Next type `set synchronize-panes on` at the prompt. To disable synchronization: `set synchronize-panes off`.

Next: [Installing the Client Tools](02-client-tools.md)
