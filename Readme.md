## Docker cheetsheet:
### A. Get Snapshot from docker container:

If you want to get a snapshot from docker container you must do these steps:
1. First you must commit running container and create new image from it.

__command:__ ``` docker commit --message="your message" <container_name_or_id> <new_image_name>:<tag> ```

this will store an image from your container.

2. You can create new container from it with docker run command.

**command:** ```docker run --name <new_docker_container> -d <new_image_name>:<tag>```

you can set specific network to this command too.

---

### B. Go to docker container:

As you now docker containers like a small server with their os, so you can run command in there like terminal. you can use this command:

**command:** ``` docker exec -it <your_container_name> bash ```

This command allow you to have bash terminal in you container.
The -it flag is a combination of two option:
##### 1. -i (interactive): 
It means that you can interact with a container by a shell in it. you can use commands and inputs.

##### 2. -t (TTY):
This option allocates a pseudo-TTY (teletypewriter), which provides a terminal interface inside the container.
It enables features like command-line editing, colored output, and a proper shell prompt, making the session behave like a typical terminal.

---

### C. Clear all unused partitions:

You know the parts of an app that is available with docker. You have container, network, volumn and etc.
Sometimes you remove or make disable one of these parts because you dont need it, but other parts that has relation with it maybe available and use memory. So you can remove them but do you remember all parts?
So you can use this dangerous command. **docker system prune**

**command:** ``` docker system prune --all ```

This command remove all unuse containers, network, volumn and etc. You can make your disk free from unuse parts but be carefull this command remove all unuse part of you docker apps. All unuse volumns this mean you loss the data that store in volumns. this command remove stop containers too. for example you stop a container for some reasons then you run this command. You lost your stoped container. Sorry.

---

### D. See what you have:
You can see all part of your containers like container id, image, command, port, name, create date and etc.

**command:** ``` docker ps ```

you can see just your containers with this command :

**command:** ``` docker container ls ```

This command work for image and networks too.

* network:
``` docker network ls ```

* image:
``` docker image ls ```

* volume:
``` docker volume ls ```

