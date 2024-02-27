---
title: "Hugo: A Static Site Generator"
date: 2023-06-16T22:24:38-04:00
tags: ['home-lab','other']
---

{{< context >}}

![Hugo banner](/images/hugo-banner.png)

## Creating Websites

After building out a bunch of different services for my home lab, I decided that I wanted to document my journey and process. What better way to do that than to build my own website and begin to post content in the form of blog posts, etc?

While there are many services (WordPress, Wix, SquareSpace, etc) that make it relatively easy to set up a web page, I instead opted to use [Hugo](https://gohugo.io/), a static site generator written in Go. The reasons for this were multi-faceted but simple. I wanted a solution that was:

- free and open source
- easy to learn, implement, and reproduce
- did *not* add in any unnecessary bloat (additional code, like JavaScript, or any additional features like databases, etc)

With this in mind, I found a couple of tutorial videos by Luke Smith (embedded below) that vastly reduced the learning curve for Hugo. It took no more than a few hours of reviewing his content and beginning to build a web page before I had this website built.

One of the perks of Hugo that I really like is its ability to host a Hugo server on a local machine, and being able to access to a live preview of the website. While there are other ways to implement a Markdown previewer, such as a Neovim plugin, having a live test webserver meant that I could make an edit to an article, and immediately see the rendered output before committing any changes. This is incredibly useful, as it allows me to make sure that everything on the site, including hotlinks, are linking correctly before I push any articles to the live webserver.

To make life easier, I set up a VM on my Proxmox for hosting Hugo servers. One particular trick that I implemented was creating a systemd service that would initialize the Hugo server on startup. Beyond the benefit of the server automatically coming online anytime the VM was booted up, setting up systemd services also allowed me to host numerous Hugo servers at the same time by changing the port. This allowed me to work on multiple different website projects at any given time, with all of the startup automated. Very convenient!

With my first web page created in Hugo, the next step was to self-host it.

---

## Fresh Install - Tips and Tricks

The following is an example of what a systemd file for Hugo looks like:

```
[Unit]
Description=hugo
After=network.target

[Service]
WorkingDirectory=/home/$USER/...
ExecStart=/usr/bin/hugo server --noHTTPCache --bind 0.0.0.0 -b $IP_ADDRESS -p 1313
User=$USER

Restart=always
RestartSec=30

[Install]
WantedBy=multi-user.target
```

Obviously, a few edits would need to be made for this example file to work:

- the working directory needs to point to the active Hugo directory
- the "ExecStart" setting requires an IP address for the -b (bind) flag
    - this IP address is the same as the IP of the server hosting the Hugo server
    - instead of an IP address, a hostname for the server can be used, so long as DNS is able to be resolved at the network level
- the "User" setting needs to be set to the user on the server

---

## Helpful Videos

## {{< youtube id="ZFL09qhKi5I" title="Learning to Hugo with Luke Smith" >}}

## {{< youtube id="QTolhoxMyXg" title="Learning to write shortcodes in Go, with Luke Smith" >}}
