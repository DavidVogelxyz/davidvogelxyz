---
title: "Network Administration"
---

{{< menu >}}

# ![Network](/images/network.gif)

In the way that is true for most regular people, I have been administerting my own home networks for years. That is to say, I was given a box by my Internet Service Provider (ISP) and I let it run in my home so I would have internet. Every once in a while, I would sign in to 192.168.1.1 to adjust some settings for a video game or something, but that was about it.

Because of the [home lab projects](/home-lab) I began working on in 2020, I started to become more aware of the potential attack surface of a poorly configured router. By the start of 2022, I had acquired what seemed to be a good router from Netgear, with more antenna (6) than I had ever seen on a router (2). What I did with that Netgear router wasn't impressive (setting up a guest network & some static IP addresses, etc), as Netgear's web UI was incredibly slow, but it did give me exposure. For example, when it came time to do some port forwarding and set up a NAT firewall rule to allow my first [OpenVPN server](/home-lab/network/openvpn-raspberry-pi) through, I had to work with the Netgear web UI.

I received my CompTIA Security+ in April 2023. I then set my sights on the CompTIA Network+, which I received in May 2023. While I was studying for the Network+, I decided that it was time to upgrade my router and build my home network from scratch, as a testament to my grasp of the material. So, brought in a [PfSense](/home-lab/network/pfsense) router installed on bare metal. At about the same time, I put together a [travel router](/home-lab/network/travel-router) from a Raspberry Pi and an install of OpenWrt. The travel router would allow me to connect back to my home network from anywhere, always through an encrypted tunnel, with a kill switch if that VPN connection was ever severed! So cool.

---

{{< articles-section >}}
