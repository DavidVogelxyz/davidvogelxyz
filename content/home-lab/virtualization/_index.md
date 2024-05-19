---
title: "Virtualization (Hypervisors)"
---

{{< menu >}}

## ![KVM banner](/images/kvm-banner.png)

In this section, I have articles about the different virtualization softwares I've worked with.

I started with [QEMU](/home-lab/virtualization/qemu) in early 2023 after building a [new computer from parts](/home-lab/other/desktop). QEMU is a type 2 hypervisor, meaning that there was another operating system (Artix Linux) that the hypervisor ran within. This was where I first learned how to do GPU passthrough.

After learning about QEMU and type 2 hypervisors, I had to find out more about type 1 hypervisors. The idea of being able to self-host a hypervisor in my own home cloud was a really cool thought, and I wanted to make that thought a reality. So, I brought back out the computer that my new desktop replaced, and I turned it into a [Proxmox server](/home-lab/virtualization/proxmox).

---

{{< articles-section >}}
