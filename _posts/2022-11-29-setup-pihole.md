---
layout: post
title: Implemented Network-level adblocking Pi-hole
date: 2022-11-29 20:52 -0600
categories: [homelab]
tags: [linux, dns, raspberry_pi]
---

## Network Wide Ad-blocking
I absolutely detest ads, they're intrusive and they make web browsing slower and less enjoyable. Nearly all my devices have some form of ad-blocking... but a few things still slip through the cracks. That's where the pi-hole comes in. We can block advertising domains at the network level. This is accomplished by handling dns requests through the pi-hole, we can process all domain name resolution requests and prevent them from resolving to an IP address. 

![pihole_dashboard](/images/pihole_dashboard.png)

Easy Installation
```bash
git clone --depth 1 https://github.com/pi-hole/pi-hole.git Pi-hole
cd "Pi-hole/automated install/"
sudo bash basic-install.sh
```

## What this won't block
This won't block advertising on everything, especially when applications are hard coded to use a different dns server. You could attempt to block all requests to the address but that can create some issues. In the instance of android smart TVs, they will attempt to reach out to google dns servers. This will require configurations on your router, which might not be available for many consumer routers.

My solution involved black-holing all traffic going to google dns servers to the ip address of the pi-hole. In addition I set all output traffic to port 53 UDP to go to the pi-hole. 

## What did I do?
- setup raspberry pi with debian
- install pi-hole
- configure network to utilize pi-hole as DNS & DHCP server
- enabled unattended updates
- setup cronjob to update pi-hole & os software weekly

Besides ad-blocking, the pi-hole is a core piece of my homelab. All computers and devices use it as a DHCP server and automatically get name resolution. All of my services are resolved internally and have a FQDN. Thanks to Let's encrypt, I have a wildcard TLS certificate for my services. 

## Improvements for the future
Once I can get my hands on some new hardware, I would like to redo my network and setup two pi-holes. I would also like to make them highly available by implementing [Gravity Sync](https://github.com/vmstan/gravity-sync). This will keep all my configurations synchronized and easy to replace.

Source project:\
https://pi-hole.net/