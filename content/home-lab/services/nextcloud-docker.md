---
title: "Nextcloud Cloud Storage, in a Docker container"
date: 2023-07-08T22:24:38-04:00
tags: ['home-lab','services']
---

{{< context >}}

![Nextcloud banner](/images/nextcloud-banner.png)

## A Personal, Secure, Open-Source Cloud Storage Suite

Having just completed the [website and e-mail server](/home-lab/services/web-server) project, I was looking for another project to expand my home-lab. Fortunately, NetworkChuck had just released a video a few weeks before on setting up what is essentially a "self-hosted version of Google Cloud." After watching the video, I decided this would be a worthwhile project to work on.

However, NetworkChuck's video was about using a software called FileCloud, and deploying it on Amazon Web Services (AWS). After my [previous experience with AWS](/home-lab/network/openvpn-aws), I chose not to go that route. I also reviewed FileCloud, and decided not to use it, as it wasn't free and open-source software (FOSS).

Instead, I opted to deploy Nextcloud, a FOSS solution, on Vultr. While I could have also deployed this server on my local [Proxmox](/home-lab/virtualization/proxmox), I would have to open up my home network in order to make the service publicly accessible, which was something I didn't want to do. At the time, I didn't know enough about networking and deploying remote SSH tunnels to have known there were other solutions to this problem. While I already had my TrueNAS configured and working, I didn't feel comfortable opening up public access to my private NAS. I wanted something separate from my NAS, that also came with a web UI for easy drag-and-drop access regardless of what computer I was using. As a reference, I had used ProtonDrive in the past, and I was looking for a self-hosted FOSS solution that would mimic the experience I had there.

So, with my plan in hand, I spun up a Debian VM on Vultr and deployed a Docker container running Nextcloud All-in-One (AIO), using Portainer to make the container management easier. I also purchased a domain to pair with the server, so that I could easily access the server from any VM or computer I used in the future. Given that the Nextcloud documentation specified certain resource usage, but also keeping in mind cost limitations, I decided to roll with a $20/month Vultr VM with 2 CPUs, 4GB RAM, and 80GB storage. I had very little issue with running the Docker container after my [previous experience with Docker](/home-lab/virtualization/docker), and I shortly went into the testing phase.

This project was interesting, for a bunch of reasons. The primary reason was that this Nextcloud deployment was the first time I ran into a situation where my choice of VM was directly affecting performance. I actually started with a $10/month 1 CPU, 2GB RAM machine, and instantly would have problems with the server crashing when trying to upload files to my shared drive. Even after upgrading to the 4GB RAM version, I was still encountering issues with the web UI locking up if I interacted with it too much. Any of these server issues ended up requiring a server restart. It was incredibly frustrating, and directly impacted my ability to make use of the service I had created.

Eventually, I realized that I was either going to be paying $20/month for a sub-par experience, or have to upgrade to the $40/month 8GB RAM VM in order to get the performance I was looking for. For the amount of usage I was getting from the deployment, I couldn't justify a $240/year server, and I *really* couldn't justify a $480/year server. So, after a month of testing the Nextcloud Docker container, I shut down the server and moved on to other projects. Fortunately, I had one on my radar: testing out [NixOS](/home-lab/other/nixos).

---

## Helpful Videos

## {{< youtube id="xBIowQ0WaR8" title="build your own cloud" >}}
