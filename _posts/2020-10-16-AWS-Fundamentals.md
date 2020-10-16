# AWS Fundamentals

### AWS Overview 

What Is Cloud Computing ?
Cloud computing is the on-demand delivery of compute power, database storage, applications, and other IT resources through a cloud services platform via the internet with pay-as-you-go pricing.

Why  is Cloud ?
Each company have some Common Services and Specialized Strategic Services.
Common Services - Compute , Storage , Networking etc. Those can be used with the help of common service provider so organization can focus on there Specialized Strategic Services.

Cloud computing stack ? Infrastructure as a Service (IaaS) , Platform as a Service (PaaS) , Software as a Service (SaaS)

Cloud Computing Deployment Models ? ( fully deployed ) Cloud , Hybrid , On-premises ("private cloud")

Why AWS ? 150+ unique servics , AWS Partner Network (APN) , AWS Marketplace.

Reference :
- https://aws.amazon.com/what-is-cloud-computing/
- https://aws.amazon.com/types-of-cloud-computing/
- https://aws.amazon.com/products/
- https://aws.amazon.com/partners/
- https://aws.amazon.com/marketplace/
- https://www.coursera.org/learn/aws-fundamentals-going-cloud-native/

### AWS Infrastructure

The AWS Cloud infrastructure is built around Regions and Availability Zones. 

- Regions : Collection of AZ . One should select region based on latency , cost , services etc 
- Availability Zones (AZ) : Data Center.

Important : Resources aren't replicated across AWS Regions unless you do so specifically.

Reference :
- https://aws.amazon.com/about-aws/global-infrastructure/

### Compute Services 

Develop, deploy, run, and scale virtually any application on the world's most reliable, secure, and capable cloud.

Types of compute - Instances, containers, and serverless computing

Instances (Virtual machines) - Amazon Elastic Compute Cloud (EC2) , Amazon EC2 Spot ,  Amazon EC2 Autoscaling , Amazon Lightsail , AWS Batch

Containers - Amazon Elastic Container Service (ECS) , Amazon Elastic Container Registry (ECR) , Amazon Elastic Kubernetes Service (EKS) , AWS Fargate

Serverless - AWS Lambda 

Edge and hybrid - AWS Outposts ,  AWS Snow Family , AWS Wavelength , VMware Cloud on AWS , AWS Local Zones


Reference
- https://aws.amazon.com/products/compute/
- https://aws.amazon.com/lambda
- https://aws.amazon.com/ecs/
- https://aws.amazon.com/eks/
- https://aws.amazon.com/fargate/


### Amazon EC2

Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure and resizable compute capacity in the cloud. It's designed to make web-scale cloud computing easier for developers.

Reference :
- https://aws.amazon.com/ec2/
- https://aws.amazon.com/ec2/instance-types/

### Amazon Lightsail 

Lightsail includes everything you need to launch your project quickly--a virtual machine, solid state drive (SSD)-based storage, data transfer, Domain Name System (DNS) management, and a static IP--for a low, predictable monthly price.

Reference :
- https://aws.amazon.com/lightsail/
- https://aws.amazon.com/lightsail/pricing

### Networking on AWS

Amazon Virtual Private Cloud (Amazon VPC) 

Amazon Virtual Private Cloud (Amazon VPC) lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.

IDEA - A box where all your application live inside and nothing comes in the box and go out of box without your explicit permission. 

Important -
creating a VPC, items must you include - Region and IP range 
A subnet is a subset of IP ranges for a VPC.
Internet Getway - configure to allow your VPC to communicate to the internet

Reference :
- https://aws.amazon.com/vpc
- https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html
- https://docs.aws.amazon.com/vpc/latest/userguide/default-vpc.html

