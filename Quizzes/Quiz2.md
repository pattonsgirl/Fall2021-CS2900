# Quiz 2
VM networking
Snapshots / clones / templates / OVF+OVA
VM security
VM's versus emulators versus simulators versus compatibilty layers versus containers
Kernel / systemd 
namespaces & cgroups

1. WSL1 and WINE use translate guest system call to host system calls.  In the case of WSL1, this meant linux system calls were translated to Windows system calls.  In the case of WINE, this meant Windows system calls were translated to Linux system calls.  What provides this translation?
    - compatibility layer
    - Emulators emulate hardware & software.  Android Development Studio emulates android devices (specialty hardware that phones use).  Video game system emulators emulate the hardware that ran the software designed for those systems.
    - cgroups deal with limiting process access to hardware resources of the machine

2. My host is connected to a private subnet (10.17.0.0/16).  My host has an IP address of 10.17.0.92  My guest has an IP address of 10.17.0.101  What networking mode is my guest using?
    - bridged
    - Partial credit: host-only.  You could argue that the private subnet may have been configured on the host
    - No credit: NAT networking.  In a NAT network configuration, the host cannot connect to the VM's IP either.  The host uses network address translation to allow the VM to communicate network traffic out and pass it back to the VM.  The VM would not get an IP address on the same subnet as the host

3. Containers perform virtualization at what level - hardware or kernel?
    - kernel

4. Virtual machines perform virtualization at what level - hardware or kernel?
    - hardware

5. Containers are going to be contained processes.  What makes it possible to control a container's access to resources - such as limiting the amount of RAM the containered process can use?
    - cgroups
    - systemd - cgroups are a feature of systemd
    - hypervisor manages hardware resources for virtual machines

6. T/F Snapshots create a "duplicate" of the VM.  The snapshot could be uploaded and downloaded to other systems and would contain a fully working version of the VM
    - False - snapshots are changes to the VMs in terms of files and hardware configuration.
    - clones / ovf/ova images would create duplicated of a VM

7. T/F Assuming both are accessible on the  network, the OS on a VM is as vulnerable as any OS on a host.
    - True