---
title: "Bitcoin Node Version 2"
date: 2021-12-18T21:26:15-04:00
tags: ['home-lab','bitcoin']
---

{{< context >}}

## Introduction

This article describes an outdated way to build a Bitcoin node. For more information on how I would set up a Bitcoin node today, check out [my guide on creating a Bitcoin node](https://github.com/DavidVogelxyz/library/blob/master/servers/bitcoin-node-on-debian.md), found on my GitHub.

---

## Going Down the Rabbit Hole of Headless Servers

My first home lab project was about to level up in a big way.

My first experience with a headless server was in the spring of 2021. I reinitialized my Raspberry Pi with Ubuntu Server and I forced myself to set up a node from scratch using only the command line. With some help and assistance and some guide videos, I made it happen. Skills I had just learned continued to develop:

- software integrity checks using GPG
- full disk encryption
- networking through the Tor network
- writing service files
- connecting new software to other self-hosted services

I also gained some new skills and abilities. Those included learning how to SSH, in addition to learning how to SSH securely by securing `sshd` using public/private key pairs. I learned how to troubleshoot multiple Raspberry Pi servers and maintain maximum uptime and high availability. I also combined SSH with a previous skill, Tor networking, in order to expose a Tor hidden service so I could remotely administer a server without exposing my home IP address. It was slow, but it was private and it was encrypted. It was also really cool.

The high achievement of the Version 2 era was the end of 2021, when I upgraded the entire headless software stack to include the block indexer. Suddenly, my node was supercharged. It powered stronger wallet software and a more aesthetically pleasing (yet incredibly useful) web-based timechain explorer. It also had better security with a firewall and software to limit the potential for DDoS attacks by banning spam attacks. That's pretty cool.

The best part was that, in just a year, I had managed to go from running my node on Windows 10 (LOL) to running my node on Linux, with just a command line. So freaking awesome.

This new node was so good that it basically ran uninterrupted from the end of 2021 until the end of 2022, when it was upgraded to the new [Version 3](/home-lab/bitcoin/bitcoin-node-v3).


[![Mempool - Dashboard](/images/mempool-dashboard.png "Mempool - Dashboard")](/images/mempool-dashboard.png)

*An image of the home page of the web UI for the Mempool explorer, added to the Bitcoin node stack in Version 2.1. A public version of the website can be found at [mempool.space](https://mempool.space).*

---

## The Build

### Version 2.0 (spring 2021)

- Ubuntu Server 20.04 LTS (arm64)
    - Tor daemon
- Bitcoin Core (daemon)
- Specter Wallet (Server)
- btc-rpc-explorer

### Version 2.1 (winter 2021)

- Ubuntu Server 22.04 LTS (arm64)
    - UFW
    - fail2ban
    - nginx
    - Tor daemon
- Bitcoin Core (daemon)
- Electrs (indexer)
- Mempool (timechain explorer)
    - MariaDB

To address a potential discrepancy, Version 2.1 ran Ubuntu 20.04 LTS until spring 2022, when Ubuntu 22.04 LTS was released. Since Version 2.1 ran 22.04 for the majority of its life, it is listed as such.

*NB: Around this time, I also learned that Ubuntu Desktop can be made into Ubuntu Server by setting the `systemd` boot to be `multi-user` and not `graphical`. To go further, the desktop environment can be uninstalled, as well as the `snap` related packages and any other Ubuntu bloat.*

---

## Fresh Install Bullet Points

This version, and all of its subversions, have been retired in favor of a more recent version. Check [this page](/home-lab/bitcoin/) for the most up-to-date version of the Bitcoin node stack.

Thanks to those who got me here!

- Tj for his [guide to "Full Disk Encryption on Ubuntu"](https://help.ubuntu.com/community/Full_Disk_Encryption_Howto_2019)
- Stadicus for his [Raspibolt guide series](https://raspibolt.org/)
