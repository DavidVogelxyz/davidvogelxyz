---
title: "NixOS: Declarative Configuration Systems"
date: 2023-07-11T22:24:38-04:00
tags: ['home-lab','other']
---

{{< context >}}

![NixOS banner](/images/nixos-banner.png)

## Running NixOS

After getting my [website and e-mail server](/home-lab/services/web-server) set up, and after trying out [Nextcloud through a Docker container](/home-lab/services/nextcloud-docker), I was looking for other ways to expand my Linux knowledge. I had already come to the conclusion that distro-hopping was largely a waste of time. I ran Arch (specifically, Artix) for my main desktop PC, and I used Debian (no longer Ubuntu) for all of my server projects. Beyond this, I felt that other Linux distributions were just "variations on themes" -- a few configurations might be changed here and there, but nothing was ever substantially different. If I wanted to see real variation, I could just install a different desktop environment (DE) onto a Debian or Arch VM and test that out.

However, this all changed when I found out about NixOS, thanks primarily to Chris Titus Tech's videos on his testing of NixOS.

NixOS is a Linux distribution that is more than just its eponymous package manager, Nix. It is an Linux distribution that focuses on state-based configurations, using an immutable design and declarative configuration. In more simple words, it was an operating system that allowed the user to configure the system using one configuration file, and this file would allow a user to deploy a fresh install of NixOS and have a perfect reproduction of another system. This is incredibly cool, and has many utilities when it comes to deploying multiple identical Linux machines.

Specifically, I saw a [Chris Titus video from mid-June 2023](https://www.youtube.com/watch?v=fuWPuJZ9NcU) that discussed the utility of NixOS in a corporate environment, because of Nix's state-based configurations. The last time I had heard that ([Proxmox](/home-lab/virtualization/proxmox)), I jumped on the opportunity to learn and benefitted greatly. Would NixOS be another Proxmox in terms of the value I would derive from it?

I had to find out.

While my stint with NixOS wasn't longer than a few weeks, I was able to successfully configure a fresh "configuration.nix" file that implemented `dwm` as the window manager, as well as my `zsh` config files.

### Beginning to Appreciate Git

One thing I will note is that this was one of the first instances where I began to appreciate the value of `git`, and separately GitHub. Part of the fun of NixOS is being able to completely delete a VM and reinstall NixOS from scratch, while retaining all the progress I made by using a configuration file. However, in order to do that, I would need an easy way to access that configuration file. This is where GitHub began to play a role. GitHub allowed me to upload my configuration file to a publicly hosted repository, which made using `curl` to download that configuration file during install incredibly easy. On top of that, by using `git`, I now had a way to track any changes I made during the process.

Didn't like something that I did? Changing a line broke my system? I could just roll back the changes to a previous commit and keep going as if nothing had happened. This was very useful, and I was only beginning to scratch the surface of that utility.

### The Inception of DWM install scripts

Another note worth mentioning is that, between spinning up a bunch of Debian VMs on my local Proxmox, and now creating a NixOS VM, I was hitting a phase where I was getting tired of doing "the same work over and over again."

Because of my appreciation for how efficiently I was using LARBS on my [desktop](/home-lab/other/desktop), I figured out how to get `dwm` working on Debian, as well as on this NixOS VM, and I wanted to make future deployments simple and quick. So, in combination with beginning to learn about and appreciate `git`, I started working on scripts that I could use to quickly install `dwm` to VMs, without having to manually enter commands. While those adventures will be detailed in a future article, I was beginning to write those preliminary scripts in late July and early August of 2023, and was using them in conjunction with my "configuration.nix" file. This allowed me to use a NixOS VM, test out some new features, tear it down, and then use both my "configuration.nix" file and my `dwm` scripts in order to get everything back in working order. While I could have improved the reproducibility of my NixOS experience by using `home-manager`, I was beginning to get more proficient with different Linux distributions and learning how to troubleshoot issues that would arise.

### Troubleshooting NixOS

My initial attempts at NixOS, and specifically getting `dwm` and `dwmblocks` working correctly, came with a bunch of obstacles to overcome. I probably could have used `home-manager` to resolve some of these issues, but I was focused on making things more difficult than they had to be by configuring everything the way I was used to.

While I was able to get `dwm` working rather quickly, I spent a decent amount of time attempting to get `dwmblocks` to display correctly. Even when I did, I had a lot of trouble getting the bar's objects to be clickable. I'm writing this article after the fact (and after having deleted my NixOS VM in favor of a fresh start), but I don't recall ever getting the bar to work as it does on Arch and Debian.

Another piece that required many iterations was getting an optimized "configuration.nix" file. Back during the summer of 2023, my coding and scripting skills were minimal. I could parse a NixOS configuration file, but I ran into some issues while writing my own. Piecing together a working config file required trial and error, and I redeployed the NixOS VM a handful of times as I figured out what worked and what didn't.

---

## Fresh Install - Tips and Tricks

While it took me a handful of days to get my "configuration.nix" file working correctly, the benefit of NixOS is that a fresh install is incredibly easy when using a previously configured installation. I would simply use the file I created, which can be found on my [GitHub](https://github.com/davidvogelxyz/nixos), and run:

```
nixos-rebuild switch
```

A fresh configuration is mostly similar. Boot into an installation media (ISO burned onto a USB drive), do the same partitioning and file system creation done for any Linux distribution, mount the drives, and then run:

```
nixos-generate-config --root /mnt
```

Configure the file found at "/mnt/etc/nixos/configuration.nix", and then install the OS using:

```
nixos-install
```

---

## Helpful Videos

## {{< youtube id="_Z32SYFbxpw" title="First Time NixOS Install with Customization" >}}

## {{< youtube id="IRRtk320j2A" title="NixOS Config - Autologin - Flatpak - Fonts - Polkit - Release Upgrade" >}}

## {{< youtube id="1qd0iHadvdo" title="NixOS Fast Reboots with SystemD TimeOut" >}}

## {{< youtube id="l7HvMM6rLNE" title="NixOS NFS Mounting" >}}

## {{< youtube id="fuWPuJZ9NcU" title="NixOS is Mindblowing" >}}

## {{< youtube id="wpS3qIprHL0" title="NixOS Gaming Setup and Comparison" >}}

## {{< youtube id="NuPKijYukuQ" title="NixOS is NOT for Beginners" >}}

## {{< youtube id="Hiwyu7wXB8U" title="NixOS Revisited" >}}

## {{< youtube id="8lCgb1xEp8w" title="NixOS Update and Cleanup" >}}

## {{< youtube id="T8mY9LhnER4" title="NixOS Home Manager Install" >}}
