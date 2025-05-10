# Introduction to YAML

 This project demonstrates how to deploy a simple Nginx web server application to a Kubernetes cluster using YAML files. By following this guide, you will learn how to create and apply Kubernetes deployment and service YAML files to manage your application.



## Project Overview

The project involves the following steps:

1. Starting Minikube, a local Kubernetes cluster.
2. Creating a deployment for the Nginx application using a YAML file.
3. Exposing the deployment as a service to make it accessible.
4. Verifying the deployment and service status.
5. Accessing the Nginx application through the Minikube IP address.


## Step-by-Step Guide

### 1. Start Minikube
Minikube is a tool that allows you to run Kubernetes locally. Start Minikube to set up your local Kubernetes cluster.

using command `Start Minikube`

![1](./img/1%20start%20minikube.png)



### 2. Create the Deployment
I create a deployment for the Nginx application using a YAML file (`nginx-deployment.yaml`). This file defines the desired state of the application, including the container image and the number of replicas.

using command `nginx-deployment.yaml`

![2](./img/2%20create%20deployment.png)



### 3. Verify the Deployment
After applying the deployment YAML file, verify that the deployment has been created successfully and is running.



![6](./img/6%20deployment%20created.png)

![7](./img/7%20deployment%20running%20.png)



### 4. Expose the Deployment
Expose the deployment as a service using a YAML file (`nginx-service.yaml`). This step makes the application accessible via a NodePort or LoadBalancer.

using command `

![3](./img/3.%20expose%20deployment.png)

using command `nginx-service.yaml`

### 5. Verify the Service
I check that the service has been created successfully. The service will route traffic to the Nginx deployment.

![5](./img/5%20service%20created.png)


### 6. Get the Minikube IP Address
I retrieve the Minikube IP address, which will be used to access the Nginx application.

using command `minikube ip`

![8](./img/8%20get%20ip%20address.png)

![9](./img/9%20minikube%20ip.png)



### 7. Access the Application
I Open a web browser and navigate to the Minikube IP address. and i can see the Nginx welcome page, confirming that the application is running successfully.

![1](./img/10%20welcome%20to%20darey%20.png)



## Summary

In this project, i have learned how to deploy a simple Nginx web server application to a Kubernetes cluster using YAML files. i created a deployment and exposed it as a service, making it accessible via the Minikube IP address. This hands-on experience demonstrates the power of YAML in managing Kubernetes resources and provides a solid foundation for deploying more complex applications in the future.