---
title: "QEMU on Artix Linux Desktop PC"
date: 2023-02-20T22:51:13-04:00
tags: ['home-lab','virtualization']
---

{{< context >}}

![QEMU banner](/images/qemu-banner.png)

# Virtualization for the Desktop

`QEMU` is a type 2 hypervisor. What that means is that, I can install `QEMU` on an operating system, like Artix Linux on my [desktop PC](/home-lab/other/desktop), and that will allow me to virtualize computers within my computer. Using a type 2 hypervisor, I can run virtual machines of all different operating systems from *within* my Linux PC. As an example, I can run Windows occasionally for games, but virtualize Windows within my Linux OS, and that keeps all of the spooky stuff that Windows does restricted to the virtual machine.

Almost immediately after I got my new desktop PC up and running, I installed `QEMU`, `virt-manager`, and a few other packages on it. Not only did I manage to get the hypervisor running; but, not long after that, I successfully passed through the second GPU to the virtualization software. With assistance from an HDMI splitter, I can access my VMs from the same keyboard, mouse, and monitor. That may not sound special on its own, but consider that the setup needs to receive two different HDMI outputs from two different GPUs in order to work. Because of this setup, I am able to get essentially bare metal performance from my Windows VMs, which means that high performance tasks like gaming work just as well virtualized.

Because of my success with installing `QEMU` and getting the GPU passed through, I was starting to feel good at computers. I got this virtualization setup working, which was one of the main drivers behind building the new PC. But, in addition, I also had installed a 'new-to-me' version of Linux (Arch, as opposed to Ubuntu/Debian), and I was still successful. I felt like I could tackle any home lab project and I'd make it work. So, when I soon heard about type 1 hypervisors, like Proxmox, I was eager to build out a [VM server self-hosted by my own personal cloud](/home-lab/virtualization/proxmox).

[![Windows 10 VM - Desktop](/images/qemu-win10-desktop.png "Windows 10 VM - Desktop")](/images/qemu-win10-desktop.png)

*A screenshot of the desktop of my Windows 10 VM, running on my Artix Linux Desktop PC using QEMU. There are a couple of `dxdiag` windows up showing the NVIDIA GPU being passed through, as well as the hardware that Windows 10 is virtualizing on top of.*

---

# The Build

QEMU

- Type 2 hypervisor
- Deployed using [Desktop](/home-lab/desktop)

![Desktop - Neofetch - QEMU](/images/desktop-with-qemu-windows.png "Desktop - Neofetch - QEMU")

*A `neofetch` of the desktop PC while also virtualizing my Windows 10 gaming VM.*

---

## Fresh Install Bullet Points

Here's how I would reinstall QEMU on an Arch Linux machine if I needed to:

- Go to my personal GitHub and reference my guides on:
    - [Installing QEMU on Arch Linux](https://github.com/DavidVogelxyz/library/blob/main/qemu/install-qemu-arch.md)
    - [GPU passthrough on QEMU](https://github.com/DavidVogelxyz/library/blob/main/qemu/qemu-gpu-passthrough.md)

Thanks to those who got me here!

- [Arch Linux wiki](https://wiki.archlinux.org/title/PCI_passthrough_via_OVMF) article on PCI passthrough
- Mental Outlaw [QEMU install video](https://www.youtube.com/watch?v=wxxP39cNJOs)
- Mental Outlaw [GPU pass-through video](https://www.youtube.com/watch?v=KVDUs019IB8)

## {{< youtube id="wxxP39cNJOs" title="Installing QEMU with Mental Outlaw" >}}

## {{< youtube id="KVDUs019IB8" title="GPU pass-through with Mental Outlaw" >}}

