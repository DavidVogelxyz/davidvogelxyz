---
title: "pfSense on a Protectli Router"
date: 2023-05-04T22:56:48-04:00
tags: ['home-lab','network']
---

{{< context >}}

![pfSense banner](/images/pfsense-banner.png)

# Building a Home Network from Scratch

I was working my way through the CompTIA Network+ certification, and had just finished the travel router project, when I decided it was time to upgrade my home network setup. I had previously been using a Netgear device that served as both the router and the access point (AP) for my network. However, various issues, including a slow web UI and an inability to do VLANs properly, made it clear that it needed to be replaced at some point. I decided to take a small break from studying -- May 2023 was now that moment.

I set up a Protectli router running pfSense. And, the process was relatively painlessly, the first time around. I followed a guide (link below) and set up a basic home network, with some custom firewall rules and NAT permissions for my OpenVPN server. I did have to overcome the hurdle of bridging some physical interfaces so I could have additional LAN ports. But, it felt like the issues I was experiencing made sense, and so did the solutions. After getting the network to a stable, working place; I resumed my studying for my upcoming exam. Afterwards, though, it was time for VLANs!

A couple of weeks later, I revisited the router in order to implement those VLANs. Even though I passed my exam, and received my CompTIA Network+ certification, I was not prepared for the weekend of obstacles that I endured. I spent far too many hours of a full weekend troubleshooting. While that was painful, I also gained a ton of experience that studying for the Network+ had not given me. Before, I could correctly answer exam questions about VLANs. Now, I understand them so well that I can set them up even if some of the hardware isn't playing nice.

Surprisingly, I feel rewarded for the time I spent fixing my home network. I received extremely valuable hands-on knowledge that I'm confident will be useful in the future. I became really comfortable with pfSense too. I can follow someone's guide and configure a network, but I can also say that I know how to deviate from that guide, as is needed, in order to build a custom network that suits my needs. And, that's another thing: I got a really secure home network out of it, one that I set up myself. That's really awesome.

[![pfSense - Firewall](/images/pfsense-firewall.png "pfSense - Firewall")](/images/pfsense-firewall.png)

*An image of the firewall rules for the LAN interface on my pfSense router.*

---

# The Build

### Hardware

- Protectli

### Software

- pfSense

### Old hardware

I was able to make use of all of my old hardware. The managed switches I had stayed where they were, and the old Netgear router was demoted to just being an access point (AP). This allowed me to extend the wireless coverage to more areas of my home that needed it, since the office area was entirely wired connections.

---

## Takeaways

Even though I followed a guide throughout the process, having a good understanding of networking basics was extremely helpful as I set up my pfSense router.

### Bridging

The Protectli router that I have doesn't have a bunch of LAN connections in the way I was use to. It has one LAN port, and an OPT1 and an OPT2 port (short for *optional*). In order to make use of the OPT1 port as another LAN port, I had to set up a bridge between the interfaces. That required setting up a new interface between the two, adjusting some settings, and then adding in some firewall rules to allow LAN traffic to talk to anyone. Figuring this out took a mix of searching the right keywords and knowing how to correctly implement the forum post solution I had found.

### Firewall

pfSense makes it easy to set firewall rules on a per interface basis. That meant firewall rules for LAN, OPT1, their bridge, and any VLANs I created (and any bridges they needed). While that felt like a lot of work, my solution was building a spreadsheet of rules and working from there. The table allowed me visual clarity into the differences between the VLANs, based on their firewall rules. Then, I copied over to all of them the default *block* and *allow ping* rules. Soon enough, I had a complete set of firewall rules for all of my VLANs and other network interfaces. Then, all I had to do was test them.

### VLANs

Learning VLANs was painful. The pain had little to do with pfSense or Protectli, a fair amount to do with these being my first VLANs, and a lot to do with issues with my switches and wireless access point. But, through this pain, I learned how to set up VLANs, and that's awesome.

My first issue was a combination of my inexperience with VLANs and the switches' (TP-Link) software. Figuring out the correct way to interact with their software took many trials and errors, and a few factory resets for the switches. Some of this was due to the requirement that the PVID also needed to be set in order for the port to *actually* be tagged. Some of my issues were also due to my interest in putting the switch onto a management VLAN. Eventually, I figured out how to get the VLAN traffic flowing.

The other issue arose at this point, and related to the Netgear wireless access point. When I first implemented the pfSense router, I changed the Netgear device to `access point` mode, over from `router` mode. In doing so, a software configuration happened that removed the device's ability to process VLAN tags -- essentially making the Netgear a "dumb switch." This meant that the AP's IP address would have to reside within the same VLAN it was propogating. Naturally, this also conflicted with my attempts to set up a management VLAN. Solutions were arrived at, as they always are, but I spent a good while thinking that I had misconfigured the VLANs on the pfSense side.

There was also the small thing with bridging VLANs in order to get VLAN traffic from the VLAN interfaces on the LAN port to the VLAN interfaces on the OPT1 port. Not getting it right (ex. bridging a VLAN to its parent interface) would cause loops and bring the network down. That was a fun learning experience too.

### OpenVPN

### WireGuard (coming soon)

---

## Fresh Install Bullet Points

- Follow [the guide](https://nguvu.org/pfsense/pfsense-baseline-setup) that I originally found for setting up a pfSense router
- [Message board post](https://linustechtips.com/topic/753059-how-do-i-configure-opt1-and-opt2-as-additional-lan-on-pfsense) from Linus Tech Tips about bridging OPT1 with LAN
- [YouTube video](https://www.youtube.com/watch?v=5ohLAFHnOHg&t=855) from Tom Lawrence at Lawrence Systems on YouTube describing how to tag the VLANs correctly on TP-Link switches
- [YouTube video](https://www.youtube.com/watch?v=I61t7aoGC2Q) from Tom at Lawrence Systems about OpenVPN on pfSense

---

## Helpful Videos

## {{< youtube id="5ohLAFHnOHg?start=855" title="Tagging VLANs correctly on TP-Link switches with Lawrence Systems" >}}

## {{< youtube id="I61t7aoGC2Q" title="OpenVPN on pfSense with Lawrence Systems" >}}
