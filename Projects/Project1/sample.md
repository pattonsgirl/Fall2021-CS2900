# Project 1

## Part 1 - Building VMs

- Guest VM used: Ubuntu Linux
- VMM (virtual machine manager / software): VirtualBox

### Setting up a Ubuntu VM on a Windows 10 host

- **NOTE** - think next semester, you'll take a class that needs familarity with virtual machines.  Give yourself the gift of good documentation

1. Downloaded ISO from [https://ubuntu.com/download/desktop](https://ubuntu.com/download/desktop)
    - Chose the Desktop ISO to have access to a GUI interface (instead of server where terminal only)
    - Choosing the Desktop edition also allows running of a web browser.  This VM could then be used to demo effects of networking settings by playing with web page access
2. Install VirtualBox for [Windows hosts](https://download.virtualbox.org/virtualbox/6.1.26/VirtualBox-6.1.26-145957-Win.exe)
3. Create a new Virtual Machine - basically, determine the RAM and disk space the virtual machine will be allocated
    - How much disk space?  Fixed or flex?
    - How much RAM?  What about your host?
    - 3D acceleration?  What performance do you need out of your VM?  Do you even have GPU resources to make this really worthwhile?
    - Guest Additions - what are you loosing without it, what would you gain with it, and do you want it?
4. Install an OS to the Virtual Machine
    - How to specify which ISO is the install ISO
    - Maybe (for your notes) any installation tips / tricks you did
        - Example: messing with partitions
    - How to detach install ISO once done
        - This step is needed sometimes.  I'll go with your judgement

## Part 2 - Exploring Virtualization

### Exploring Host Disk Usage
1. Describe where your Guest OS is saved and how much space it takes up
    - From your configuration above, is this going to expand?
2. Can you directly access your Guest files from the virtual machine image folder?  Why or why not?
3. Explore the sizes of creating "snapshots" vs. templates / clone.  What do each of these achieve?
    - Remember, only VMWare software can do templates.  It is a cool feature, but proprietary to VMWare

### Exploring Guest Networking

- **NOTE** - assume standard out of box networking configuration, that is to say NAT networking
    - If you find your "out of box experience" is different, note it and explore it
- Explain your approximate networking configuration for your Host - we talked about the home standard of:
    - modem from ISP, assigns public IP
    - router provides DHCP private network.  Devices are connected to your router, which is your gateway
    - your network requests to sites are routed through your router, which plugs in your public address, requests info from the world, gets the info back, then passes the request back to the device that made it (NAT - Network Address Translation)
- Explain the network configuration for your Guest
    - Does your guest have a network accessible address?  For example, can other devices connected to your router get to it?
        - The usual answer is no, so how is your Guest getting network access?

## Part 3 - Networking with Style

- Pick a networking method besides NAT, and see what it does.
- Document the networking configuration you choose.  
- In class, we explored bridged & host-only networking, and demonstrated the effects of each of these.
- If I were writing this up, I would likely use the example where I installed a web server and played with accessing it from the different IP configured on my host and guest

## Useful commands:

### Powershell:
- `ipconfig` - Displays settings for all available networking adapters

### Linux / bash:
- `ip a` - Displays settings for all available networking adapters