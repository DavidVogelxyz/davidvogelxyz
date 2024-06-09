---
title: "Neovim: Now in Lua!"
date: 2023-08-27T22:24:38-04:00
tags: ['home-lab','other']
---

{{< context >}}

![Neovim banner](/images/neovim-banner.png)

## Introductory Notes

This article tells the story of how I wrote my own [Neovim configuration](https://github.com/davidvogelxyz/nvim) from scratch -- this project can be accessed by following the link to my GitHub.

## "You Can Go Your Own Way"

While I was working on my `debian-dwm` project (links: to [article](/home-lab/other/debian-dwm); to [GitHub](https://github.com/davidvogelxyz/debian-dwm)), I began to notice that my Neovim experience wasn't exactly where I wanted it to be. I had been using Luke Smith's Vim config file for about a year now, and it was an excellent way to get started with Neovim. However, I was beginning to use Neovim for everything I did on my machine, and I was starting to realize that there were more features that I wanted. After watching enough of thePrimeagen's content, I knew that I wanted some additional plugins that would take my experience to the next level. Fortunately, I had recently come across a video of his, where he starts with the bare-bones Neovim experience and builds it from scratch to suit his needs. And, I thought, "hey, why not do it with him?" In the worst case scenario, I could always revert back to using Luke's Vim config file.

So, I sat down one day in late August 2023, and wrote my own Neovim configs alongside Prime. The first thing that I had to get used to was Lua. While Luke Smith's Vim config was written in Vimscript, so it would be backwards compatible with the original Vim, Prime was writing configs for Neovim alone, and so he opted to use Lua in order to have greater control over the code he wrote. By doing this, I learned a ton about how my favorite text editor functioned. I learned:

- How to work in Netrw, Neovim's default file explorer, allowing me to create files and directories without having to exit Neovim.
- How to create profiles for Neovim, so I could have alternate versions of my setup.
    - For example, I created two profiles that were identical, except that one would install the LSP plugin, and one that wouldn't.
    - Pairing this with `debian-dwm`, I would be able to choose whether or not to install an LSP with my Neovim, saving myself time on VMs that weren't going to be used for coding.
- How to create custom keymaps that worked well with my [new Kinesis keyboard](/home-lab/other/kinesis).
    - One of my favorites is that I bound "save file" to a double-tap of the spacebar.
        - This has enabled me to save my work incredibly quickly.
        - As a byproduct, I now save my work after every change, without even realizing it.
- How to install and operate a plugin manager.
    - While I still use `vim-plug`, as I did when using Luke's configs, I learned how it actually works, and that allowed me to more easily add and remove plugins.
    - Also, I learned how to direct `vim-plug` to install a specific version of a plugin.
- How to add new colorschemes to my Neovim configs.
    - This didn't really help my productivity, but it definitely improves the experience. When you're looking at raw texts for hours at a time, you want it to look aesthetically pleasing!
- How to set options in Lua, as opposed to Vimscript.
    - While all my settings are beneficial, the following is a small list of options I figured out at this time:
        - Incremental search is useful for showing what exactly I'm searching for, and where it appears in the file.
        - Scroll offset (scrolloff) keeps me from editing files near the bottom or top of my file.
            - Unless I'm at the absolute first or last lines of a file, Neovim will enforce a buffer, so I can see the lines above or below what I'm working on.
        - Remapping <Ctrl-U> and <Ctrl-D> with "zz" -- this allows me to keep my eyes on the center of the screen as I jump up and down the file.
            - I also have the same setting for using search, which means I barely have to scan to find the string I'm searching for, since it's always near the center of the screen.

I was also introduced to some awesome new plugins!

## Plugins

These tools have greatly improved my ability to use Neovim. Especially when working on code projects, I can't work without them.

### Telescope

One of my favorite additions to my Neovim is Telescope: a fuzzy finder. While Luke's configs also had a fuzzy finder, Telescope enabled me to also have a file preview for any file that I was searching over. Because of Telescope, I massively increased my use of the fuzzy finder within Neovim -- where I almost never used `fzf`, I constantly use Telescope. With Prime's help, I also added some custom keymaps, including one that allows me to use `grep` through the entire working directory to search for a file, and then displays that output in Telescope. This has been a great help when working within a repository, as I can now quickly find files I'm working on.

### Harpoon

As Prime accurately describes it, Harpoon is truly "a glorious way to navigate files". Basically, what Harpoon allows the user to do is to use the same set of keymaps for switching between files. What does that mean? It means that I know that "Ctrl-J" is always my #1 file in a project, "Ctrl-K" is my #2 file, and "Ctrl-L" is my #3 file. Then, no matter what project I'm working on, I can use those same keymaps to always hit the most important files. I can readily change those files out; if another file needs to be moved in, or the positions need to change, I can do that with no effort required. In addition, the marks are set on a "per repo" basis. If I'm working on my `debian-dwm` project, those keymaps will access the marks for that project; if I switch over to the `library` repo, then I have access to the marks for *that* repo. So, I now have the muscle memory to very effortlessly flip through the most accessed files in any one of my repos/directories/projects. And, if I want to add something that's not in my Harpoon just yet, I use Telescope to navigate to it, add it to Harpoon, and then set it as whichever mark I need it to be. Harpoon is incredibly useful.

### LSP

The last thing I want to shout out in particular are Language Server Protocols (LSPs) in Neovim. While I wasn't coding much besides Bash scripts at the time, setting up LSPs paid dividends in the future. Once I started coding in Rust, having `rust-analyzer` built into Neovim made life so easy, as I was able to have my code actively assessed by the Rust compiler while I was programming. I also got some auto-complete features and function descriptions built into my Neovim. It's not something I needed up until this point, but now that I have them, I don't know what I'd do without them.

## I Use Vim, BTW

While I was using Vim a lot before this, creating my own custom configuration caused me to love Vim even more. I now use Vim for everything I can, whether it's coding, writing documentation in Markdown, or even my daily to-do lists. The more I use it, the more I become comfortable with using Vim motions and navigating using Harpoon and Telescope. Since creating these config files, I have become a bit obsessed with using Vim for everything I can. I even have a version of my Neovim configs written in Vimscript; that way, when I'm working on servers, I can quickly deploy a more lean version of my setup using just Vim (as opposed to Neovim).

It's kinda become a way of life. 🤣

## Helpful Videos

## {{< youtube id="w7i4amO_zaE" title="0 to LSP : Neovim RC From Scratch" >}}
