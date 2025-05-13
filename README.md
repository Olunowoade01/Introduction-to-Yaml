# Introduction to YAML and Kubernetes



This project demonstrates how to deploy a simple Nginx web server application to a Kubernetes cluster using YAML files. Additionally, it explores how containers within a pod can communicate with each other using `localhost`. By following this guide, you will gain hands-on experience with Kubernetes deployments, services, and multi-container pods.



## Project Overview

The project is divided into two parts:

1. **Deploying an Nginx Application**:
   - Start Minikube.
   - Create and verify a deployment for the Nginx application.
   - Expose the deployment as a service.
   - Access the application through the Minikube IP address.

2. **Networking in Kubernetes**:
   - Create a multi-container pod with Nginx and BusyBox.
   - Demonstrate communication between containers using `localhost`.



# 1. Deploying an Nginx Application

# Step 1: Start Minikube
Minikube is a tool that allows you to run Kubernetes locally. Start Minikube to set up your local Kubernetes cluster.


`minikube start`


![1](./img/1%20start%20minikube.png)

### Step 2: Create the Deployment
Create a deployment for the Nginx application using a YAML file (`nginx-deployment.yaml`). This file defines the desired state of the application, including the container image and the number of replicas.


`kubectl apply -f nginx-deployment.yaml`


![2](./img/2%20create%20deployment.png)

### Step 3: Verify the Deployment
After applying the deployment YAML file, verify that the deployment has been created successfully and is running.


`kubectl get deployments`


![6](./img/6%20deployment%20created.png)

![7](./img/7%20deployment%20running%20.png)

### Step 4: Expose the Deployment
Expose the deployment as a service using a YAML file (`nginx-service.yaml`). This step makes the application accessible via a NodePort or LoadBalancer.


`kubectl apply -f nginx-service.yaml`


![3](./img/3.%20expose%20deployment.png)

### Step 5: Verify the Service
Check that the service has been created successfully. The service will route traffic to the Nginx deployment.


`kubectl get services`

![5](./img/5%20service%20created.png)

### Step 6: Get the Minikube IP Address
Retrieve the Minikube IP address, which will be used to access the Nginx application.


`minikube ip`


![8](./img/8%20get%20ip%20address.png)

![9](./img/9%20minikube%20ip.png)

### Step 7: Access the Application
Open a web browser and navigate to the Minikube IP address. You should see the Nginx welcome page, confirming that the application is running successfully.

![1](./img/10%20welcome%20to%20darey%20.png)



## Part 2: Networking in Kubernetes

### Step 1: Start Minikube
Before proceeding with our project, we need to start Minikube.


`minikube start`


![1](./img/01%20start%20minikube%20cont.png)

### Step 2: Create the Multi-Container Pod
Create a file named `multi-container-pod.yaml` and paste the provided snippet. The YAML file defines a pod with two containers: one running Nginx and another running BusyBox.




![2](./img/02%20creat%20a%20file%20cont.png)

### Step 3: Apply the YAML Configuration
To create the pod, apply the YAML configuration using `kubectl apply`. Open a terminal and navigate to the directory where you saved the `multi-container-pod.yaml` file.


`kubectl apply -f multi-container-pod.yaml`


![3](./img/03%20paste%20link%20in%20file%20cont.png)



### Step 4: Verify the Pod
Check the status of the pod using `kubectl get pods`. You should see the pod listed with a status of "Running".


`kubectl get pods`


![4](./img/04%20pod%20creadted%20cont.png)

### Step 5: Check the Pod Logs
To verify that both containers are running and that the BusyBox container is updating the HTML file, check the pod logs.

`kubectl logs multi-container-pod`

![5](./img/05%20continuation.png)

### Step 6: Access the Nginx Server from BusyBox
To demonstrate communication between containers using `localhost`, access the Nginx server from the BusyBox container.


`kubectl exec -it multi-container-pod -- /bin/sh`


![6](./img/6%20continu.png)

## Summary

In this project, you have learned how to deploy a simple Nginx web server application to a Kubernetes cluster using YAML files. You created a deployment and exposed it as a service, making it accessible via the Minikube IP address. Additionally, you explored how containers within a pod can communicate with each other using `localhost`. This hands-on experience demonstrates the power of YAML in managing Kubernetes resources and provides a solid foundation for deploying more complex applications in the future.