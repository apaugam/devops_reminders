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

List all containers running : 
```
docker ps
```

Inspect specific container configuration : 
```
docker inspect CONTAINER_NAME / CONTAINER_ID
```

Display container stderr | stdout  : 
```
docker logs <container name|id>
```

Copy data into a container : 
```
docker cp <data> <container name| id>:<PATH>
```

Export container to .tar archive : 
```
docker export <container name|id> > <filename>.tar
```

Import container from a .tar archive : 
```
docker import <filename>.tar
```



* * *
## Dockerfile
Build from an existing image :
```
FROM <image>:<tag>
```

Copy the PATH files to a specified container PATH :
```
COPY <PATH> <container PATH>
```

Run a specific command when building the image (can have many) :
```
RUN <cmd>
```

Run a specific command when container starts (can have only one) :
```
CMD [“”,””]
```

Specify a working directory (should be already created) :
```
WORKDIR
```

Expose a specified port to be accessed :
```
EXPOSE <port>
```

Force to rebuild and not using the cache :
```
ONBUILD COPY | RUN |
```

Add labels to images (commonly reverse DNS)
```
LABEL <label>=<value>
```
