## Written Response

1. What is the difference between mounting a folder (bind mount or volume) and using the COPY instruction in a Dockerfile?

   - mounting creates a shared space where the container can make changes to files that will persistent on the volume or host folder
   - the COPY instruction copies the files / folders specified into the contianer - changes made will only persistent within the container.
   - Choice student answer:
     - Mounting a folder makes the folder available in the new directory with the folder still stored in the original place. It does not "Copy" anything, when that specific folder is unmounted it will no longer be able to be accessed. Using COPY, you can copy the folder from the host onto the new image which will become part of each new container that is created from that image.

2. What happens when an image is built?

   - containers are created with command level changes (like installing new packages)
   - each command level change adds a layer to the image
   - once all changes are made to the overlayed filesystem, the image is "committed" into one
   - Choice student answers:
     - Every time Docker encounters a RUN instruction in the Dockerfile, it fires a new container. The bundle for the container is formed by the base image plus all the changes made by preceding from the Dockerfile. When the RUN steps are executed completely, all the changes made to the container's filesystem become a new layer in the image being built and the process repeats starting from the next Dockerfile instruction.

3. Identify 2 types of namespaces and how they play into isolation of containers

   - network
   - PID
   - mount
   - user
   - cgroups
   - UTS
   - https://www.nginx.com/blog/what-are-namespaces-cgroups-how-do-they-work/

4. What does the following command do:
   docker run -dit --rm --name bubbles --mount type=bind,source=/foo,target=/bar -p 3030:56 busybox ./bar/program
   - Most beautiful student answer:

```
docker run creates a writeable container layer over an image and runs it.

-dit runs the container in detached mode (runs in background), interactive mode (keeps standard input open), and creates a pseudo terminal that the user can utilize with the container.

--rm deletes the container once you stop the container

--name names the container, "bubbles" is the name given to this specific container.

--mount mounts the container according to what the user specifies. The user in this question requested a bind mind mount binding the container from a directory from the /foo folder to a directory from the /bar folder.

-p publishes the container port's to the host. In this case it is publishing port 56 from the container to port 3030 of the host.

busybox is the base image that the container is running off of

./bar/program is the program that is being ran upon the startup of the container.
```

5. What benefit(s) does image tagging provide?

   - version control of images over time

6. [BONUS] I have a researcher whose project uses CUDA, a proprietary package owned by NVIDIA. CUDA can be a complicated install. The project also uses python 3 for some pieces. What image would you recommend they start with from DockerHub? Assume they will be creating a Dockerfile to make their own image, but need a recommendation for a base image to start from.
   - start with ubuntu 20, as it has most libraries that cuda would add, then add CUDA, may have python3 already
   - start with nvidia/cuda - https://hub.docker.com/r/nvidia/cuda
   - start with python
   - use a community image that has both - https://hub.docker.com/r/qts8n/cuda-python
     - NOTE: this would not be recommended for a stable environment - it is adding complexity to the software upgrade chain
   - start with busybox
     - This is my least favorite - as we explored, different bases are going to come with different starting points, so to speak. If you go with busybox, with are going to need to do some extra work to get all the libraries installed (lots of RUN commands)

## Short Answer

1. Dockerfile instruction to specify a base image:

   - FROM

2. Identify a container registry:

   - docker hub
   - quay.io
   - Azure
   - AWS / Amazon
   - Google
   - GitHub
   - and many more...

3. For an image, I need a command to execute once the image is run as a container. Which instruction should I utilize, CMD or RUN?

   - CMD
   - RUN instructions are used during the building of an image. Each RUN create a new image layer and spins up a container where the intructions are run, then "saved" as a new layer

4. One word for all three blanks: Containers share the host `____`, whereas Virtual Machines add a hypervisor over the host `____` and the VM itself has its own `____`
   - kernel
   - OS was also accepted (although would be a shaky answer in accuracy)

## True / False

1. Once a container is running, you cannot ask it to execute additional commands / perform additional actions.

   - False. You can use `exec` in docker, for example, to run additional commands / actions in a running container. Any actions would be persistent to the container, not to the image.

2. `docker images` shows the status of containers on the host system

   - False. `docker ps -a` shows the status of containers on the host system, including running, exited, etc.

3. Since images have no standard, images built for / with specific container engines can only be run with the same container engine. Simply worded, an image built in docker can only run using docker on other systems; systems using podman would be incompatible with the image.

   - False. Images have a standard per the OCI. An image built in docker can be used in another container engine. An example of this would be the ability to pull images from other container registries

4. Images need to be built. Once an image is built, it can be pushed / uploaded to a registry for sharing.

   - True. At some point every image was "built" to an instruction set and committed as an image

5. Container orchestration is the idea of automating the container management process via a set of commands to do health checks, deploy containers across systems, and update images.

   - True.

6. By picking a base image like ubuntu, the image will come pre-packaged with libraries specific to my application, like nodejs and python
   - False. Picking a "monolithic" base image does not mean it will come with all libraries / software pertaining to your application needs.
