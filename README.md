# Useful Commands

eval "$(docker-machine env default)"

docker ps -al

##### Save changes to existing container
docker commit <CONTAINER ID> <IMAGE_NAME>

docker rm -f <CONTAINER ID>

docker rmi -f <IMAGE ID>

docker build -t <REPOSITORY NAME>/<IMAGE NAME>:<TAG NAME> <DOCKERFILE PATH>

docker exec -it <CONTAINER ID> /bin/bash

##### IP of the docker host. This is needed to use port forwarding as localhost etc does not work
docker-machine ip default

docker run -it -p <HOST PORT>:<CONTAINER PORT> -v <HOST DIR>:<CONTAINER DIR> <CONTAINER ID>

docker-machine restart default

docker inspect <CONTAINER ID> | grep "\"IPAddress\"" | head -1 | awk '{print $2}'

docker run -it -p 8080:8080 -v /Users/Abhijit/Workspace/docker/tomcat:/var/log/tomcat8 <CONTAINER ID>

docker run -it -p 3306:3306 -v /Users/Abhijit/Workspace/docker/mqsql:/var/log/mysql <CONTAINER ID>

docker run -it -p 3306:3306 -e ROOT_PASSWORD=changeit <CONTAINER ID> bash

curl -v -T build/libs/hello-world-0.0.1-SNAPSHOT.war -u script:script "http://192.168.99.100:8080/manager/text/deploy?path=/hello&update=true"

# Useful References

[Developing Inside Docker Containers with OS X](pharnisc.github.io/2015/09/16/developing-inside-docker-containers-with-osx.html)

[Docker - Beginner's tutorial](https://blog.talpor.com/2015/01/docker-beginners-tutorial)

[Arun Gupta's Docker Images](https://github.com/arun-gupta/docker-images)
