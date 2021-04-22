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

### How to run the container:
You can run the docker container using the command "docker run [OPTIONS] IMAGE [COMMAND] [ARG...]".

OR

You can just start the container using the command "docker start [container name]". Like I had used "docker start container1" to start my container.

### How to view the project:
Open your browser and go to ip and port "localhost:80".

## Configure AWS CLI:
1)Download AWS CLI Intaller from https://aws.amazon.com/cli/.

2)Run the downloaded MSI installer or the setup file and follow the instructions.

3)To confirm the installation, use the "aws --version" on your cmd.

4)Configure your AWS IAM user with admin credentials using the command "aws configure" and type your "AWS Access Key Id", "AWS Secret Access Key", "Default Region Name" and "Default output format". All of these provided by your AWS IAM user.

AWS IAM User Credentials I used:

AWS Access Key Id = AKIATMNUEADG7H6GCRLY

AWS Secret Access Key = gmUw5pcUr99GQRC8U8CwND9QLKZBtSRsstNBUY+R


## Create ECR:
You can create Elastic Container Registry(ECR) using the command:

"aws ecr create-repository --repository-name [Repository Name] --region [Configured Region]".
    
I have created ECR using the command:

"aws ecr create-repository --repository-name ceg3120/hemantsharmarepo --region us-east-1" 

My repository name = ceg3120/hemantsharmarepo.

## Configure GitHub Secrets:

1)On GitHub, navigate to the main page of the repository. Under your repository name, click Settings.

2)In the left sidebar, click Secrets.

3)Click New repository secret.

4)Type a name of the secret and secret value.

5)Click Add secret.

I have created 2 secrets :

"AWS_ACCESS_KEY_ID" = To store the access key id. Value = AKIATMNUEADG7H6GCRLY.

"AWS_SECRET_ACCESS_KEY" = To store the secret access key. Value = gmUw5pcUr99GQRC8U8CwND9QLKZBtSRsstNBUY+R..

## Configure GitHub Workflow:

From your repository on GitHub, create a new file in the .github/workflows directory named [workflowfileName.yml].
    
    NOTE:Workflow file has a extension .yml

I created my workflow file in .github directory with the name "workflow.yml". Followings are variables to change:

name

AWS_REGION

ECR_REPOSITORY

CONTAINER_NAME

aws-access-key-id (Will be taken automatically from secrets)

aws-secret-access-key (Will be taken automatically from secrets)

aws-region

ECR_REGISTRY

IMAGE_TAG

run

## Docker Pull (Extra Credit):
You can pull images from docker hub repository using the command "docker pull [options] [ImageName]".

Please note: A repository can contain multiple images. To pull all images from a repository, provide the -a (or --all-tags ) option when using docker pull.

I have pulled the image hello-world with latest tag from library repository which is public. Using the command "docker pull hello-world".

There is no requirement to pull image from public repository just pull it using the command mention above. On the other hand, you need to have a Kubernetes cluster, and the kubectl command-line tool must be configured to communicate with your cluster.

You can run the image using the command "docker run hello-world:latest".
