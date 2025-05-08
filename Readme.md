## docker cheetsheet:
A.  Get Snapshot from docker container:
if you want to get a snapshot from docker container you must do these steps:
1. first you must commit running container and create new image from it.
command: docker commit --message="your message" <container_name_or_id> <new_image_name>:<tag>

