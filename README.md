# Run Whonix without root

These helper scripts will run Whonix Gateway and Workstation without needing
root access, libvirt, or bridge support. It uses qemu user networking and a
socket to communicate between the Workstation VM and the Gateway VM.

Download the KVM release of Whonix from
[here](https://www.whonix.org/wiki/KVM#Download_and_Extract), verify the images
and extract them.

First start the gateway::

```run-gateway ./Whonix-Gateway-*qcow2```

By default it uses 256M and runs in text mode. You can change this by setting
MEM first. It also defaults to 2 CPUs, this can be changed by setting CPU when
running it::

```MEM=1024 CPU=1 run-gateway ./Whonix-Gateway-*qcow2```

Then run the Workstation, MEM and CPU also work here. It defaults to 2048M
of RAM and 2 CPUs.

```run-workstation ./Whonix-Workstation-*qcow2```

Communication between the VMs uses socket 7001 on localhost, and the traffic is
not encrypted, so anyone one the local system who manages to gain enough
privileges to monitor localhost could examine the traffic.
