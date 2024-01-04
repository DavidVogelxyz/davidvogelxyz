---
title: "Network Attached Storage Using TrueNAS Scale"
date: 2023-04-23T22:56:32-04:00
tags: ['home-lab','services']
---

{{< context >}}

![TrueNAS banner](/images/truenas-banner.png)

## Self-hosted Cloud Storage

If the [Proxmox VE server](/home-lab/virtualization/proxmox) wasn't my first "home lab flex," then my network attached storage (NAS) definitely was. It's a flex because of the hardware it's running, but it's also a flex because of the software it's running. And, it's a flex because of how that software is configured. It was actually as impressive as rebuilding a PC and turning it into a Proxmox server with GPU passthrough. Maybe more.

What makes my NAS so great?

The 16GB of RAM it has is pretty great. What makes it better is that I had to completely disassemble the ASUSTOR NAS I had purchased in order to install the two RAM modules. After working on my desktop PC and the Proxmox server, opening up a NAS was no problem, even if it was a complete disassembly.

It runs TrueNAS Scale. TrueNAS is awesome because it's free and open-source software (FOSS) that's built on a Debian architecture. What's more awesome is that I installed TrueNAS on a device whose manufacturer doesn't condone non-official softwares being installed on their hardware. I would rather have control over the devices I purchase than have a warranty, so I just installed my own software over it. So cool.

The 4 drives that fill the 4 bays of the NAS, and all their storage capacity, are maybe the best part. Self-hosting my own cloud storage that I can access from anywhere with the help of my [home VPN server](/home-lab/network/openvpn-raspberry-pi) -- that's undoubtedly pretty cool. ***BUT***, what's actually the best part is how I set those drives up:

- The NAS is running ZFS as the file system.
- The NAS is configured in RAID 10.
    - RAID 10 isn't officially a thing in ZFS. So, I just configured my datapool to stripe the data between two drives, and then use the *other* two drives as mirrors. Basically, a RAID 10 on ZFS.
    - I get 50% of the theoretical storage capacity of my 4 drives, but I get increased transfer speeds and the ability to lose any 1 drives without issue.
        - Depending on which drives fail, I can even lose two drives without issue.
- The NAS has link aggregation (LAG).
    - I had extra room on the switch, so I configured LAG on my NAS take advantage of the second Gigabit Ethernet port and speed up transfer times.

That's why my NAS is such a "home lab flex" -- it's freaking awesome.

---

## The Build

### Base - ASUSTOR NAS:

- Upgrades/additions:
    - 16GB RAM, upgraded from 4GB
    - Internal SSD
    - 4x 8TB hard drives

### Software

- TrueNAS Scale

---

## Fresh Install Bullet Points

Here’s how I would reinstall TrueNAS if I needed to:

- Use the [video guide](https://www.youtube.com/watch?v=u9qPZQczuPI) released by ASUSTOR to correctly disassemble the unit and replace/upgrade the RAM and add an internal SSD
- Follow the [video guide](https://www.youtube.com/watch?v=q5y9BDkwHmQ) by the YouTube channel NASCompares to walkthrough the software install, using TrueNAS Scale instead of Core (not by choice; Core wouldn't install; related to drivers for the NIC)

Thanks to those who got me here!

## {{< youtube id="u9qPZQczuPI" title="Upgrade RAM with ASUSTOR" >}}

## {{< youtube id="q5y9BDkwHmQ" title="Installing TrueNAS Scale with NASCompares" >}}

