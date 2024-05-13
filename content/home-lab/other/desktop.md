---
title: "DIY Desktop PC Running Artix Linux"
date: 2023-02-13T22:51:03-04:00
tags: ['home-lab']
---

{{< context >}}

![Artix banner](/images/artix-banner.png)

# The New Computer

This desktop PC, which I built from parts in February 2023, is ridiculously awesome. Why?

- Because I built it myself.
    - Building my PC gave me a greater understanding of the inner workings of computers. Even though I had been working with the Raspberry Pi for over a year, I learned more from building a PC that I had from the Pi computers. I felt empowered to diagnose and fix my own computer problems. It was cool.
- Because it runs Artix Linux.
    - I had been running Ubuntu Desktop on my desktop PC since summer 2022, and I had tried Arch before. However, this was my first time using Arch as a daily driver.
    - LARBS!
- Because I learned about [virtualization](/home-lab/virtualization/).
    - One of the reasons why I built this computer with the parts I chose was for virtualization. I had been having trouble playing certain games on Linux because I was using container solutions and emulators to run the games, and I had heard that virtualization through a software such as [QEMU](/home-lab/virtualization/qemu) could be a potential solution.
- Because all of this gave me the tools to learn about [Proxmox virtualization](/home-lab/virtualization/proxmox).
    - While working with QEMU to set up virtual machines was useful in setting up a Proxmox server, so was building a PC. It gave me the skills to rebuild my old desktop PC and convert it into a Proxmox server.

So, for all these reasons and more, my current desktop PC is a powerhouse.

![Desktop - Neofetch](/images/desktop-neofetch.png "Desktop - Neofetch")

*A neofetch of the desktop PC at rest after running VMs for nearly 2.5 days.*

---

# The Build

## Hardware:

- Motherboard: ROG Strix X570-E
- CPU: AMD Ryzen 9 5900X
- RAM: 64GB (4x 16GB) G.Skill Trident Z DDR4 3600MHz
- GPU 1: 12GB AMD Radeon RX 6700 XT GDDR6
- GPU 2: 8GB NVIDIA GeForce RTX 2070
- Storage 1: 1TB Samsung 980 Pro SSD
- Storage 2: 1TB Samsung 980 Pro SSD
- Storage 3: 4TB Seagate Barracuda HDD


## Software:

- Artix Linux
    - Arch-based
- LARBS
- QEMU

Installed using legacy boot (BIOS) and a fully encrypted root partition.

I use LARBS, created by Luke Smith, as a desktop solution. Check out [LARBS on Luke's site](https://larbs.xyz) or over on [Luke's GitHub](https://github.com/LukeSmithxyz/LARBS). It uses a combination of `dwm` and `dmenu` to create a simple window manager solution.

One of the things I find most impressive about my desktop is not how much software it runs, but actually how *little* software it runs.

I used [virtualization](/home-lab/virtualization/) to solve some of those needs. With [QEMU](/home-lab/virtualization/qemu), I can spin up a Windows machine for any software I want to use that runs best on Microsoft software. No more Wine containers, or bottles; no more Lutris; and, no more having to stash a Windows computer for "just in case." In fact, the performance using QEMU is so good, that I even install any superfluous Linux software on a VM *first*, meaning that the amount of software I install on bare metal is very little.

---

## Fresh Install Bullet Points

Here's how I would reinstall my current desktop if I needed to:

- Go to my personal GitHub and reference my guides on:
    - [Installing Artix Linux](https://github.com/DavidVogelxyz/library/blob/master/install-os/install-arch.md)
    - [Security Hardening on Artix Linux](https://github.com/DavidVogelxyz/library/blob/master/security/secure-arch.md)
    - [Installing QEMU on Artix Linux](https://github.com/DavidVogelxyz/library/blob/master/qemu/install-qemu-arch.md)
- Download LARBS for the desktop

Thanks to those who got me here!

- Building a PC
    - Linus Tech Tips
        - [Video 1 POV](https://www.youtube.com/watch?v=v7MYOpFONCU)
        - [Video 2 comprehensive](https://www.youtube.com/watch?v=BL4DCEp7blY)
- Installing Artix Linux
    - This [guide by Luke Smith](https://videos.lukesmith.xyz/w/n1cMQYYzwPoegM2oXfz2iC) ([YouTube link](https://www.youtube.com/watch?v=dI3bGeT31Bo))
    - The [Artix wiki](https://wiki.artixlinux.org)
    - The [Arch wiki](https://wiki.archlinux.org)
- Learning Artix Linux
    - [VimTutor with Vim Diesel](https://www.youtube.com/watch?v=d8XtNXutVto)
    - [Using LARBS]()

## {{< youtube id="v7MYOpFONCU" title="Build Computer Video #1" >}}

## {{< youtube id="BL4DCEp7blY" title="Build Computer Video #2" >}}

## {{< youtube id="dI3bGeT31Bo" title="Install Artix Linux with Luke Smith" >}}

## {{< youtube id="d8XtNXutVto" title="VimTutor with Vim Diesel" >}}

