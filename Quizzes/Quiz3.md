# Quiz 3

1. Write the commands to pull and then run a base image from Docker Hub named "alpine"
Note: docker commands are expected, but proof that you are playing with other container engines is a-okay
    - `docker pull alpine`
    - `docker run alpine`
        - notes: if alpine doesn't have a process that spins up on start, this will run the container, but then terminate it because it doesn't have anything to do.  Using -it or sending it a command like `sh` or `sleep long_time` will create an ongoing process

2. Hopefully as you have been tinkering with containers, you've been thinking about something you want to do with containers.  Write a project idea you would like to see here.  

For grading purposes, there is no right or wrong answer.  We can discuss in class how to containerize these ideas.
    - containerize a python project
    - containerize an emulator
    - containerize Minecraft 
        - pull "add to your inventory" certain images "items/tools/food etc." which would affect the way you "play the game"
    - how the environments can become standard for development for QA and production teams
    - solving dependency conflicts
    - networking simulation
        - Containers are less secure than VMs so I wouldn't utilize it for malware analysis. I was thinking you could use it as a testing grounds for a network architecture. You could possibly set up a bunch of container since they are lightweight, and create and simulate what a basic Zero Trust network is. You could use this to show beginner's and potential skeptics on everything a Zero Trust architecture implies and entails.  
    - interconnected containers
    - website
    - I am currently in team projects 1 this semester and we have to build an autonomous robot that is capable of doing things. Our idea is to essentially replace the guide dog with a robot that can detect objects and go around them while communicating with the user through their phone. Maybe we could use containers to isolate each function the robot has to do and then bring them together?
    - redundancy / resilency with containers
    - security vulnerabilities / network / malware analysis
    - We have containerized Valhiem and triggered it to run (use cloud resources) only when people are playing

3. I run a container and open a shell to it.  In the container shell, I try to run a program that in installed on my host (firefox or git), but my container says command not found.  Why can't my container use programs installed on my host?
    - the container is in a jailed directory - this uses a kernel / systemd function called chroot.  When we use chroot, the process runs in a directory that is isolated from system folders and directories - this includes programs - programs are installed to directories (folders) and therefore need to exist uniquely in folder accessible by or interal to the container.

4. What feature of systemd creates process id isolation within containers?
Extra hint: Because of this feature, containers will think of themselves as having PID 1, while in truth the host has a process id assigned to it.
    - namespaces / namespace / PID namespace
    - PIDs will always exist for any process on the system - having a process ID is not unique to a container.  To the system, the container is a process and has a process ID.  Within the container, the container cannot see other processes on the system - it will refer to itself as having PID 1 and (within the container) uniquely assign PID to its child processes (which again would have a system PID)
    - User namespace would be more like accounts on a system.  If we both have accounts on a system, and I log in on my account, I stick with the things I have permission to do and see.  Same for you - if you log in, you stick to the things you have permission to do.
    - We haven't zoomed in on how this works in containers just yet, but the essence is this.  With containers, our aim is for isolation.  Processes have associated users (including root, and account holders or a system).  If a container runs a process with root, should they also get root on the system?  The troubling fact we will find is that with current configuration, they do.  Now containers could run their internal processes as other user ids that don't tie back to system ids.  This will be what we will aim to do to continue adding to our secure containering discussion.

5. A ____ is a set of files that define the resource limits (if any) of a process.  Processes can be assigned to ____ in order for those processes to be limited in the amount of system resources they can consume.
    - cgroup / control group 
    - I'll specify next time that only one word was needed to fill in multiple blanks ;)

6. A virtual machine (IP 10.0.0.24) and host (IP 10.0.0.20) exist on the same subnet (10.0.0.0/24), but the guest cannot communicate with other machines outside of this network (only with the host).  What type of virtual networking is enabled?
    - host-only
    - in the given scenario, the host and guest can talk within a subnet, but not other machines outside that subnet.
    - in bridged networking (there are a few ways this is configured, we'll discuss), in essence, you are connecting to the same network as your host.  This means your VM could communicate with machines on your network or outside the network, per how the network is configured.
    - NAT'ed networking would not put the machines on the same subnet to communicate.  In NAT'ed networking, the host would  be a communications pass through.  No devices would be able to connect to the VM by IP.

7. T/F By definition from the Open Container Initiative, a virtual machine counts as a standard container.