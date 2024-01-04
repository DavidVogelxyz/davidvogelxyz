---
title: "OpenVPN Servers Using Cloud Service Providers"
date: 2022-12-16T22:46:08-04:00
tags: ['home-lab','network']
---

{{< context >}}

## Advantages to using other people's computers

At the end of 2022, I revisited VPNs. My Raspberry Pi VPN was doing a great job with allowing me remote access to my home network, but my public IP was always my own. Why did I want a different IP? So I could give my phone a VPN connection when using the internet, to reduce the amount of data I leak, and to try and control what does leak. That way, web apps, like social media apps, would believe I live in a different part of the US. I would get reminders to vote for states I didn't live in. It felt good to push back a bit against all the unrequested, unwanted, permissionless corporate data collection.

Therefore, I sought out cloud service providers (CSP) such as Vultr and Linode for access to cheap and easy-to-use computing platforms. I didn't know it at the time, but those infrastructure-as-a-service platforms were being offered because of [virtualization](/home-lab/virtualization). Virtualization made it easy to spin up a Debian machine, secure it, and then run the [OpenVPN installation script](https://github.com/angristan/openvpn-install) by Angristan. Because of how easy and cheap it was, I actually showed others how to set up their own VPN servers, in order to have alternatives to the well-known VPN service providers. It didn't make sense to run projects I've already run using CSPs; but, I was excited to have them as another tool in my toolbox.

**INSERT FROM THE FUTURE:** I used [Amazon Web Services (AWS) to run an OpenVPN server](/home-lab/network/openvpn-aws). For many reasons that are detailed on that post, it was a terrible experience compared to using CSPs such as Vultr and Linode (and others like them). AWS is unnecessarily convoluted with terms, the web UI is slow, and it felt weirdly neutered (and not in a way that made it simpler).

[![Vultr - Dashboard](/images/cloud-dashboard.png "Vultr - Dashboard")](/images/cloud-dashboard.png)

*An image of a cloud service provider web dashboard showing two active servers; one for OpenVPN, and one for Hugo.*

---

## The Build

### Version 1.1 - Cloud server deployment (winter 2022)

- Debian 11 (Bullseye)
    - UFW
    - fail2ban
- OpenVPN
- Nala (wrapper for `apt`)

This build lacked much that was noteworthy. Vultr and Linode (and other CSPs like them) made it really easy to spin up a VM with a pre-installed OS, and using Debian meant that I could use the most up-to-date OS installer without casuing the script to break. It was simple and reliable. It simply worked.

The only thing of note was `nala`. It was around this time that I learned of `nala`, a wrapper for `apt` that made package management feel more like `pacman` while on Debian-based systems. It's noteworthy because, it made Debian (and by extension, Ubuntu) fun again. It was enjoyable to SSH into a server running Debian/Ubuntu and to do regular updates, if it meant getting to watch `nala` render the output. It almost made me want to start migrating back to Debian-based systems...

---

## Fresh Install Bullet Points

Here’s how I would rebuild my VPN server if I needed to:

- Go to my personal GitHub and reference my guide on:
    - [Security Hardening on Artix Linux](https://github.com/DavidVogelxyz/library/blob/main/security/secure-arch.md)
- Use [Angristan's script](https://github.com/angristan/openvpn-install) to build the VPN server and configuration file

Thanks to those who got me here!

- Angristan for his [script](https://github.com/angristan/openvpn-install)
- Mental Outlaw for his [video about creating an OpenVPN server](https://odysee.com/@AlphaNerd:8/how-to-create-your-own-vpn-(and-why)) ([YouTube link](https://www.youtube.com/watch?v=Lk_v6Q0YsNo))

## {{< youtube id="Lk_v6Q0YsNo" title="How to Create a VPN Server with Mental Outlaw" >}}

