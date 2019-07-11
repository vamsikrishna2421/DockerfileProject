# DockerfileProject
Dockerfile for routinely used containers

# This script is meant for quick & easy install via:
   $ curl -fsSL https://get.docker.com -o get-docker.sh
   $ sh get-docker.sh

# About Dockerfile for server containers
As soon as CMD instructions are finished exection , container stops. We need to manually start the container.
So to solve this issue , a small command is included at the end which will run infinite time. 
$tail -f /dev/null

# How to use Dockerfile
For example , in case of Tomcatfile
1.Change filename from Tomcatfile to Dockerfile and be in same directory
2.TO create image from DOckerfile Runcommand:
$docker build -t tomcat:1.0 .
3.To create container from image  Run command:
$docker run -itd --name tomcat-container -p 8080:8080 tomcat:1.0
4.Go to browser and search <host-ip-address>:8080

# About Jenkins file
This Dockerfile is little tricky.
The fact is initialAdminPassword for jenkins is generated only after started the service for first time.
And takes few seconds for creation.
So we can see starting the service in RUN as well as CMD. Along with sleep 10 (10secs will be safe enough).
Issue: the java version from default-jdk package jdk8 is not compatible for some of jenkins plugins.
Need to use jdk-11 instead to support all plugins.
