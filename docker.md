Install Docker on Ubuntu
`https://docs.docker.com/engine/install/ubuntu/`

Create an ubuntu docker container  
`docker pull ubuntu`

Build image from dockerfile with name  
`docker build . -f DOCKERFILE -t NAME `

Build image from specific file  
`docker build -t CONTAINERIMAGENAME - < DOCKERBUILDFILE`

Run and name a container in background  
`docker run -idt --name CONTAINERNAME CONTAINERIMAGENAME`

Run container with network using hosts's network  
`docker run -idt --network host --name CONTAINERNAME CONTAINERIMAGENAME`

Enter container as root in bash shell  
`docker exec -it CONTAINERNAME bash`

Install sudo  
`docker exec -it  --user root ubuntu apt-get install -y sudo`

Run docker container Ubuntu as user 'nobody'  
`docker run --name ubuntu --user nobody -id ubuntu`

Get back into container as user 'nobody'
`docker exec -it --user nobody ubuntu /bin/bash`

Execute commands as root  
`docker exec -it  --user root ubuntu apt-get -y update`

Install sudo  
`docker exec -it  --user root ubuntu apt-get install -y sudo`

Push image to dockerhub  
Log in to dockerhub  
`docker login`

Check images  
`docker images`

Tag image  
`docker tag IMAGEID YOURDOCKERHUBUSERNAME/YOURREPOSITORYID:TAG`

Push image to dockerhub  
`docker push YOURDOCKERHUBUSERNAME/YOURREPOSITORYID`

Build a container that runs in background
```
apiVersion: v1
kind: Pod
metadata:
  name: ubuntu
spec:
  containers:
  - name: ubuntu
    image: ubuntu:latest
    # Just spin & wait forever
    command: [ "/bin/bash", "-c", "--" ]
    args: [ "while true; do sleep 30; done;" ]
```
