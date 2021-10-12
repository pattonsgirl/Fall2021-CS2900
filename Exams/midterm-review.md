# Virtual Machines

- Virtualization at hardware level
- Virtual machine managers
    - VirtualBox
    - VMWare
    - Hyper-V
    - UTM
    - Parallels
- Hypervisor
    - type 1
    - type 2
- Host
    - What does the host hardware mean for the guest?
    - CPU virtualization
- Guest
    - What hardware settings can be configured
    - Guest addition capabilities (VirtualBox specific term)
- VM Networking
    - NAT
    - Host-only
    - Bridged
        - https://docs.oracle.com/en/virtualization/virtualbox/6.0/user/network_bridged.html
        - https://www.vmware.com/support/ws4/doc/network_bridged_ws.html 
- VM saving / backups / portability
    - snapshots
    - templates (VMWare specific term)
    - clones
    - why disk type may matter
    - OVF + OVA
- VM security / vulnerabilities
    - assuming network access to world from VM, as vulnerable as any other OS
    - apply updates (hypervisor & OS)
- Investigating the cloud (AWS) as a virtual machine creator / host

# Other things that are not Virtual Machines or Containers

- Emulators
- Simulators
- Compatibility layers

# Containers

- Virtualization at kernel level
- systemd / kernel features for containers
    - chroot
    - namespaces (specifically, PID namespaces)
    - cgroups
    - User namespaces (something we might not touch, but don't refer incorrectly ;) )
- OCI - Open Container Initiative - committee that makes rules about what is and is not a standard container
    - hint: its all about isolation
- Container engines
    - Docker
    - containerd
    - LXC
    - Singularity
    - podman
- Container images
    - registries (Docker Hub has been a focus)
    - `pull`ing and viewing downloaded images
- Running containers
    - executing commands inside
    - applied exploration of container isolation via chroot, namespace, cgroups
- Container filesystems
    - overlayfs
    - image layer (lower)
    - modified upper layers (upper) once container runs
- Container portability
    - save / load - dealing with image layers
    - export / import - dealing with the merged overlay filesystem


# Ignore these notes for studying

Future notes:
 - cloud can also be used to run containers
