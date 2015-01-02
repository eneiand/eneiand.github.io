#### Introduction and History
* Container History
  * Operating System-Level Virtualization
* Advantages
  * speed
  * soft memory
    * allocating, running an app in memory
  * crash manangement / resiliency because of speed
    * limit ddos, if one container is hit the other might not be
    * kill and restart
  * Security
* Docker, The Container Story
  * standardized container
* Docker Technology
  * Google Go
  * cgroup and namespace w/ Linux kernel
  * AUFS union filesystem
  * lxc underneath (Linux Containers)
#### Using Docker
* interactive shell
 *  'sudo docker -d &' to start docker service
 *  'sudo docker pull ubuntu' to fetch an image
 *  'sudo docker run -i -t ubuntu /bin/bash' to run image and present with shell prompt
 *  Ctrl+p Ctrl+q to disconnect
* Running docker
  * 'sudo docker ps' to list all running container instances 
  * 'sudo docker search ubuntu' to look for an image
  * 'sudo docker kill ' to kill a running instance
* Docker Repositories
  * index.docker.io
  * tagged images
  * docker can create, push, pull, search the repos. 
  * top level -> docker team, user repos not checked
#### Working Samples
  * Dockerfile contains description of how to build the docker image
  * 'sudo docker build -t adron/bearder-tribble .' build the image 
