# Jenkins (BlueOcean) with JRE 11 for Arm64v8

These build file tested with Ubuntu 18.04/20.04 on Raspberry PI4 / Rock PI 4 

- Included package
  - OpenJDK JRE : v11
  - Jenkins : 2.249.1

- NOTICE
  - This build image required host's /data/jenkins directory to store configuration data of Jenkins.

# Build and run

- Build image
```
# docker-compose build
```
- Run container
```
# docker-compose up
```
- Build and Run
```
# docker-compose up --build
```

# Environment

- Change Jenkins version
  - Change "JENKINS_VER" on Dockerfile
  - Change image tag on docker-compose.yml
- Volume mapping
  - Host's /data/jenkins directory to /home/jenkins directory of container.
