# Build-2048-App-EKS-AWS
Build a Highly Available, scalable and fault tolerant Application in Elastic Kubernetes Service using AWS

## Introduction:
This project demonstrates deploying Highly Available, Scalable and Resilient 2048 application in AWS EKS Cluster. A Containerized application deployed in multiple availability zones in Private subnet of VPC and application load balancer is hosted in public subnet which can access the application in private subnet.

## Architecture

<img width="1145" height="709" alt="Screenshot 2025-07-16 at 8 06 22 PM" src="https://github.com/user-attachments/assets/2388086d-9857-43b1-bbb3-0ded04e730da" />

-------------------
## Project Highlights:
1. Containerization:
   * Containerized the 2048 application using docker to ensure consistent runtime environment

2. EKS Cluster:
   * It is fully managed Kubernetes cluster, Created the EKS Cluster from the stratch using EKSCTL utility for creating the Highly availability and resilience solution
  
3. FARGATE:
   * Created the Fargate profile(Serverless compute) for worker nodes for running containerized application

4. Kubernetes Tools:
   * Managed Kubernetes clusters using kubectl, eksctl, and Helm for streamlined operations.

5. Elastic Container Registry (ECR):
   * Set up ECR to store Docker images for streamlined deployment to EKS.

6. Route 53:
   * Created the Route 53 alias record to route traffic to the load balancer

7. Load Balancer:
   * Created and deployed the ALB in public subnet in multiple availability zones for high availabilityy and to route traffic to the fargate in worker nodes using Ingress Controller

8. VPC:
   * Created the Virtual network space from scratch to create the eks cluster in secure environment

---------------
### Understanding EKS Cluster:
* Control plane : Managed by AWS, including the components such as API Server, etcd, cloud controller manager, scheduler.
* Woker Nodes: It is handled ny us for creating the node group such as EC2 instances or serverless compute as fargate to run the application.
* Integration : AWS eases the process of connecting between control plane and data plane
* Networking: Configured the secure communication between control plane and worker nodes
* Monitoring and Logging : Integrated cloudwatch for the realtime performance and health tracking

-------------------
### Resources created for the application:
1. Deployment : It contains the pod configuration such as app docker image and replica set configuration
2. Service : It is used for exposing the apps to external world and perform service discovery using labels and selectors
3. Ingress Resource : It contains the configuration for routing the external traffic to service which inturns reaches the containerized app running in pod
4. ALB Ingress Controller : This controller is deployed in control plane which will watch all the ingress resources and will configure the Load balancer

-----------
## Request Flow 
EXternal Request -> Load Balancer -> Ingress resource -> Service -> Deployment -> Pods

-----------
## Conclusion:

In conclusion, this project highlights the successful implementation of a  application hosted on an AWS EKS Cluster, following cloud-native principles. By leveraging AWS's robust services and integrating best practices, the architecture delivers high scalability, resilience, and security while remaining cost-efficient. This hands-on experience reinforces the practical knowledge of designing, deploying, and managing cloud-based applications, making it a significant step forward in mastering modern application hosting solutions.



