---
title: "OpenVPN Server on a Raspberry Pi"
date: 2022-05-23T22:46:08-04:00
tags: ['home-lab','network']
---

{{< context >}}

![OpenVPN banner](/images/openvpn-banner.png)

## VPNs done right

Most people don't understand VPNs. This is mostly due to effective marketing by companies selling VPN services. People believe VPNs are far more than they actually are. But, VPN still have utility, if applied correctly.

The one and only utility that a VPN provides is the ability to relocate the point where one's local traffic becomes wider internet traffic. Put simply, VPN servers allows an individual to change their public IP address. Uses for this include remotely accessing private networks, such as a corporate or home network, or pretending to be somewhere else to get a different country's streaming service catalog. For this purpose, a VPN service with access to servers in different countries may have use.

VPNs are claimed to be secure because of the **encryption** provided by the VPN tunell. Because traffic leaves the client computer and transits over to the "external local network" using an encrypted tunnel, the client's ISP no longer has "provider-level access" to the client data. But, that access doesn't go away -- the control is simply transferred over to the ISP of the VPN server. This is one big caveat to the marketing reads of the VPN service companies regarding security.

With this in mind, in the spring of 2022, I used another Raspberry Pi to deploy an OpenVPN server. I was deploying the server simply to gain remote access to my home network using an encrypted connection. Nothing more, nothing less.


The OpenVPN Pi server was awesome. It was one of my most stable server projects, achieving a >99% uptime for the 6 months that it ran. I tested it from across the world and I was always able to connect, no matter what. And, it was much faster than the hidden services I had been routing through the Tor onion network. The OpenVPN Raspberry Pi project was also the first to open my eyes to networking. While I had been communicating with my Bitcoin and camera servers over the local network and over Tor, being able to set up a Raspberry Pi to enable full network access from anywhere across the world, with minimal latency, was incredibly cool.

---

## The Build

### Version 1.0 - Raspberry Pi 4, 8GB (spring 2022)

- Ubuntu Server 20.04 LTS (arm64)
    - UFW
    - fail2ban
- OpenVPN

Regarding operating systems, it is worth noting that Ubuntu 22.04 LTS (Jammy Jellyfish) had already released by the time I started this project. However, due to issues of package dependencies and wanting different version, I was unable to get Ubuntu 22.04 working with the [script](https://github.com/angristan/openvpn-install) I was using to install the OpenVPN server. I had to downgrade to Ubuntu 20.04 (Focal Fossa) in order to get everything working.

It is also worth noting that current Debian systems seems to work fine as well -- it is *only* Ubuntu, and *only* versions 22.04 and above, that have the issues with the script.

---

## Fresh Install Bullet Points

**NB: The Raspberry Pi OpenVPN server was the first way I learned to set up a VPN server, but it is only one of many ways. From spinning up a [Docker container](/home-lab/virtualization/docker) or a [Proxmox VM](/home-lab/virtualization/proxmox), to running the server on the cloud (with [Linode](/home-lab/network/openvpn-cloud), not [AWS](/home-lab/network/openvpn-aws)), to running the VPN server directly on a [pfSense router](/home-lab/network/pfsense), there are so many options to choose from. Building another Raspberry Pi VPN server would be driven almost entirely by circumstance.**

Here’s how I would rebuild my VPN server if I needed to:

- Go to my personal GitHub and reference my guides on:
    - Operating system
        - [Installing Debian](https://github.com/DavidVogelxyz/library/blob/main/install-os/install-debian.md)
        - [Installing Arch Linux](https://github.com/DavidVogelxyz/library/blob/main/install-os/install-arch.md)
    - [Security Hardening on Artix Linux](https://github.com/DavidVogelxyz/library/blob/main/security/secure-arch.md)
- Use [Angristan's script](https://github.com/angristan/openvpn-install) to build the VPN server and configuration file

Thanks to those who got me here!

- Angristan for his [script](https://github.com/angristan/openvpn-install)
- Mental Outlaw for his [video about creating an OpenVPN server](https://odysee.com/@AlphaNerd:8/how-to-create-your-own-vpn-(and-why)) ([YouTube link](https://www.youtube.com/watch?v=Lk_v6Q0YsNo))

## {{< youtube id="Lk_v6Q0YsNo" title="How to Create a VPN Server with Mental Outlaw" >}}

