[![CircleCI](https://dl.circleci.com/status-badge/img/gh/tosyno123/project-ml-microservice-kubernetes/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/tosyno123/project-ml-microservice-kubernetes/tree/main)

# Summary of the project
This project is a pre-trained, sklearn model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. The below were done to operationalize a Python flask app using kubernetes:
1. Test the project code using linting
2. Complete a Dockerfile to containerize this application
3. Deploy the containerized application using Docker and make a prediction
4. Improve the log statements in the source code for this application
5. Configure Kubernetes and create a Kubernetes cluster
6. Deploy a container using Kubernetes and make a prediction
7. Upload a complete Github repo with CircleCI to indicate that the code has been tested

## Instructions
1. Clone the project repository to your local machine
```bash
git clone https://github.com/tosyno123/project-ml-microservice-kubernetes.git
cd project-ml-microservice-kubernetes
```

2. Create and activate a new environment
```bash
make setup
```

3. Install project dependencies
```bash
make install
```

4. You will need to install the below libraries:
 - Docker
 - Hadolint 
 - Kubernetes (Minikube)

5. You’ll need to create a free docker account, where you’ll choose a unique username and link your email to a docker account. Your username is your unique docker ID

6. After installation of the above libraries, you can verify that you’ve successfully installed docker and minikube by printing its version in your terminal
```bash
docker --version
kubectl version
```
7. Run Lint Checks
```bash
make lint
```
8. Run a Container
```bash
./run_docker.sh
```
9. Replace the ```dockerpath``` in the file ```upload_docker.sh``` then save your file
```
<<your docker ID>>/mlapi
```
10.  Upload the Docker Image
```bash
./upload_docker.sh
```
11. Configure Kubernetes to Run Locally
```bash
minikube start
```
12. Deploy with Kubernetes
```bash
./run_kubernetes.sh
```
13. Make a prediction using a separate terminal tab
```bash
./make_prediction.sh
```

## Repository Files
1. Dockerfile - this contains all the commands one could call on the command line to assemble an image
2. Makefile - this includes instructions on environment setup and lint tests
3. app.py - this is the Python flask application file
4. make_prediction.sh - this is responsible for sending some input data to your containerized application via the appropriate port
5. requirements.txt - this contains all dependencies to be installed
6. run_docker.sh - this contains commands to get Docker running locally
7. run_kubernetes.sh - this contains commands to deploy the application on the Kubernetes cluster
8. upload_docker.sh - this contains commands to upload your built image to docker and will make it accessible to a Kubernets cluster

## License
[MIT](https://choosealicense.com/licenses/mit/)
