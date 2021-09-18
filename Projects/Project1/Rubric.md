# Project 1 Rubric

 / 10

## Part 1 - Building VMs ( / 4)

1. Create a new Virtual Machine ( / 2)
    - How much disk space?  Fixed or flex?
    - How much RAM?  What about your host?
    - 3D acceleration?  What performance do you need out of your VM?  Do you even have GPU resources to make this really worthwhile?
    - Guest Additions - what are you loosing without it, what would you gain with it, and do you want it?
2. Install an OS to the Virtual Machine ( / 2)
    - How to specify which ISO is the install ISO
    - Maybe (for your notes) any installation tips / tricks you did
        - Example: messing with partitions
    - How to detach install ISO once done

## Part 2 - Exploring Virtualization (  / 4 )

### Exploring Host Disk Usage (  / 2)
1. Describe where your Guest OS is saved and how much space it takes up
    - From your configuration above, is this going to expand?
2. Can you directly access your Guest files from the virtual machine image folder?  Why or why not?
3. Explore the sizes of creating "snapshots" vs. templates / clone.  What do each of these achieve?
    - Remember, only VMWare software can do templates.  It is a cool feature, but proprietary to VMWare

### Exploring Guest Networking (  / 2)

- Understanding of Host networking situation
- Understanding of Guest networking situation

## Part 3 - Networking with Style (  / 2)

- Pick a networking method besides NAT, and see what it does.
- Document the networking configuration you choose.
