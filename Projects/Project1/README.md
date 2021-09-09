# Project 1

## Objectives

- Play with creating virtual machines
- Play with networking and virtual machines
- Create documentation in a GitHub classrooms repo

## Part 1 - Building VMs

- Pick one (or two) guest Operating Systems that are not the same as your host OS
- Write a guide on how to set up the Guest OS for you Host.  Include info such as
    - disk space reserved (and are you allowing it to expand) and why
    - memory / RAM allocation
    - whether or not you allow 3D acceleration
    - whether or not to include Guest Additions (in whatever form your VMM terms it) and what benifits it provides
        - also note which additions you utilize and how you configured them to work
        - Enabling full screen mode would count as a usage of Guest Additions ;)

## Part 2 - Exploring Virtualization

- Your disk is saved to a folder on your host OS.  
    - From your host, can you access the files and folders you create in the guest directory through this folder?  Why or why not?
- You can create snapshots / templates from a VM depending on your goal
    - templates would be for replicating / deploying a VM of the same configuration
    - snapshots would be for tracking changes over time - think backups.
    - Create one of each - a snapshot and a template, and analyze the disk space each takes up.  Make notes on what it actually stored when you choose these options.
- The hypervisor manages virtualized networking devices for your Guest to connect to the outside world
    - Determine the networking layout that facilitates this.
    - You can draw a diagram or take a series of snapshots to reference when discussing how this is setup

## Part 3 - Networking with style

- In class we discuss network configurations that are commonly deployed with virtual machines:
    - NAT networking
    - Host-only networking
    - Bridged networking
    - Internal networking (note this may only be supported by VirtualBox - have not tested al VMMs)
- NAT networking is the default configuration that is used with virtual machines managers like VirtualBox.
- Pick on of the other networking methods, and document how to configure it and prove that it is working as you say.

## Submission

1. Commit and push your changes to your repository.  Verify that these changes show in your course repository, https://github.com/WSU-kduncan/cs2900-YOURGITHUBNAME

2. In Pilot, paste the link to your project folder.  Sample link: https://github.com/WSU-kduncan/cs2900-YOURGITHUBUSERNAME/blob/main/Projects/Project1