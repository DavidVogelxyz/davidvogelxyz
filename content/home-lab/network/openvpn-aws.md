---
title: "OpenVPN Server Using Amazon Web Services"
date: 2023-06-12T15:25:35Z
tags: ['home-lab','network']
---

{{< context >}}

![AWS banner](/images/aws-banner.png)

## Introduction

For more information on how I would set up a VPN server today, check out [my guide on creating a VPN server](https://github.com/DavidVogelxyz/library/blob/master/servers/openvpn-server-on-debian.md), found on my GitHub.

---

## Welcome to the Jungle

While I have been working with cloud service providers (CSP) for months, I hadn't yet tried out Amazon Web Services (AWS). I decided to re-deploy a project that I'm familiar with, OpenVPN, because I thought it would be easy. "Easy" is not how I would describe my experience with AWS.

The OpenVPN parts of the setup were streamlined and quick; all the hurdles came from the AWS side of the experience. Everything was made intentionally obtuse, and it feels like it was done to necessitate a certification on "AWS." Instead of just spinning up a Debian server/container using an image, I had to find my way over to the "EC2" dashboard in order to search the "AMI catalog" (AMI, for Amazon Machine Image) for the right selection. The VM configuration page was also riddled with jargon and terms, with all the useful information tucked away behind links. None of this is to even mention how slow the website operates compared to Linode. Despite all the complications, I managed to boot a pre-imaged OpenVPN server and test it out.

![xkcd comic](/images/xkcd-standards.png)

*An [*xkcd* comic](https://xkcd.com/927). No context given.*

The experience with the OpenVPN web UI itself was smooth. I had never used an OpenVPN server with a web UI before, so it was fun to click around for a bit and see what all the menu options were. I eventually found out that this version of OpenVPN server was operating on a "7 day free trial," after which I would be billed via AWS. Even though I was supposed to have a "12 month free trial" with AWS for certain VMs, this apparently did not extend to the OpenVPN server. I used the server for a bit longer before bringing it down and terminating all my VMs with AWS. I like the web UI, don't like having to pay, and still prefer self hosting for my VPN needs.

I'm actually in awe of how bad my AWS experience was compared to other CSPs I've used. The AWS web dashboard was slow and painful to use, I spent far too long getting a VM spun up, and I spent the entire time feeling confused. I know from using other CSPs and their platforms that doesn't have to be the case. Other things that bothered me include:

1. Because of the SSH sign in being mediated through keys (with no passwords), AWS actually seems to disallow passwords on the servers. To me, this is a huge red flag.
1. Pricing. While "12 month free trial" sounds enticing, I saw that the pricing for a year of this VPN after the trial ended was $660 USD, or over $50 per month. That's insane.

All in all, I still have no idea what the appeal of AWS is. It just doesn't make sense to me. I still want to try Google's cloud platform though.

So far, I'm pretty happy that I started with Linode and other CSPs like it.

[![OpenVPN Admin Server - Dashboard](/images/aws-openvpn-aws-admindash.png "OpenVPN Admin Server - Dashboard")](/images/aws-openvpn-aws-admindash.png)

*An image of the dashboard to the web UI for the OpenVPN Admin Server running on an AWS machine.*

---

## The Build

### Software stack:

- Ubuntu
- OpenVPN

[![AWS Web UI - Dashboard](/images/aws-dash.png "AWS Web UI - Dashboard")](/images/aws-dash.png)

*An image of the dashboard of the web UI for Amazon Web Services.*

---

## Fresh Install Bullet Points

**NB: I have no interest in running this project again, and I have no interest in running any project on AWS ever again.**

Thanks to those who got me here!

- NetworkChuck for his [video on installing an OpenVPN server on AWS](https://www.youtube.com/watch?v=m-i2JBtG4FE)

## {{< youtube id="m-i2JBtG4FE" title="OpenVPN on pfSense with Lawrence Systems" >}}
