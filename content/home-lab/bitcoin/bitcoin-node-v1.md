---
title: "Bitcoin Node Version 1"
date: 2021-02-18T21:26:15-04:00
tags: ['home-lab','bitcoin']
---

{{< context >}}

## Running my first home lab project

My first home lab project was a Bitcoin node.

This was back in the spring of 2020, during the coronavirus lockdown times. I knew nothing of building home labs at the time. I really knew nothing at all besides Windows, and a little bit of Mac OS. The first iteration of my Bitcoin node was nothing more than a Dell laptop running Windows 10 with Bitcoin Core GUI running on top of that. It was simple, and it allowed me to connect my Wasabi Wallet software to it. But, the more I learned about Bitcoin nodes, the more I understood that the next step was for me to harness the power of the command line. To do that, I would need to install Linux.

I ran Linux for the first time in the winter of 2020. I wasn't ready for the full command line experience, so I installed Ubuntu Desktop onto a laptop and ran the Bitcoin Core GUI. On the surface, all I had done was import my Windows experience onto Linux. This was mostly true. My use with Linux was primarily graphical, which meant a lot of clicking through a GUI. But, I was beginning to gain a little experience with pulling up a terminal and entering some commands.

My next move was to free up the laptop and install my node onto a Raspberry Pi. At the start (January 2021), I continued to use Ubuntu Desktop, same as before. But, I started to train new skills such as:
- doing software integrity checks using GPG
- performing full disk encryption
- networking services through the Tor network
- writing service files to run software at startup
- installing new software and connecting it to other self-hosted services

As I did, I also noticed how cumbersome my setup was. On the occassions that I wanted to check in on my server, I had to put together a complete monitor-keyboard-mouse setup that I would be putting away at the end of the check-in. In addition, I was also becoming painfully aware of how slow the Raspberry Pi was, because I demanded a graphical interface.

So, for [Version 2](/home-lab/bitcoin/bitcoin-node-v2), I decided to go completely headless. My server, that is.

[![btc-rpc-explorer](/images/btc-rpc-explorer.png "btc-rpc-explorer Dashboard")](/images/btc-rpc-explorer.png)

*An image of the dashboard of the web UI for the btc-rpc-explorer (Version 1.2 era). This is an image from the public version of the website, which can be accessed using [this link](https://bitcoinexplorer.org/).*

---

## The Build

### Version 1.0 - Windows 10 (laptop; spring 2020)

- Windows 10
    - Tor daemon
- Bitcoin Core (GUI)

### Version 1.1 - Ubuntu Desktop (laptop; winter 2020)

- Ubuntu Desktop 20.04 LTS (x86)
    - Tor daemon
- Bitcoin Core (GUI)
- Specter Wallet (Server)
- btc-rpc-explorer

### Version 1.2 - Ubuntu Desktop (Raspberry Pi 4, 8GB; early 2021)

- Ubuntu Desktop 20.04 LTS (arm64)
    - Tor daemon
- Bitcoin Core (GUI)
- Specter Wallet (Server)
- btc-rpc-explorer

---

## Fresh Install Bullet Points

This version, and all of its subversions, have been retired in favor of a more recent version. Check [this page](/home-lab/bitcoin/) for the most up-to-date version of the Bitcoin node stack.

Thanks to those who got me here!

- [This forum post](https://askubuntu.com/questions/1287837/luks-disk-encryption-on-raspberry-pi-4-and-ubuntu-desktop-20-10) for explaining how to do full disk encryption on a Raspberry Pi
- [Ketan](https://k3tan.com) & Ministry of Nodes for [this YouTube playlist](https://www.youtube.com/playlist?list=PLCRbH-IWlcW290O0N0lQV6efxuCA5Ja8c)

---

## Helpful Videos

## {{< youtube id="gT1izYKvhBw?list=PLCRbH-IWlcW290O0N0lQV6efxuCA5Ja8c" title="Node Box Guide by Ministry of Nodes" >}}
