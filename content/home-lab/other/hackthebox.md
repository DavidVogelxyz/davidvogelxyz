---
title: "HackTheBox: Learning Penetration Testing"
date: 2023-08-11T22:24:38-04:00
tags: ['home-lab','other']
---

{{< context >}}

![HackTheBox banner](/images/hackthebox-banner.png)

## Hacking the Box (ethically, of course)

Throughout the summer of 2023, I was working on improving my Linux and IT skills. I had built a [webpage and e-mail server](/home-lab/services/web-server), deployed a [Nextcloud instance using Docker](/home-lab/services/nextcloud-docker), and even messed around with [NixOS](/home-lab/other/nixos). I was putting hours of my day, every day, into this process. While this was a fun and engaging process, I also sought out downtime here and there. But, I also wanted my downtime to at least be "somewhat productive."

I settled on finding a "hacking game" to play -- something that would help me learn about the Linux command line interface (CLI), while also being fun. I found a few games, including [Shenzhen I/O](https://store.steampowered.com/app/504210/SHENZHEN_IO/) and [Hacknet](https://store.steampowered.com/app/365450/Hacknet/). While playing through the first hour of Hacknet, I realized that it was *at best* a facsimile of the actual CLI experience; it wasn't going to teach me much, but it was going to approximate the experience. But, I thought, "why play a game on a pseudo-Linux CLI when I could learn stuff that actually uses the Linux CLI?"

Around the same time, I watched yet [another NetworkChuck video](https://www.youtube.com/watch?v=uTAaFExLgwQ) or two, where he mentioned a platform called [HackTheBox](https://hackthebox.com). It was exactly what I was looking for. Instead of playing a game that "mimicked" hacking, and wasting valuable time, I could instead divert my attention to something that would provide value to a future career in IT and system administration. Not only would learning basic penetration testing provide value, but it would also develop skills that could translate into the real world. If my future involved "white hat hacking", then I would learn how to penetrate Linux systems; if my future involved cyber-security or system administration, then I would learn what types of attacks were possible, and I could start thinking of ways to better secure servers.

So, I spun up a free HackTheBox account and started my journey. I started with the "Starting Points" section, which claimed that it would teach me the "basics of penetration testing." I learned how to connect to `FTP`, `SMB`, `telnet`, `rsync`, and `RDP` anonymously; used `nmap` to identify open ports, and broke into a MongoDB server. Then, I continued on, and learned how to perform SQL injections, server-side template injection, remote file inclusion, and how to perform attacks using remote SSH shells. I also learned how to use privilege escalation, perform cookie manipulation, brute force passwords with john the ripper, and exploited some LXD containers to gain access to privileged file systems. I was so engrossed with what I was learning, I completed all of the roughly 15 free VM targets in about a day or so -- I started on Thursday afternoon, and had exhausted the free tier by Friday evening.

### Pwning HackTheBox

*As a note: I have since learned a few things about the platform. HackTheBox (HTB) Labs is the part of the website that gives access to the "Starting Points" educational boxes. In addition, a "free user" is usually limited by the 2 hour time limit on the free-to-use "pwnboxes" -- I was able to maximize my use of the free tier by leveraging my Proxmox and VMs.*

Not only did I power through the free tier, but I did so utilizing skills I had been building over the past 6 months. While I could have used the freely provided "pwnbox" VMs, I instead opted to use my own VM through my [Proxmox](/home-lab/virtualization/proxmox) to complete the "Starting Points" course. Where I could have installed "Kali Linux" to a VM, to have all of these hacking tools readily available, I instead opted to use a Debian VM I had created, running `dwm`. This meant that I had to go out and install all of the different packages I needed myself. And, it resulted in me learning more about the tools I would use than I would have if I had them pre-installed on the VM. I remember using `nmap` to query a server's open ports, `hashcat` to crack password hashes, and `tcpdump` to intercept network traffic. While some of the packages were available in the Debian package repos, there were also tools that I could only acquire by cloning down `git` repositories and building the software from source code, something I had rarely done before this point. Going through the HackTheBox course material improved my skills in far more ways than just "penetration testing."

Once I completed the free tier of HackTheBox, I seriously considered shelling out $15 for a month's subscription to gain access to the gated content. While I didn't end up doing this, it was only for a few main reasons.

1. The free VMs that were part of the "Starting Points" course were very structured.
    - While there were more "Starting Points" VMs to hack, I would soon complete those too. Then, I would have access to a myriad of boxes that were far less structured. It would quickly become a test of "use the skills you've learned, and be creative." While there was tons of merit to continuing on, I decided that I wanted to only spend the $15 if I was going to seriously commit to an hour or two of HackTheBox per day, and I wasn't ready to do that.
1. I decided to go down a different path. In late July and early August, I had come across on YouTube a programmer and streamer by the name of "[thePrimeagen](https://www.youtube.com/@ThePrimeagen)". I enjoyed his content greatly, and his videos started to plant a seed in my head - maybe I should consider learning more about coding. In particular, I had discovered that he had a [data structures and algorithms course on Frontend Masters](/home-lab/other/theprimeagen-dsa-course), and that I could access that course for a $15 monthly subscription. Instead of putting the $15 towards HackTheBox, I decided to pursue a Frontend Masters subscription for the time being, with an expectation that I would eventually return to HackTheBox when I was done.

---

## Helpful Videos

## {{< youtube id="uTAaFExLgwQ" title="the hacker’s roadmap (how to get started in IT in 2023)" >}}

## {{< youtube id="4CJMpZfK1rI" title="hack the box" >}}
