---
title: "Bitcoin Nodes"
---

{{< menu >}}

## ![Bitcoin logo](/images/bitcoin.png)

## Context

Bitcoin node
: A server that runs the [*Bitcoin Core*](https://github.com/bitcoin/bitcoin) software and verifies transactions.

The reason to run a Bitcoin node is simple: when using Bitcoin, when dealing with money, how does one trust the servers that are communicating with the wallet (account) software? The server administrator is always going to have an idea of who's pinging from where, and metadata leaks a ton about transaction details. The solution is simple: self-host the server. The solution is running a Bitcoin node.

A *bare minimum* expectation for a Bitcoin node is to be a reference server for wallet software, though a node may also run other software to increase functionality. Those other softwares can include blockchain explorers, privacy-enhancing tools, and access to the Lightning network. Because nodes are used as the reference server for wallet software, high availability is incredibly important and uptime needs to be maximized.

---

In this section, I walk through the different iterations of Bitcoin nodes I've run.

1. [Bitcoin Node Version 1](/home-lab/bitcoin/bitcoin-node-v1) includes all of my first nodes, which were also my first ever [home lab projects](/home-lab). The first iteration was a Windows computer running *Bitcoin Core*, followed by a Ubuntu Desktop instance running Bitcoin alongside a blockchain explorer (btc-rpc-explorer). The final update to the Version 1 era was to put the node stack onto a Raspberry Pi.

1. [Bitcoin Node Version 2](/home-lab/bitcoin/bitcoin-node-v2) was a major upgrade. I started by running everything headless and using SSH to interface with the servers. Next, I began using new software, including a block indexer (Electrs) and an improved blockchain explorer (Mempool). Later in the Version 2 era, I reinstalled the software stack onto a more powerful mini computer.

1. [Bitcoin Node Version 3](/home-lab/bitcoin/bitcoin-node-v3) improved by upgrading the operating system to Arch Linux and the indexer to Fulcrum.

I also share a story where I was the first to [brute force a Bitcoin wallet](/home-lab/bitcoin/bitcoin-hack) in order to move a small amount of money before anyone else could.

---

{{< articles-section >}}
