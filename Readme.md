## docker cheetsheet:
### A. Get Snapshot from docker container:

If you want to get a snapshot from docker container you must do these steps:
1. First you must commit running container and create new image from it.

__command:__ ``` docker commit --message="your message" <container_name_or_id> <new_image_name>:<tag> ```

this will store an image from your container.

2. You can create new container from it with docker run command.

command: docker run --name <new_docker_container> -d <new_image_name>:<tag>
you can set specific network to this command too.

### B. Go to docker container:

As you now docker containers like a small server with their os, so you can run command in there like terminal. you can use this command:
__command:__ ``` docker exec -it <your_container_name> bash ```

this command allow you to have bash terminal in you container.
the -it flag is a combination of two option:
##### 1. -i (interactive): 
it means that you can interact with a container by a shell in it. you can use commands and inputs.

##### 2. -t (TTY):
This option allocates a pseudo-TTY (teletypewriter), which provides a terminal interface inside the container. It enables features like command-line editing, colored output, and a proper shell prompt, making the session behave like a typical terminal.
