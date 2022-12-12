---
layout: post
title: Terraform Modular Deployments
date: 2022-11-29 16:41 -0600
categories: [web]
tags: [git, ci/cd, github, terraform, iac]
---

This project utilizes openweathermap.org as the source data, NodeRed to query the data, influxdb to store the data, and Graphana to visualize the data.


This logical map is from the Terraform course I was following.

![modules_endstate_logical_map](https://raw.githubusercontent.com/mcclellan-d/terraform-docker/main/modules_endstate_logical_map.png)

The objective of this section was to learn how modules interact with each other and creating a deployment.

Here's some of the lesson highlights
- Module Variables
- Terraform Graph
- Troubleshooting dependencies
- Module outputs
- Lifecycle Customization and Targeting
- Using for_each
- Nesting modules
- Deploying the environment 






















## Related links

My Github repo: https://github.com/mcclellan-d/terraform-docker

Source Course: https://courses.morethancertified.com/p/mtc-terraform