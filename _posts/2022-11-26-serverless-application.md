---
layout: post
title: Serverless Application
date: 2022-11-26 18:09 -0600
categories: [cloud]
tags: [aws, serverless, lambda, api]
---
# Serverless Application
AWS Services Used: *S3, API Gateway, Lambda, Step Functions, Simple Email Service(SES), Simple Notification Service(SNS)*

This was a silly lab but was an excellent way to incorporate many of the services covered by the Solutions Architect course. 

This lab consisted of 5 stages:
- STAGE 1 : Configure Simple Email service 
- STAGE 2 : Add a email lambda function to use SES to send emails for the serverless application 
- STAGE 3 : Implement and configure the state machine, the core of the application
- STAGE 4 : Implement the API Gateway, API and supporting lambda function
- STAGE 5 : Implement the static frontend application and test functionality

![endstate_lab](https://raw.githubusercontent.com/acantril/learn-cantrill-io-labs/master/aws-serverless-pet-cuddle-o-tron/02_LABINSTRUCTIONS/ARCHITECTURE-ENDSTATE.png)

## Issues
There were a few issues with this lab. Due to regulations in the United States, there are more barriers involved with getting a phone number for the SNS service. I configured everything for SNS but there would be a several day delay to get the number working, and involve additional costs.

Lab Source code:
https://github.com/acantril/learn-cantrill-io-labs/tree/master/aws-serverless-pet-cuddle-o-tron