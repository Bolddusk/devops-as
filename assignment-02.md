# devops-as-2

Use the same github repo as used in Assignment1 or create another repo and type the answers/commands for following scenarios and merge them to main branch from a PR
- ## Explain Docker Containers vs VMs
- VM Provides complete isolation from host os whereas containers provides lightweight isolation from the host and other containers. Vm runs the complete OS including the kernel whereas Container runs the user mode portion of an OS and can be change to contain just needed services for you app. Vm runs any OS inside whereas Container  run on the same OS version as the host.  
- ## Explain Docker Architecture
- The Docker architecture uses a client-server model and comprises of the Docker Client, Docker Host, Network and Storage components, and the Docker Registry/Hub
- Docker Client : It enables users to interact with Docker. The Docker client can reside on the same host as the daemon or connect to a daemon on a remote host. A docker client can communicate with more than one daemon. The Docker client provides a command line interface (CLI) that allows you to issue build, run, and stop application commands to a Docker daemon.
- Docker Host : It provides a complete environment to execute and run applications. It comprises of the Docker daemon, Images, Containers, Networks, and Storage.
- Docker registries : Thery are services that provide locations from where you can store and download images. In other words, a Docker registry contains Docker repositories that host one or more Docker Images.
- ## Write command to create an nginx container in detached mode with name assignment-2 running on host port 9090 on a custom network named assignment-2
- docker container run -d --name assignment-2 -p 9090:80 nginx
- docker network create assignment-2
- docker network connect assignmnet-2 assignment-2 

- ## Write command to see logs of the above container
- docker container logs assignment-2
- ## Write commands to Exec into the container and cat the output of the default nginx file at /usr/share/nginx/html/index.html 
- docker exec -i -t assignment-2 /bin/bash
- cat /usr/share/nginx/html/index.html
- ## Exit the above container, and now recreate the container by Volume using bind mounting
- ## Command to exec into the above container and replace the default index.html to a custom one, which says that “I am becoming a Docker Expert” and it should be persisted for the next times.
- docker container run -v /home/osboxes/Desktop/devops/nginx/:/usr/share/nginx/html --name nginx-container -p 9090:80 nginx
