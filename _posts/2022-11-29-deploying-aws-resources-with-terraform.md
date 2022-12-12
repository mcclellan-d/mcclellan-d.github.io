---
layout: post
title: Deploying AWS resources with Terraform
date: 2022-11-29 16:41 -0600
categories: [web, wip]
tags: [git, ci/cd, github, terraform, iac, kubernetes, k3s]
---

Services Used: *EC2, RDS, Elastic Load Balancer, Terraform Cloud, Kubernetes (K3s)*

This was from the course 'More than Certified in Terraform' by Derek Moran. This was created while following videos in 'Section 4: Deploy AWS Resources with Terraform'. All my code can be found [here on Github](https://github.com/mcclellan-d/terraform-aws). Terraform Cloud gets introduced as a service, this will manage our terraform state and later on incorporate version control systems.


## Endstate Logical Map
![endstate](https://raw.githubusercontent.com/mcclellan-d/terraform-aws/main/images/MTC_logical_map.png)

## Lesson highlights
* Configuring providers
* Deploying a VPC
* refactoring code to not be "Hardcoded"
* VPC Security groups
* Setting up RDS
* ALB Security groups & Listener
* Lifecycle policies
* Deploying EC2 instances
* Deploying NGINX with kubernetes


First we start off deploying a VPC, initially the subnets were 'hardcoded', then we refactor the code to use 'cidrsubnet()' function and utilize 'aws_availability_zones'. This allows us to easily specify the number of subnets we want and spread this across several availability zones. We finish setting up the VPCs by configuring the Route Tables and Internet Gateway, and security groups. The next stage involves the EC2 instances, setting up SSH keys, and utilize User Data to run a bash script to install and setup our K3s cluster. Lastly we deploy NGINX with our K3s cluster.

## Additonal notes 

The region was swapped to 'eu-north-1' so most of this can be kept in the AWS free-tier. t2.micro is not available in that region, thus t3.micro is offered instead. K3s was picked over K8s as it has less computational overhead. Rather than using ETCD we're using a MySQL instance on RDS, this also takes advantage of the free-tier and reduces load on ec2 instances.



### Relevant links
https://github.com/mcclellan-d/terraform-aws

More Than Certified - Derek Morgan\
https://courses.morethancertified.com/p/mtc-terraform