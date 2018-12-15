These helper scripts will run Whonix gateway and workstation without needing
root access, libvirt, or bridge support. It uses qemu user networking, and a
socket to communicate between the Workstation VM and the Gateway VM.

First start the gateway::

```run-gateway ./Whonix-Gateway-*qcow2```

By default it uses 256M and runs in text mode. You can change this by setting
MEM first. It also defaults to 2 CPUs, this can be changed by setting CPU when
running it::

```MEM=1024 CPU=1 run-gateway ./Whonix-Gateway-*qcow2```

Then run the Workstation, MEM and CPU also work here. It defaults to 2048M
of RAM and 2 CPUs.

```run-workstation ./Whonix-Workstation-*qcow2```

