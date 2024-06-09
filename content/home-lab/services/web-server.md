---
title: "Web Pages and Mail Servers"
date: 2023-06-22T22:24:38-04:00
tags: ['home-lab','network']
---

{{< context >}}

![Vultr banner](/images/vultr-banner.png)

## My first web page

This website, [davidvogel.xyz](https://davidvogel.xyz), is a project that I created using Hugo and self-hosted using Vultr.

After learning how to use Hugo from Luke Smith and his videos (more [here](/home-lab/services/hugo)), I was excited to create my own webpage to document my journey through the build-out of my home lab. Through the guidance of another of his videos, embedded below, I deployed a VPS on Vultr and bought a domain and built this website.

At that time, there was only a handful of projects to document, so I got to work writing articles. Through this process, I not only became more comfortable with spinning up servers in the cloud, but I also learned how to do various things, such as:

- configuring DNS records for websites
- create webpage configurations with `nginx`
- working within `vim` (specifically, `neovim`)
- writing shortcodes for Hugo in Go
- writing articles in Markdown

During early summer of 2023, I created articles for all of the projects that I had done up until this point. While my writing has improved over the course of running this website, it was a great experience to document what I had done thus far. I learned how to write documentation in Markdown, which has come in handy as I've continued to write [guides for my GitHub](https://github.com/davidvogelxyz/library). I started to learn how to code during this time. One of my accomplishments was to create a shortcode that governs the menu found at the top of my website. Another was to write a shortcode that assessed if my articles were older than a certain date, and to add a context blurb explaining that the article was written "in the future". I also edited some of the existing shortcodes that controlled the "previous" and "next" articles, found at the bottom of most pages. All of this was done in `neovim`, which I was beginning to really like as a text editor. I was learning Vim motions, and I no longer felt that `nano` was a faster way to get work done. It was a great summer!

However, I wasn't satisfied with just a webpage. As Luke demonstrates in the video, it was also possible to set up a hosted mail server, such that I could have an e-mail account with my own personal site. I used the installation script that he built to do this too (and had to get permission from Vultr to open the SMTP ports for my server), but I was able to get that working too.

The more I worked on projects like this, the more I was developing a passion for Linux, and self-hosted servers, and free and open-source software. I wanted to complete even more projects, which is why I quickly jumped into the next one: deploying an instance of [Nextcloud cloud storage](/home-lab/services/nextcloud-docker).

---

## Fresh Install - Tips and Tricks

Tips and tricks for setting up a webpage and mail server for the future including the following:

- watch Luke Smith's video. There are a handful of minor additions I have from my time setting up this webpage, but this is an occasion where the original video is truly the best source of information on how to do it.
- Regarding `nginx`, reading documentation on what the server configuration settings actually mean will help in the future with deploying other server projects.
- Regarding `vim` and `neovim`, I learned the basics from watching videos made by Luke Smith. In particular, he has a [video](https://www.youtube.com/watch?v=d8XtNXutVto) where he spends an hour going through `vimtutor`. This is an excellent starting point, and gave me a foundation from which to learn how to Vim. More on this in a future article.
- Regarding shortcodes, Luke's video on how to create shortcodes is a great introduction. To go beyond that, read the Go documentation and start learning Go's syntax.
- Regarding Markdown, a quick read-through of the [documentation on getting started](https://www.markdownguide.org/getting-started/) will help greatly.
    - I think this is an especially good skill to develop, as being able to write in Markdown has many applications, such as being able to create guides and documentation that can be posted onto GitHub, etc. Many projects support Markdown, and it is a simple syntax that makes writing formatted text really easy.

---

## Helpful Videos

## {{< youtube id="3dIVesHEAzc" title="Becoming an Internet Landchad with Luke Smith" >}}

## {{< youtube id="d8XtNXutVto" title="Vim Diesel's OFFICIAL Vimtutor Let's Play/Commentary!" >}}
