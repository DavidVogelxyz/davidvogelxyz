---
title: "Bitcoin Node Version 3"
date: 2022-11-11T15:58:03-04:00
tags: ['home-lab','bitcoin']
---

{{< context >}}

![Arch banner](/images/arch-banner.png)

## Introduction

This article describes an outdated way to build a Bitcoin node. For more information on how I would set up a Bitcoin node today, check out [my guide on creating a Bitcoin node](https://github.com/DavidVogelxyz/library/blob/master/servers/bitcoin-node-on-debian.md), found on my GitHub.

---

## Leveling Up My Bitcoin Node Even Further

By the end of 2022, I had been running the [Bitcoin Node Version 2.1](/home-lab/bitcoin/bitcoin-node-v2#the-build) for about a year. It had been running incredibly robustly since I brought it online, and especially after upgrading it to Ubuntu 22.04 LTS in May 2022. But, it also gave off a sense of staleness. I had thought about testing out some potential upgrades, and the end of the year provided the time. And, it was the perfect time, because it was just about the **two year anniversary** since I started running Ubuntu Linux servers.

I upgraded the Bitcoin node in a big way. I upgraded the hardware to a badass mini laptop meant for gaming; except, instead, I threw a 1TB SSD inside and made it into a portable powerhouse. I also moved away from Ubuntu, right past Debian, and installed Arch Linux. Why not? Then, on top of Arch, I installed a more powerful indexer, Fulcrum, that was going to make my Mempool explorer quicker and my wallet sync even faster. Finally, I added a web UI dashboard, so I can keep track of my home lab web links for later.

The upgrade had its challenges. There were issues with networking and with nginx, and there were some issues that had to do with differences between Debian-based systems and Arch-based ones. Some packages had extra installation steps that I was unaware of. It was not easy.

But, as I perservered through each problem, I became better at troubleshooting issues. I learned more about Linux and about how different softwares interact with each other. I practiced finding my own answers, instead of being able to ask someone for help. It was a struggle, but I came out a better Linux user because of it.

The Version 3 era is also where I really developed a love for building servers. The emptiness of my Homer web dashboard was an invitation to deploy more services and create as many buttons as possible. I also developed an interest in writing scripts so that I could quickly re-deploy my installs instead of copy-pasting commands again and again. That would allow me to build a foundation of knowledge and skill, such that I could reiterate the base layer far more quickly, and spend more time working on new additions to my home lab.

---

## The Build

### Version 3.0 (fall 2022)

- Arch Linux (x86)
    - UFW
    - fail2ban
    - nginx
    - Tor daemon
- Bitcoin Core (daemon)
- Fulcrum (indexer)
- Mempool (timechain explorer)
    - MariaDB
- Homer web dashboard

Some key notes about upgrading to Version 3.0:

1. Getting networking at the beginning of the setup process takes a bit more work.
1. Ubuntu has a user named 'www-data'; on Arch, this user is named 'http'. In addition, the Arch directory is located at '/srv/http', rather than whatever Ubuntu is. This took me a while to figure out, and I was not able to get Mempool nor NGINX working until I did.
1. Some of the directories for NGINX needs to be manually added. Not sure why, but a quick `mkdir` fixes this.
1. Some of the package names are different.
1. Installing MariaDB has additional steps.
1. In addition, when installing Mempool, certain files need to be redirected to point to the right direction or use the right user.

While it runs `systemd` just like the Version 2 era Ubuntu servers, it boots incredibly fast. I believe it has something to do with how the full disk encryption was set up, because the Version 2 Ubuntu servers all boot much slower than the Version 3 Arch servers.

Another difference between the two Version eras is the encryption passphrase entry at startup. Ubuntu was far slower to process the entry, and would only allow one entry before forcing the user to shutdown and restart to attempt the unlock again. In contrast, the Version 3 Arch servers process entries very quickly and allow multiple attempts.

Fulcrum was also a massive success at speeding up the wallet lookups. Everything became near instant, especially on the local network, which I now was addicted to using. With the power of the VPNs, I could always use this fast connection to use my wallets and check on transactions using the Mempool explorer. Life's good.

---

## Fresh Install Bullet Points

Here’s how I would rebuild my Bitcoin node if I needed to:

- Go to my personal GitHub and reference my guides on:
    - [Installing Arch Linux](https://github.com/DavidVogelxyz/library/blob/master/install-os/install-arch.md)
    - [Security Hardening on Arch Linux](https://github.com/DavidVogelxyz/library/blob/master/security/secure-arch.md)

Thanks to those who got me here!

- Stadicus again for his [Raspibolt guide series](https://raspibolt.org/)
- I learned how to install Arch (and Artix) Linux with assistance from:
    - the [Arch wiki](https://wiki.archlinux.org)
    - this [video guide](https://videos.lukesmith.xyz/w/n1cMQYYzwPoegM2oXfz2iC) by Luke Smith ([YouTube link](https://www.youtube.com/watch?v=dI3bGeT31Bo))

---

## Helpful Videos

## {{< youtube id="dI3bGeT31Bo" title="Installing Arch Linux with Luke Smith" >}}
