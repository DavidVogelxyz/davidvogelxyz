---
title: "Travel Router - Raspberry Pi Running OpenWrt"
date: 2023-05-01T22:58:45-04:00
tags: ['home-lab','network']
---

{{< context >}}

![OpenWrt banner](/images/openwrt-banner.png)

## Secure VPN Internet On-the-Go

I successfully built multiple travel routers, each one using nothing more than a Raspberry Pi, an external USB wireless adapter, and a connection to a remote OpenVPN server.

But why do this? Two main reasons:

1.  Home lab access no matter where I am
1.  Secure internet access when outside the home

If I'm not using my home network, I'm using someone else's network. Now that I have an awesome home lab, that's not okay. So I built my travel router with a connection back to my [home OpenVPN server](/home-lab/network/openvpn-raspberry-pi) so that I always have access to my home's local network. Access that, for example, allows my laptops to connect to my [Proxmox VM server](/home-lab/virtualization/proxmox), and therefore my [Docker containers](/home-lab/virtualization/docker), at all times. Or, I can pull a file off of my [network attached storage (NAS)](/home-lab/services/truenas) anywhere I go. It means that, no matter where I am, I always look like I'm using the internet from the comfort of my home. Sometimes, that's exactly what I want.

An added benefit to this "everywhere-I-go" home network access is that the VPN tunnel protects my traffic from a potentially compromised network connection. Whether it's rogue users or a rogue network administrator, using other networks confers a level of risk that the traffic sent over the network will be sniffed. Even with HTTPS and SSL, there's tons of metadata that can be gathered from any traffic going over the network. If the traffic is instead being routed through an encrypted tunnel until it reaches the VPN server, it would be entirely unreadable. So, the travel router adds a security benefit as well.

Another plus of the travel router is its convenience. Normally, any device that wanted to connect to the VPN would need VPN software and a configuration file. Instead of needing to do that, I simply connect the device to a specific wireless network hosted by the travel router, and the device is automatically connected to the internet through the VPN. The travel router is also configured to have a "VPN kill switch," so that the router cuts the internet anytime the VPN connection is lost. This ensures that any traffic leaving the router is on its way to the home OpenVPN server) and, therefore, encrypted.

Yet another benefit to building the travel routers was that I was actively pursuing my CompTIA Network+ certification at the time, and the travel routers were a practical home lab project for someone studying for a networking exam. While I followed guides for most of the initial setup, I had a strong understanding of what I was doing because I was solidifying the material I was learning for my certification.

[![Travel Router Web UI Dashboard](/images/travel-router-dashboard.png "Travel Router Web UI Dashboard")](/images/travel-router-dashboard.png)

*An image of the travel router's web UI dashboard.*

---

## The Build

### Hardware:

- Raspberry Pi 4, 8GB RAM
- External USB wireless antenna
    - MediaTek 7601u chipset

### Software:

- OpenWrt
- OpenVPN
- `mt7601u-firmware` driver

As is posted on my GitHub, my particular pair of antenna and driver no longer installs correctly, as the 2023 May 15 update to the `mt7601u-firmware` driver package broke the compatibility. I now build new travel routers by using a backup image I created from a currently working travel router.

---

## Fresh Install Bullet Points

Here’s how I would rebuild my travel router if I needed to:

- Go to my personal GitHub and reference my guide on:
    - [Setting up travel routers](https://github.com/DavidVogelxyz/library/blob/master/network/install-openwrt-travelrouter.md)

To give credit to those who got me here:

- [NetworkChuck Raspberry Pi Travel Router video](https://www.youtube.com/watch?v=jlHWnKVpygw)
- [OpenWrt guide to OpenVPN client using LuCI](https://openwrt.org/docs/guide-user/services/vpn/openvpn/client-luci) specifically for help with the VPN kill-switch

---

## Helpful Videos

## {{< youtube id="jlHWnKVpygw" title="NetworkChuck Raspberry Pi Travel Router video" >}}
