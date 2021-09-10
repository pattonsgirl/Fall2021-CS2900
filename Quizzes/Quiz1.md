# Quiz 1

1. What is the password to view Webex recordings (all of them)?
    - Cs2900-F21

2. What virtual machine manager / software is working on your host?
    - VirtualBox is the popular winner
    - Have some VMWare peeps and one running UTM

3. What is your host OS?
    - Windows is the majority
    - Couple Macs
    - Where my Linux hosts at?

4. What type of hypervisor is Hyper-V?
    - Type 1, which actually means interesting things for Windows 10 + WSL2
    - Type 1 hypervisors run on the hardware.  There is no "Host" persay - the hypervisor is the "Host"
    - For Windows 10, this means Hyper-V is directly interfacing with the hardware.  The devs designed it to work with Windows 10 as the "Host" so it can access things like the GPU via Hyper-V.  
    - WSL2 is more of the traditional "guest", with Hyper-V as the hypervisor managing its resources.

5. I would like to connect to a USB drive attached to my host from the guest VM.  What are some steps that need to happen? 
    - VirtualBox
    1. Install 'Guest Additions' extension.
        - Download guest additions
        - Attach it to your guest as a disk (before you power on guest)
        - Open the mounted disk in the guest
        - Run the appropriate installer
    2. Right click on your VM and select settings.
    3. Check the USB Drive you're interested in using. Save and exit.
    4. Launch your VM and under 'Devices' you should see your USB Drive under 'USB Devices'
    5. Your USB Drive from your host machine should show up on your VM like normal now.
    - These are the steps taken in UTM to connect a USB drive to a VM:
    1. On the VM that we want the drive we right click and select Edit
    2. Go to the sharing tab
    3. Put a check in the "USB 3.0 (XHCI) Support" box
    4. Select the maximum number of USB drives below that (default is 3)
    5. Click Save
    6. Start the VM and when the popup comes up from MacOS saying UTM wants to access the drive, click on Allow
    7. The drive is now accessible in the virtual machine
    - VMWare:
    1. Choose VM-Removable Devices
    2. To connect the USB to the vm - click the Vm's name
    3. If there was already a usb device in there, be sure to disconnect that to allow the new one to configure the settings.

6. T / F Type 1 hypervisors run on top of the host operating system.
    - False
    - Type 1 hypervisors run on the hardware.  There is no "Host" persay - the hypervisor is the "Host"
    - Type 2 hypervisors run on top of the host operating system
    - I "dropped" this question and gave everyone credit

7. T / F I can assign my virtual machine more resources than my host has (in terms of hardware).  It's all virtual!
    - False
    - I am limited to the disk, RAM, and CPU resources that my host has.  I cannot pull out more resources.
    - Now the catch here is we then went and played with networking, where I did "create" hardware that is not "on" my host.  So partial credit for those who marked "True"