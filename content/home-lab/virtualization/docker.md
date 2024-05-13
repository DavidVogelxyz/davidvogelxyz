---
title: "Docker Containers on Arch Linux VM"
date: 2023-05-31T16:22:27Z
tags: ['home-lab','virtualization']
---

{{< context >}}

![Docker banner](/images/docker-banner.png)

## Everybody Loves Docker

Since getting into virtualization, I have heard tons of people say many positive things about `Docker`. I created a Ubuntu VM in early 2023 when I first created my [Proxmox server](/home-lab/virtualization/proxmox), but I had only created one or two containers quickly. Now, I not only had an interest in learning about Docker, but a need to learn Docker: I wanted to host my [Hugo server](/home-lab/services/hugo) using Docker, so I could work on my website before pushing it live.

Docker is incredibly lean. The VM I have Docker running on was given a small amount of CPU resources and only 4GB of RAM. Despite that, it has the ability to run tons of containers all at the same time. While I have been able to run certain containers in ways to push their resource use and max out the VM, it's not something that I've run into during standard server use.

![Docker VM - Neofetch](/images/docker-vm-neofetch.png "Docker VM - Neofetch")

*A neofetch of a SSH terminal window for the Proxmox VM running my Docker containers.*

---

## The Build

### Hardware (virtualized):

- 2 CPU cores @ 3.8GHz
- 4GB RAM

### Software:

- Docker
- Portainer

### Portainer

I really, really like `Portainer`. It has made getting into Docker extremely easy. While it was good to watch [this NetworkChuck video](https://www.youtube.com/watch?v=eGz9DS-aIeY) and do the exercise with him of setting up containers using the command line, there's a lot with Docker that can get confusing when it comes to the proper switches and flags. Portainer makes it incredibly easy to get Docker containers set up that run the way I want them to.

[![Portainer - Dashboard](/images/portainer-dashboard.png "Portainer - Dashboard")](/images/portainer-dashboard.png)

*An image of the dashboard of the web UI for the Portainer docker container, running on my Arch Linux VM, which itself runs on my Proxmox VE server. So cool.*

---

## Fresh Install Bullet Points

Here’s how I would reinstall Docker and Portainer if I needed to:

- Go to my personal GitHub and reference my guides on:
    - [Installing Docker and Portainer on Arch Linux](https://github.com/DavidVogelxyz/library/blob/master/docker/install-docker-arch.md)
- [NetworkChuck Portainer video](https://www.youtube.com/watch?v=iX0HbrfRyvc) on YouTube

Thanks to those who got me here!

- [NetworkChuck Docker playlist](https://www.youtube.com/playlist?list=PLIhvC56v63IJlnU4k60d0oFIrsbXEivQo) on YouTube

## {{< youtube id="iX0HbrfRyvc" title="Installing Portainer with NetworkChuck" >}}

## {{< youtube id="eGz9DS-aIeY?list=PLIhvC56v63IJlnU4k60d0oFIrsbXEivQo" title="Docker playlist with NetworkChuck" >}}

