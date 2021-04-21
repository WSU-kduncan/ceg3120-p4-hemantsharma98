# Project 4 

## Project Overview:
Docker is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers.

AWS stands for Amazon Web Services. It is a subsidiary of Amazon providing on-demand cloud computing platforms and APIs to individuals, companies, and governments, on a metered pay-as-you-go basis.

In this Project, I used docker to create image and store it into a container. Moreover, with the help of AWS ECR(Elastic Container Registry) which is a service of AWS I managed to store and deploy that container image.

## Run Project Locally:
### How to install a docker:
1)Create a account at https://www.docker.com/.

2)Download Docker Desktop from https://www.docker.com/products/docker-desktop (Windows,MAC,Linux) choose your OS.

3)For Windows double-click on the Docker Desktop Installer.exe to run the installer.

4)Follow the instructions and wait till the process is done.

5)After it click close and restart.

6)Open cmd and execute the commmand "docker --version" to check the version of the docker you have installed.

You can also see the docker icon on the right hand side of the taskbar. If it's running then there is no problem just login into your account. 

### How to build the container:
1)Create a file named Dockerfile.

2)Add instuctions in a Dockerfile.

3)Build Dockerfile to create a image with the command "docker build [OPTIONS] PATH | URL | -". I had used the command "docker build -t hemantimage1:serv1 .".

4)Create a container with the command "docker create --name [container name] [OPTIONS] [ImageName:Tag]". I had used command "docker create --name container1 -p 80:80 hemantimage1:serv1".


## Configure AWS CLI:

## Create ECR:

## Configure GitHub Secrets:

## Configure GitHub Workflow:

