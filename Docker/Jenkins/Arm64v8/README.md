# Jenkins (BlueOcean) with JRE 11 for Arm64v8

This project for the ARM based SBC board.
- Tested SBC
  - RaspberryPI4 with Ubuntu 20.04LTS
  - RockPI4 with Ubuntu 18.04LTS/20.04LTS

- Package information
  - OpenJDK JRE : v11
  - Jenkins : 2.249.1

- NOTICE
  - If you want to use another version of jenkins, you can change *JENKINS_VER* on *Dockerfile*
  - The compose file already mapped host's */data/jenkins* to container's */home/jenkins/data* directory to store Jenkins configuration data.
  - If you want to mapping host's directory to container's */home/jenkins/data* directory, host directory should have *GID:500*, *UID:500*

## Build and run

### Run using docker command
- Build image
```
# docker build . -t ${image_name}:${tag}
```
- Run container 
```
# docker run --name jenkins -d ${image_name}:${tag}
```
- Run container with host directory map
```
# docker run --name jenkins -e JENKINS_HOME=/home/jenkins/data -v /data/jenkins:/home/jenkins/data -d ${image_name}:${tag}
```

### Run using docker-compose command

- Build image
```
# docker-compose build
```
- Run container
```
# docker-compose up -d
```
- Build and Run
```
# docker-compose up --build -d
```

## Environment (docker-compose)

- Build image version tag
  - Image version tag is already defined on the *docker-compose.yml*. You can change it
- Volume mapping
  - The compose file already mapped Host's */data/jenkins* directory to container's */home/jenkins/data* directory.
  - If you don't want to mount it, please comment out the *volumes* section on *docker-compose.yml*

## Build image URL

- https://hub.docker.com/repository/docker/shieldguy/jenkins-blueocean-jre11-arm64/tags?page=1
