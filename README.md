#TryDocker

#Created the directory called html and placed index.html to display a webpage

#Ran the below command from terminal to start the web server using nginx

`docker run -v /Users/s0e02l3/git/TryDocker/html:/usr/share/nginx/html:ro -p 8080:80 -d nginx`

#To list the process running on docker
`docker ps -a`

#To list the docker images
`docker images`

#To stop a docker container
`docker stop <container_name>`

#To remove the container from docker
`docker rm <container_name>`

#To run a new docker container instance
`docker run -it ubuntu bash`

#This downloads from DockerHub
`docker run hello-world`

#To look into the container process
`docker top <container_name>`

#To start the docker container running already 
`docker start --attach <container_name>`

#To create docker image, follow below. 
1. Create the Dockerfile, on what to do. 
2. Sample file available in repo

#To create the docker image
`docker build -t testnginx .  `

`[+] Building 0.3s (7/7) FINISHED                                                                                                                                                                                                              
 => [internal] load build definition from Dockerfile                                                                                                                                                                                     0.0s
 => => transferring dockerfile: 85B                                                                                                                                                                                                      0.0s
 => [internal] load .dockerignore                                                                                                                                                                                                        0.0s
 => => transferring context: 2B                                                                                                                                                                                                          0.0s
 => [internal] load metadata for docker.io/library/nginx:latest                                                                                                                                                                          0.0s
 => [internal] load build context                                                                                                                                                                                                        0.1s
 => => transferring context: 167B                                                                                                                                                                                                        0.0s
 => [1/2] FROM docker.io/library/nginx                                                                                                                                                                                                   0.1s
 => => resolve docker.io/library/nginx:latest                                                                                                                                                                                            0.0s
 => [2/2] COPY html /usr/share/nginx/html                                                                                                                                                                                                0.0s
 => exporting to image                                                                                                                                                                                                                   0.0s
 => => exporting layers                                                                                                                                                                                                                  0.0s
 => => writing image sha256:50a1e93b75b497dfbf7ed6cc26b08aa545258e75628d307c0370b0e0fad8b8cc                                                                                                                                             0.0s
 => => naming to docker.io/library/testnginx   `

#How to start containers for the created Docker Image
`docker run --name foo -d -p 8080:80 testnginx`

#Refer to Example2 folder for another complicated example on another web server creation using python
`docker run --name webapp -p 8080:4000 mypyweb`

#How to Pass environment variable
`docker run --name webapp -p 8080:4000 -e NAME="Sara" -d mypyweb`

#How to add the image to Docker Hub
`docker tag mypyweb saravannann/sara_repo:1.00`

#Push Docker image to DockerHub
`docker push saravannann/sara_repo:1.00`

#Stop all running containers
`docker stop $(docker ps -a -q)`

#Delete all existing images
`docker image rm $(docker images -a -q)`

#Delete specific image
`docker image rm [image name]`

#Delete all containers
`docker rm $(docker ps -a -q)`

#Display Logs of Container
`docker logs [container name]`

###########################
#Docker-Compose

#Build Docker-Compose

`docker-compose build`

#Run Docker-Compose

`docker-compose up`


#Bring down Docker-Compose
`docker-compose down`

#Logs for particular Service
`docker-compose logs -f [service name]`

#list the containers
`docker-compose ps`

#Executes command in running container
`docker-compose exec [service name][command]`

