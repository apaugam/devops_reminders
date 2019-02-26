# Docker Cheat Sheet
Author : Aël PAUGAM
Contact : ael.paugam@gmail.com
GitHub : github.com/apaugam
_ _ _


## Index
1. Assumptions
2. Docker
	1. Docker basics
	2. Installation
	3. Docker running
3. Dockerfile

* * *
## Assumptions
Syntax of the document...

* * *
## Docker
1. Docker basics
2. Installation
3. Docker running

###### List all containers running
```
docker ps
```

###### Inspect specific container configuration
```
docker inspect <CONTAINER_NAME|ID>
```

###### Display container stderr | stdout
```
docker logs <CONTAINER_NAME|ID>
```

###### Copy data into a container
```
docker cp <PATH> <CONTAINER_NAME|ID>:<CONTAINER_PATH>
```

###### Export container to .tar archive
```
docker export <CONTAINER_NAME|ID> > <FILENAME>.tar
```

###### Import container from a .tar archive
```
docker import <FILENAME>.tar
```

* * *
## Dockerfile
###### Build from an existing image
```
FROM <IMAGE>:<TAG>
```
Will be pulled from the dockerhub or specified repository if not already downloaded. Examples : nginx, alpine, ubuntu, debian, centos

###### Copy the PATH files to a specified container PATH
```
COPY <PATH> <CONTAINER_PATH>
```
Usually copying the app true path.

###### Run a specific command when building the image (can have many)
```
RUN <CMD>
```

###### Run a specific command when container starts (can have only one)
```
CMD [“”,””]
```

###### Specify a working directory (should be already created)
```
WORKDIR <CONTAINER_PATH>
```

###### Expose a specified port to be accessed
```
EXPOSE <PORT_NB>
```

###### Force to rebuild and not using the cache
```
ONBUILD COPY | RUN |
```

###### Add labels to images (commonly reverse DNS)
```
LABEL <LABEL>=<VALUE>
```
