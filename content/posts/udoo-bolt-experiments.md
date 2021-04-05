---
author: "Vignesh Krish"
date: 2021-04-05
linktitle: preliminary experiments with Udoo Bolt
title: Udoo Bolt - Experiments Part 1.
---

I've had the Udoo Bolt ever since the Kickstarter campaign of 2019(?), I forget. It is a nifty little Single-Board-Computer (SBC) that packs a Ryzen Embedded V1000-series CPU into a nice chassis with some nice perks such as GPIO ports and USB-C for powering and video-output. You can find the specifications [here](https://www.udoo.org/discover-the-udoo-bolt/).

I have the cheaper and slightly less powerful variant of the two available: V3. It comes with a two-core / four-thread Ryzen running at 2.3 GHz. It is a very interesting little piece of hardware.

This is typed out on the Udoo Bolt running *Elementary OS (Hera)* with a partitioning system that divvies up the 32GB eMMC and the 240GB SSD into a frankenstein of a partition table. 

### Setting it Up

Setting up a SBC with their custom enclosure has been quite a walk in the park. I've set it up with the following:

1. Transcend MP510 NVMe SSD
2. 8GB Transcend Memory Module TS1GSH64V4B
3. Udoo Metal Chassis

The hardest part of the process was sourcing a working BT/WiFi chipset that connects to the M.2-2230 port available on the SBC and of course playing around with Linux on it.

### Handling WiFi/BT

Currently, the little PC is connected to the internet via an old-fashioned but easy to get-working Ethernet cable. The hardest part of the process in setting it up has been the whole WiFi/BT setup.

The Udoo Bolt comes with a `M.2 2230` connector on the board. It is perfect for unified BT/WiFi modules such as these:

![](/images/m2-2230-image.jpeg)

I ended up picking up an Intel module: `Intel Wireless AC-9200`. The first problem was that the module shipped without the cables for the antenna. I have not yet sourced the antenna cables for the module. But, even then, the modules were not properly recognized by the flavor of Linux I ran back then: Manjaro. I wasn't able to diagnose the cause of the problem because I did not have a usable system to test it with. 

Then, I realised that I had a different module lying around. This was an Asus PCI-E 1x card which is actually just an PCI-E extender on a M.2 2230 card, this time the `Intel Wireless AC-8206NGW` (I'll have to double check on this).

Without the proper cables and antennas, I skipped the process of testing the WiFi cards and ended up using a straightforward Ethernet connection as it is tried and tested and it worked without any issues.


### Linux Flavors

As of this moment, I have tried 3 different flavors of Linux on the board: `Manjaro, Ubuntu, Elementary OS`. All the 3 different flavors worked flawlessly:

- The Manjaro linux was on an i3 window manager
- Ubuntu was on the standard gnome window manager
- Elementary OS (the flavor I'm typing this on) rolls its own.

There was no issues / problems with any of the three different flavors. All of them worked flawlessly and without any issues when loading it up either from the USB drive or getting it installed.

I've installed the Manjaro linux on the eMMC while the Elementary OS is now on the SSD. There haven't been any major issues in moving them around with respect to partitions, all of the flavors have worked out fine. 

### Going forward...

This little SBC is going to be my temporary desktop where I'd like to try to setup and play around with different things. It seems to handle most of my workloads fine.

YouTube on 4K seems to play without issues while chugging along with the Visual Studio Code where i'm editing something. Blender also seems to work fine and renders some of the demo scenes without any hitches.

I've not been able to throw advanced workloads at it yet. The plan is to set up and play around with OpenCL as that is something I'd like to see and experiment with in the future.

As things stand it seems to be a quite alright machine to use as a playground for very-many things. With that in mind, I'm quite happy with it and its performance. If things start to choke up, I wouldn't mind throwing an extra 16 GB memory module at the system to see if that expands some of its footprint.

**Things to do...**

- I still want to get the WiFi/BT module to work on it, that would make it the perfect use case for a small hidden away NAS system
- I want to get AMD's OpenCL libraries working, it seems to be available but the process to get it working seems to be slightly convoluted.
- Finally, I have an Intel Neural Compute Stick 2 lying around, I don't know where I found it from. But, it seems promising and I would like to experiment with the stick to see if I can use it as a local Deep Learning processor coupled with the Udoo Bolt

