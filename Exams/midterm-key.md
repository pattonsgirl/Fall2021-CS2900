## Written Response

1. What does it mean to have a virtual machine using NAT networking?  Describe how NAT plays into the networking scenario.
    - The virtual machine will act as if it is on another private subnet and your host machine can be thought of as a router. NAT (Network address translation) happens twice. When your real router processes traffic to your host machine and/or other devices, and when your host machine processes traffic to your virtual machine. All traffic will still show up to outsiders/The Internet as coming from your public ip address.

2. I need the ability to clone virtual machines, but change some settings of the clone before deploying (such as network settings).  Which virtual machine manager has a feature that will provide this capability?
    - VMWare
    - VMWare has templates, which differ from clones in that 1. they can be used to create VM's from, but are their own thing and 2. will let me configure some settings of the incoming VM
    - VirtualBox: the maximum that could be configured was whether or not to keep the MAC address from the original VM.  It does not allow configuration.
        - TODO: score for answer of VirtualBox
    - Hyper-V: you know, its more work, but I'll give it to you - https://www.altaro.com/hyper-v/templating-virtual-machines-with-hyper-v-manager/

3. Explain what the following command does (including what the extra options do): `docker run -dit --rm --name jerry ubuntu`
    - `docker run` - run a specified image
    - image is `ubuntu`
    - `--name` used to name the container jerry (instead of a random name from docker)
    - `--rm` removes the container once it is done
    - `dit` - detached, open STDIN, allocate a psuedo-tty
    - --rm = Sets rm to true, which removes the container when you exit, making it a temporary use container. (According to manpages.org this command is incompatible with -d.) - Thank you Dylan

4. A Windows 10 vulnerability has just been noticed.  Are guest virtual machines running Windows 10 also vulnerable?
    - An operating system just runs on hardware (even virtual hardware).  Isolation (in this case via the hypervisor) keeps the host and the guest separate, but the OS on either is just a piece of software. Regardless of where an OS is running, it needs to be updated, patched, and monitored for suspicious activity.  The only thing that could keep the VM from getting a virus is for it to be fully isolated, including networking isolation (and perhaps an ability to do updates).  Any vulnerability found for that OS would still be a vulnerability for the guest, just not one that could be exploited as it didn't have networking connectivity
    - In short, yes. Your VMs are just as vulnerable as your host but not the other way around. You can have a piece of malware on your VM that is safe and isolated from your host (most of the time). But your host can access your VMs, so a piece of malware on your host can find its way onto your VMs. Most malware likely won't be this sophisticated, but there are definitely pieces of malware out there that can cause damage all the way from your host to your VM.


5. (2 pts) Select from host-only or bridged - Describe the networking situation and accessibility for, between, and surrounding the host and guest.
    - Host-only networking: If you have a virtual machine and a host (where the VM and the host have different IPs) and they are on the same subnet, the guest can only communicate with the host and no other machines outside of the isolated network.
    - Bridged: The guest machine is assigned an IP in the same subnet as your host and other devices on the network, and all devices on this subnet can communicate back and forth with the guest. In bridged mode, the guest machine appears to be no different from another device on your network.

6. What do cgroups define?
    - cgroups define which resources and how much of each resource is able to be used by a process or group of processes

7. (2 pts) How do containers use the overlay filesystem?
    - Containers run on images - images are the lower layer.  When the container is running, an upper layer is created.  We interact with a merged version of this lower and upper layers.  Changes made in the container have no effect on the lower layer (image)

8. How does jailing / using chroot protect files / folders between the host and container?
    - chroot changes the **apparent** root directory. This means that a container will think it is in the root directory even when it is not. Anything "higher" (outside the directory tree) than the container's apparent root directory will be shielded (probably) from the container's operations.


## Short Answer / Fill in the Blank

1. Which type of hypervisor is installed on bare metal?
    - type 1

2. If you need to be able to roll back small changes within a VM, what is more efficient - snapshots or clones?
    - snapshots

3. Container ____ hold container images.  Images can be 'pull'ed or 'push'ed to these.
    - registries
    - registry vs. repository - registries can be used to push and pull containers and can keep track of tagged versions of containers.  A repository is a different thing that will be clearer once we talk building our own.  A container repository would be the build file for the container image and and associated files that might get updated over time.

4. Once you have created a virtual machine, you can select an ____ file, which is an installation image that contains installation configuration and installs the operating system to the virtual disk
    - iso

## True / False

1. Nintendo 64 games can be played inside a virtual machine.

2. Containers and virtual machines both have isolation in common.

3. Virtual disks can be set to expand if out of space.

4. I have created a many interconnected virtual machines on a single host.  While creating individual clones is feasible, it would be better to create an OVA that includes the OVF of the interconnected machines.

5. Containers perform virtualization at the hardware level
    - False