# Mount

`Volume`: mechanism for persisting data generated by and used by Docker container. managed by docker. [link](https://docs.docker.com/storage/volumes/)

`Bind mount`: file or directory on the host machine is mounted into a container. reference by its absolute path. dependent on the directory structure and OS. [link](https://docs.docker.com/storage/bind-mounts/)



# Dev environmet

docker run -dit -p 5000:5000 --restart unless-stopped -v $(DEV_PATH):$(CONTAINER_APP_PATH) --name $(CONTAINER_NAME) $(SERVICE_NAME)
