---
layout: post
title: Continuous Deployment using Terraform Cloud
date: 2022-12-05 21:02 -0600
category: [cloud,wip]
tags: [aws, ci/cd, github, terraform]
---

# This is a work in progress
This section of the course focuses on Terraform Cloud and Github. Most of the course had us manage the Terraform state locally on our machine. In this section we offloaded state management into *Terraform Cloud*.

We utilize the tag feature to deploy our modules.


 
 ### GitHub repos utilized as terraform Modules
[Terraform-CI/CD](https://github.com/mcclellan-d/terraform-cicd) \
We defined how we interact with AWS, GitHub, and Terraform-Cloud with these files.

[Networking Module](https://github.com/mcclellan-d/)\
We use the network module to define the VPC, public CIDRs, private CIDRs, route tables, and Security Groups.

[Compute Module](https://github.com/mcclellan-d/terraform-aws-compute)\
  Terraform compute module for deploying ec2 instances in AWS. 




### Image of Terraform Cloud compute module

![](/images/terraform_cloud-compute-module.png)