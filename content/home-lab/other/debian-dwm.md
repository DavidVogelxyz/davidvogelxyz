---
title: "Debian DWM: Like LARBS, But Not Exactly"
date: 2023-08-23T22:24:38-04:00
tags: ['home-lab','other']
---

{{< context >}}

![LARBS banner](/images/larbs-banner.png)

## Introductory Notes

This article tells the story of how I created my first true Git project, [`debian-dwm`](https://github.com/davidvogelxyz/debian-dwm) -- this project can be accessed by following the link to my GitHub. If you want to learn more about how I install Debian onto new computers and VMs prior to using `debian-dwm`, check out [my guide on installing Debian](https://github.com/davidvogelxyz/library/blob/master/install-os/install-debian.md)!

## My First Real Git Project

`debian-dwm` is a project I have been working on since late July 2023, though it really only took shape in late August 2023. I had been using LARBS on my Artix desktop for about 6 months, so much so that I was loathe to use any other desktop solution. While KDE is definitely my favorite desktop environment for Linux, I vastly prefer the flexibility of a window manager like DWM. However, LARBS is written for Arch-based distros, such as Artix Linux. There was no easy way to deploy a similar build of DWM onto a Debian machine. So, I decided to make it myself.

I didn't directly copy Luke Smith's LARBS for a handful of reasons. The primary one was that my Bash knowledge wasn't where it needed to be -- I had no idea what Luke was doing with portions of his script. For example, the way that he was using Bash to pass arguments into functions that he had written completely baffled me at the time. But, another reason was that there were some things that I wanted the script to do, that Luke's script didn't do. A great example of this was the ability for the script, were it to fail, to be able to pick up from some sort of "milestone marker", rather than starting again from the beginning. I saw this as a great opportunity to push myself to learn more, to build something myself that would be heavily inspired by, but not a carbon copy of, someone else's work.

### "We All Start Somewhere"

The first iteration of `debian-dwm` was completed by early August. At that point, it was genuinely just a list of commands that would run in succession. There was honestly nothing special about my script, ***except*** for the fact that it would work on a Debian system. I actually used this first iteration to create the VM that I would use to complete the "Starting Points" section of [HackTheBox](/home-lab/other/hackthebox). I even used a version of these scripts to get DWM working on [NixOS](/home-lab/other/nixos) because I refused to make use of `home-manager`. While the script wasn't anything special, it did what it needed to do: it installed Luke Smith's DWM onto a Debian system. However, I was already beginning to implement my own additions to the script. The primary example of this was creating a way to have those "milestone markers": thus, my idea of "modules" was born.

Simply put, I had no idea how to have the installer be able to "pick up where it left off." I hadn't been introduced to Ansible at the time, so I was struggling to find a way to make my main script be able to know what part of the install it was on. So, I came up with my way of doing it.

I broke the script up into smaller modules. The key was that every module that was going to get forked into an external shell would be preceeded by a logical operator that checked to see if the module file existed. If it didn't exist, it would simply move onto to the next module. If the module completed successfully, it would move that module into a separate directory, so that it wouldn't exist the next time the main script was run. And, if the module failed, it would leave the file in place, so that the main script would start from there if run again. It would also print a message to user, telling them exactly which script failed. Though it wasn't particularly elegant, it worked as a first implementation.

### Improving My Work

However, once I completed thePrimeagen's [Data Structures and Algorithms course](/home-lab/other/theprimeagen-dsa-course), I decided to revisit `debian-dwm` and make it better. Armed with my [Kinesis keyboard](/home-lab/other/kinesis) and a [better understanding of Git](/home-lab/other/git), I knew it was time to start applying what I had learned. One of the first things I learned how to do was to create a loop to run my modules, rather than a bunch of sequential commands. Again, in retrospect, it wasn't anything special, but it was yet another example of visible improvement. I also learned how to utilize variables in conjunction with my loop -- this meant that I could retain control of what order the loop ran the modules in by listing the modules in the order I wanted them to run. In addition, I leveraged the tools at my disposal by using my Proxmox server to test my code: by creating a standardized VM that I could clone for testing, I was able to rapidly test changes I made before uploading new commits to GitHub. At a much faster pace than before, I was able to write, test, and then implement improvements to my code.

Because I was now leveraging Git in more intelligent ways, I also no longer had to worry about finding a way to achieve proper version control. Instead of having a bunch of nearly identical directories, differentiated only by timestamps, I now had the ability to keep all that data in one repository. If I ever needed to look back a previous version, it was as easy as checking a previous commit. In addition, Git and GitHub allowed me to have a central repository for these scripts. Cloning down the repository was far easier than going through the hassle of using `scp` or `rsync` to get the scripts onto new VMs. For a first project, I really felt like I was working efficiently and utilizing all my tools in an effective way.

While I started August 2023 with a mess of repositories on my computer, with only slightly different changes between them, I ended August 2023 with a single, awesome repo that *I* wrote, containing a LARBS-inspired installer uploaded to GitHub. Now, whenever I want to create a new computer with DWM on it, I can use either LARBS or `debian-dwm` to quickly and effortlessly perform the install. I would continue to work on this project over the coming months, refining it further. But, for now, my attention had turned to something else: my [Neovim configuration files](/home-lab/other/neovim).
