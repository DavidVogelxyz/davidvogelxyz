---
title: "Learning Data Structures and Algorithms with thePrimeagen"
date: 2023-08-18T22:24:38-04:00
tags: ['home-lab','other']
---

{{< context >}}

![Frontend Masters banner](/images/frontendmasters-banner.png)

## Deciding to Learn Some Programming

During the end of July 2023 and into August, I began to watch YouTube videos by a Twitch streamer by the name of "[thePrimeagen](https://www.youtube.com/@ThePrimeagen)". His content seriously caught my attention, if for no other reason than he was an avid Vim user, whose skills greatly surpassed mine. Maybe it was his use of coconut oil; I wasn't sure. But, I felt that I could learn a lot by watching him work.

I was wrapping up my free trial experience with [HackTheBox](/home-lab/other/hackthebox), and getting ready to put down $15/month in order to get access to the full platform, when I came across thePrimeagen's Data Structures and Algorithms course on Frontend Masters. It was appropriately named "The Last Algorithms Course You'll Need". I was sold. As someone who had been working on some basic Bash scripts over the past few months and had a very basic understanding of programming, I felt like this course might be a great place to learn the foundations of computer science.

My interest in learning how to code had also been accelerated by the HackTheBox experience. I was getting frustrated with myself for having such a limited understanding of some of the tools that I used for penetration testing. I wanted to get to the next level, where I might be able to start building useful tools for myself. Plus, if I completed thePrimeagen's algorithms course quickly, I could use my remaining month with Frontend Masters to take some other courses. And, worst case scenario, I could always revisit HackTheBox in September once my memership had expired.

### Taking the Course

I started taking thePrimagen's course on August 14th, the Monday after the Friday that I finished the HackTheBox free tier. I was extremely excited for the course, as Prime brought an energy to teaching that I had sparingly encountered. However, I was not prepared for what I had gotten myself into...

I wasn't prepared for a handful of reasons:

1. I had never really done any coding before.
    - While I had some experience with Bash from the scripting I had been doing, my scripts were incredibly basic at this time. Essentially, they were just a series of commands that were being done in succession. I hadn't even written a "for loop" before!
1. I had never seen any JavaScript code before, much less TypeScript.
    - I was able to follow along with what was going on, simply because I had been working for the past year on reading source code for Bash scripts, etc. However, I didn't have any experience with JS/TS, and so there were operations that were being performed that I didn't understand without pausing the lectures and looking up documentation.
1. There was a lot of terminology that I had never encountered before.
    - Similarly to the coding language being used in the course, there was a lot that I hadn't seen before. There were many times throughout the course that I chose to stop and look up the things I didn't know, so I could make the most of the learning experience.
1. My wrists hurt. A lot.
    - Erroneously, I decided to take the course by casting the lectures to my TV and working with Prime by using a laptop. After a 10 hour course that required an additional 10 hours of work as I followed along, typing out every algorithm that he used, I started to get incredible wrist pains, especially from trying to hit all of the curly braces ("{ }") with my ring and pinky fingers. More on this in a bit.

However, I was also more prepared than I thought I'd be. For someone with only a basic understanding of programming, I realized that the work I had put into Linux and Bash were working in my favor. I may not have been able to intuit everything Prime was teaching, but I could read the code, and I was able to complete the course despite having to look things up. I was also reminded of a YouTuber named Presh Talwalker, who ran a channel called "Mind Your Decisions". On this channel, Presh would give some difficult math and logic problems, and then demonstrate how to solve them. Watching some of his videos had definitely prepped me for Prime's course, as many of the algorithms he taught allowed the students to solve problems similar to the ones on Presh's channel. Not only were the problems similar, but I was learning to solve them using code!

An example of a logic problem that was solved with an elegant solution was dubbed the "Two Crystal Balls" problem. The context for the problem was this: the student was given two crystal balls, from which we needed to find the height from which the ball would break. Obviously, we could just drop the first ball from `n=1`, and iterate up until the ball broke. Then, we'd have the answer! However, this solution would take O(n) (O of "n") time to solve. The more efficient way to solve the problem was to utilize both balls. How? We could drop the ball from multiple of the square root of the highest point (100). Once the ball broke, we could use the second ball to iterate by one, starting from the last point of non-breakage, until we found the height at which the balls would break. Solving the problem in this way would only take O(log(n)) (O of log(n)) time.

I found learning to solve problems like this fascinating, and learning how to utilize different algorithms and concepts to solve problems more efficiently has yielded tons of benefits to me (most of which would only reveal themselves later into the future). I was enjoying the content so much, that I powered through the entire course in less than a week -- starting on Monday the 14th, I had completed the entire course by Friday, August 18th.

In the course, I also learned algorithms and concepts such as:

- linear search
- binary search
- bubble sort
- queues and stacks
- arrays and linked lists
- quicksort
- tree traversal
    - depth first traversal
    - breadth first traversal
- binary search tree
- heaps
- graphs
- Dijkstra's shortest path
- maps
- LRU caching

### The Aftermath

After completing Prime's algorithm course, and deriving a ton of value from it, I decided that it might be worth my while to learn a programming language and go deeper into coding. I hadn't yet figured out which language I would choose. Right after the course ended, I thought it might be JavaScript or TypeScript. After taking an intro course to Python with my remaining Frontend Masters membership, I decided that it *wouldn't* be Python; mainly, because I noticed that I could code in Python without too deep of an understanding of the concepts I had just learned about from Prime's course. I wanted a language that would allow (nay, *force*) me to continue to develop my understanding of computer science. I wouldn't figure it out for a few months, but I eventually chose [Rust]() as my first programming language.

However, more immediately, I resolved to make a few changes to how I did things. First, if I was to continue to learn to code and do the things I had been doing, I would need to figure out this keyboard situation. After watching Prime use a Kinesis keyboard throughout the course, I decided to [get my own](/home-lab/other/kinesis). I also made the decision to [learn how to use `git` properly](/home-lab/other/git). With the combination of the Kinesis keyboard and a better understanding of `git`, I would also spend the next few weeks working on two major projects: [creating `debian-dwm`](/home-lab/other/debian-dwm), a version of Luke Smith's LARBS that would install DWM onto Debian computers, and [building my own Neovim configuration files from scratch](/home-lab/other/neovim).

## Video Preview of the Course

## {{< youtube id="Lwr3-doAgaI" title="The Last Algorithms Course You'll Need by ThePrimeagen - Preview" >}}
