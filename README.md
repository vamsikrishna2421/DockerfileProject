# DockerfileProject
Dockerfile for routinely used containers

# This script is meant for quick & easy install via:
   $ curl -fsSL https://get.docker.com -o get-docker.sh
   $ sh get-docker.sh



#How to use Tomcatfile
1.Change filename from Tomcatfile to Dockerfile and be in same directory
2.TO create image from DOckerfile Runcommand:
$docker build -t tomcat:1.0 .
3.To create container from image  Run command:
$docker run -itd --name tomcat-container -p 8080:8080 tomcat:1.0
4.Go to browser and search <host-ip-address>:8080
