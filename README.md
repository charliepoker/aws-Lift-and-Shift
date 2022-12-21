# AWS LIFT AND SHIFT

## About The Project

- Multi Tier Web Application stack
- Host & Run on AWS Cloud For Production
- Lift & Shift Strategy

## Resources

                AWS SERVICES
    |---------------------------------------|--------------------------------------------|
    |   EC2 INSTANCES                       | VM FOR TOMCAT, RABBIT MQ, MEMCACHE, MYSQL  |
    |---------------------------------------|--------------------------------------------|
    |   ELB [LOAD BALANCER]                 | NGINX LB REPLACEMENT                       |
    |---------------------------------------|--------------------------------------------|
    |   AUTOSCALING                         | AUTOMATION FOR VM SCALING                  |
    |---------------------------------------|--------------------------------------------|
    |   S3/EFS STORAGE                      | SHARED STOAGE                              |
    |---------------------------------------|--------------------------------------------|
    |   ROUTE 53                            | PRIVATE DNS SERVICE                        |
    |---------------------------------------|--------------------------------------------|

## Objectives

- Flexible Infrastructure
- No Upfront Cost
- IAAC

## Flow of Execution

- Login to AWS Account
- Create Key Pairs
- Create Security groups
- Launch Instances with user data [Bash Scripts]
- Update IP to name mapping in route 53
- Build Application from source code
- Upload to S3 bucket
- Download artifact to Tomcat Ec2 Instance
- Setup ELB with HTTPS [Cert from Amazon Certificate Manager]
- Map ELB Endpoint to website name in Godaddy DNS
- Verfiy app can be accessed with browser
- Build Autoscaling group for Tomcat Instances

## Stack Architecture

![Architecture](./images/architecture.jpg)

## Create Key pairs

## Create Security Groups

Security group for backend

![backend-SG](./images/vprofile-backend-SG.png)

Security group for ELB

![elb-SG](./images/vprofile-elb-SG.png)

Security group for app

![app-SG](./images/vprofile-app-SG.png)

## Launch Instances with script

Ec2 Instances
![ec2-stances](./images/ec2-instances.png)

## Update IP to name mapping in route 53

Hosted Zone
![hosted-zone](images/hosted-zone.png)
Records in hosted zone
![records-in-hosted-zone](images/records-in-hosted-zone.png)

## Build Application from source code

Build app with maven
![build-app-with-maven](./images/build-app-with-mvn.png)

## Upload to S3 bucket

Create S3 bucket
![create-bucket](images/create-s3-bucket.png)
![create-bucket-image](images/s3-bucket-for-artifact.png)
![artifact-in-s3-bucket-image](images/artifact-in-s3-bucket.png)

## Download artifact to Tomcat Ec2 Instance

![artifact-copy-to-app-server](images/artifact-copy-to-app-server.png)

## Map ELB Endpoint to website name in Godaddy DNS

![cname-record](images/cname-record.png)

## Verfiy app can be accessed with browser

App Login Page
![vprofile-login-page](images/vprofile-login-page.png)

App Dashboard
![vprofile-dashboard-page](images/vprofile-dashboard.png)

## Build Autoscaling group for Tomcat Instances

Autoscaling Group
![vprofile-LB](images/vprofile-load-balancer.png)

### Thank You!!!
