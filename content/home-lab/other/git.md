---
title: "Git: I \"Git\" It Now"
date: 2023-08-22T22:24:38-04:00
tags: ['home-lab','other']
---

{{< context >}}

![Git banner](/images/git-banner.png)

## Clowning Around on GitHub

To tell the story of how I learned Git, I have to start by being honest: I began using GitHub in January 2023, before I understood Git. Back then, I used it primarily to upload some text files containing "tricks and tips" that I had written and accumulated throughout 2022. None of them were all that good; I didn't even know how to write Markdown at the time. I just needed a place to put some badly formatted text files so I could access them from other computers, and GitHub worked for that purpose.

I was such a clown about it though. For example, I was editing those text files through GitHub, *directly from the browser*. Every time I made a small change, I would "save changes" on the web page. I didn't understand how GitHub worked under the hood, I just did what seemed to make sense. Now, looking back at those repos, I recoil at seeing 300+ commits with absolutely 0 useful commit messages. Checking the difference history and seeing that I was literally editing the text files one typo at a time... it hurts.

I really started properly using Git (and GitHub) in summer of 2023. While I created my [@davidvogelxyz](https://github.com/davidvogelxyz) account in June 2023, it took a few months for me to start using it. However, after learning more from thePrimeagen, especially from his [Data Structures and Algorithms course](/home-lab/other/theprimeagen-dsa-course), I realized it was high time for me to learn how to use Git in a more intelligent way.

And, I'm really glad that I did. It has been, by far, the most useful tool that I've learned to use thus far.

[![Git comic](/images/git-comic.png "Git comic")](/images/git-comic.png)

### Beginning to "Git" Good

There were tons of resources on YouTube that I remember using to start to learn Git: a couple of channels include Chris Titus Tech and Fireship. Some of those videos are embedded below. With my [new keyboard](/home-lab/other/kinesis) assisting me, I consumed tons of content on Git, and came up with some projects that would allow me to test out what I learned. More on those in a bit.

While my Git skills have developed massively since this period, I was starting from zero. Therefore, my focus was on the small things. I began to learn how to make useful commit messages. I leveraged what I knew about GPG keys to make sure I was always signing commit messages with a GPG key. I moved away from editing files in the browser, in favor of using Vim and the terminal to make changes. After committing those changes, I learned how to push changes to the remote repository. These were small steps, I know. But, it was progress.

I also started to develop a deeper appreciation for good documentation. Instead of badly formatted text files, I was writing up guides to projects I was working on using Markdown, compiling them into a repository I called the [Library](https://github.com/davidvogelxyz/library).

I began to notice that any project I worked on usually involved three different sources of information: one that I got 85% of the knowledge from, one that was 12%, and a final one that was the remaining 3%. While I could almost always find the 85% again, and usually find the 12%, it was incredible how often I would fail to bookmark the 3% tip that would fix some issue that I was struggling with. Instead of trying to dig through pages of search results to find it again, I began to write my own comprehensive guides, so that I could use that "single source of truth" going forward, knowing that it had all the information I needed. It didn't matter to me if no one else ever used them; it was good for me to start working on building and maintaining my own work.

Git is a version control software, and it is definitely the main attraction. Having the ability to manage only one set of files (rather than multiple copies of the same files, differentiated by timestamps), but also the ability to look back at previous versions, was an incredible benefit. It also allowed me to easily peer back at the previous state of my work, which made it easier than ever for me to appreciate my growth over time. More than ever before, I had a tool that enabled me to visualize the progress I was making. And that felt really good.

After watching those videos over the course of a day or two, I decided that the best way to gain some skill with Git was to work on a few projects that would force me to use Git properly. The two primary ones from this period of time were:

1. [debian-dwm](/home-lab/other/debian-dwm) - Any time I installed an Arch/Artix Linux desktop, I was using LARBS. I was a huge fan. However, I was using my [Proxmox](/home-lab/virtualization/proxmox) to spin up a bunch of Debian VMs over the summer, and I wanted a way to automate the process of installing the tiling window manager `dwm` onto those machines. So, I wrote an installer, inspired by LARBS, that would do exactly that.
    - Link to the [debian-dwm](https://github.com/davidvogelxyz/debian-dwm) project on GitHub
1. [Neovim config files](/home-lab/other/neovim) - While I had studied the art of Vim under Vim Diesel (Luke Smith), I was approaching a point of stagnation by using someone else's Neovim config files. Therefore, assisted by a video by thePrimeagen, I decided to write my own config files.
    - Link to my [Neovim config files](https://github.com/davidvogelxyz/nvim) on GitHub

## Helpful Videos

## {{< youtube id="v_1iqtOnUMg" title="How to Use GitHub" >}}

## {{< youtube id="ecK3EnyGD8o" title="13 Advanced (but useful) Git Techniques and Shortcuts" >}}
