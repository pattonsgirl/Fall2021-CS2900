# Quiz 5

1. T/F By utilizing namespace isolation, processes running in containers can use UIDs (usernames) that do not exist on the host

   - True

2. T/F By default, containers utilize the host's network stack - there is no isolation / abstraction of networking.

   - False

3. From the following docker run command, identify the container's port
   docker run -dit --rm -p 4141:8080 myapp:3.1

   - 8080

4. From the following docker run command, identify the host's port
   docker run -dit --rm -p 4141:8080 myapp:3.1

   - 4141

5. T/F Much like VMs, since containers are isolated we don't need to worry about patching or updating software for vulnerabilities.
   - False
