---
title: "Proxmox Virtual Environment"
date: 2023-03-18T22:52:04-04:00
tags: ['home-lab','virtualization']
---

{{< context >}}

![Proxmox banner](/images/proxmox-banner.png)

# Type 1 Hypervisor, a VM Server, for free, in the cloud

Soon after building my [custom DIY Desktop PC](/home-lab/desktop) and replacing my old PC, I watched a [video on YouTube](https://www.youtube.com/watch?v=_u8qTN3cCnQ) by NetworkChuck about Proxmox, a type of virtualization software that I could run as a server. Once I found out I could turn the old computer into a VM server, I knew immediately that I had to make it happen.

In March of 2023, I took the old pre-built computer I had purchased from NewEgg and upgraded nearly every single part of it. Where before I would severely limit how often I opened the comptuer's case for fear of breaking something, I now enjoyed completely breaking down the machine and rebuilding it as if it was from parts. When it finally booted up with all the upgrades installed, I was so excited - I couldn't wait to install Proxmox.

And that's what I did. With my new "old computer" ready, I watched a few YouTube videos and made Proxmox happen. Then, I immediately took it a step further by making sure it had the GPU passthrough right at the start, just like I had done with the [QEMU setup](/home-lab/virtualization/qemu) on my desktop PC. The upgraded parts came from a one-at-a-time process of trying to fix different problems as they came up. But, I got it done, and my type 1 hypervisor VM juggernaut was ready.

Building out another component of my home lab on my personal home cloud really motivated me to tackle other home lab projects. I felt like I could do it all! But, I had to wait. Right after completing the server, I began studying intensely for the CompTIA Security+ exam, and I had to take a pause from VMs and hypervisors and home lab projects.

Since building the server, Proxmox has become an essential part of my home network. With my self-hosted VM server, I can:

- run a VM that hosts all my [Docker containers](/home-lab/virtualization/docker).
- try out other Linux distributions that I don't want to install on bare metal.
- use it to play old software, like the occasional ISO I have from old video games I use to play on Windows 98 or Windows XP.
- test out anything I want, like intentionally downloading old viruses onto a Windows XP machine.
    - And, I can do that all from within a safe environment where I can delete the VM the moment I'm done with it, and it doesn't harm any of my other machines.
- do all of this without bloating my [main machine](/home-lab/desktop) with test VMs, or detracting from its [virtualization tasks](/home-lab/virtualization/qemu) by utilizing system resources for smaller VMs.

That's awesome.

[![Proxmox - Ubuntu VM](/images/proxmox-ubuntu.png "Proxmox - Ubuntu VM")](/images/proxmox-ubuntu.png)

*A screenshot of the desktop of a Ubuntu VM, being run on a local Proxmox server and being accessed through a web browser.*

---

## The Build

### Hardware upgrades:

- Motherboard: ASRock B450M Pro4 -> ASUS
	- Old motherboard was giving me issues in conjunction with other upgraded parts
- CPU: AMD Ryzen 2700X -> AMD Ryzen 5700G
	- This was a crucial upgrade, as the integrated graphics allowed for the passthrough of the GPU, while still allowing the hypervisor to boot.
- RAM: 16GB -> 32GB
	- More RAM to split between all the virtual machines
- Storage: blah
- GPU: NVIDIA GeForce -> AMD Radeon
	- Technically a side-grade at best. I gave the NVIDIA card to my [desktop](/home-lab/desktop) for use with [QEMU](/home-lab/virtualization/qemu). However, I needed to passthrough a GPU, so I went and found the cheapest Chinese GPU I could find.

### Software stack:

- Proxmox Virtual Environment
    - Type 1 hypervisor

![Docker VM - Neofetch](/images/docker-vm-neofetch.png "Docker VM - Neofetch")

*A neofetch of a SSH terminal window of the Arch Linux VM running on my Proxmox VE server. The Arch VM is actively running all of my Docker containers.*

---

## How to do backups using CLI

/var/lib/vz
: Directory for VM images and something else...


/etc/pve/qemu-server
: stuff


/etc/...
: more stuff

---

## Fresh Install Bullet Points

Here's how I would reinstall Proxmox if I needed to:

- Go to my personal GitHub and reference my guides on:
    - [Installing Proxmox](https://github.com/DavidVogelxyz/library/blob/main/proxmox/install-proxmox.md)
    - [GPU passthrough on Proxmox](https://github.com/DavidVogelxyz/library/blob/main/proxmox/proxmox-gpu-passthrough.md)

Thanks to those who got me here!

- [Proxmox documentation](https://pve.proxmox.com/wiki/PCI_Passthrough) on how to set up PCI (GPU) passthrough
- [NetworkChuck Proxmox install video](https://www.youtube.com/watch?v=_u8qTN3cCnQ)
- [TechnoTim 11 Things to Setup Proxmox video](https://www.youtube.com/watch?v=GoZaMgEgrHw)

## {{< youtube id="_u8qTN3cCnQ" title="Installing Proxmox with NetworkChuck" >}}

## {{< youtube id="GoZaMgEgrHw" title="First 11 Things on Proxmox with TechnoTim" >}}

