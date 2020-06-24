# Deploy Continuous Integration Pipeline with Jenkins-Docker

To play out the DevSecOps pipeline using Docker/Jenkins.

The experimental pipeline is as such:

Step 1: Github public repository
- Fresh python codes are uploaded into the public repository. 
- Jenkins will pull and build when new codes are uploaded.

Step 2: Docker/Jenkins Server
- A Jenkins running in a Docker container will receive the new codes.
- Pipeline will be initiated by Jenkins.

Step 3: Docker/Jenkins spawn a sonarqube container
- The sonarqube will conduct a SAST on the Repo Content.

Step 4: Docker/Jenkins spawn a python container 
- This container will be used to execute python codes inside.


# Progress
- Complete setting up a Docker/Jenkins that is able to establish connection to Docker Daemon on host.

# SAST Tools
- Sonarqube
