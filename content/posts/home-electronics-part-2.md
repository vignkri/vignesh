---
author: "Vignesh Krish"
date: 2021-09-20
linktitle: preliminary experiments with rpi4
title: Home Electronics Experiment - Part 2.
---
This is a continuation of [Part 1](/posts/home-electronics-part-1).

The first part of the series focused on an Udoo Bolt. To augment with something low-powered, I added a Raspberry Pi 4 with 8GB RAM as an always-on server in the local network. This server is quite powerful, the preliminary aim with the RP4 was to set up a network level ad-blocker than individual adblockers on a browser level. As things progressed, the overall usage of the RPI has also increased dramatically. It is now running a bunch of different applications.

## PiHole

The first part of the run was getting to use [PiHole](https://pi-hole.net/). It is an open-source project that aims to set up a network-level adblocker which automatically filters the requests. The overall process of setting up a PiHole was very simple. I just had to setup a very nice `docker-compose.yml` file that made it easy to run and add this docker image to the service so that it automatically came online whenever the pi rebooted. 

Once, this was up and running, the only other requirement is on the router level, to setup a fixed IP for the RP4 and setting it up as the target DNS server. This made sure that the requests were routed through the RP4.

**Benefits**

- Now I have a perfectly functional network level ad-blocker on all my systems, especially for the phones.
- All the networked-devices such as the smart-TV and other smart devices no longer phone home. My smart-TV is notorious for this behaviour as the logs on the piHole indicate that the TV phones home quite a lot
- If needed, this DNS server can also be a VPN server allowing to change geographical locations for different services. 

## Calibre

[Calibre](https://calibre-ebook.com/) is an open-source E-book management system. The best part of Calibre is the ability to take in Amazon's proprietary format(s): `.mobi`, or `.azw` and generate more commonly usable format: `.epub`. This allows for inter-operability and reduces the walled garden approach to the ebooks you get to buy on Amazon Kindle Store.

The best part of Calibre is that you can setup a server that allows for adding and downloading the books from your library quite easily. It is a very simple server that can be launched from the command-line that allows for importing, exporting and even reading a book from one of the bookshelves.

**Benefits**

- Reduce the dependence on one single store for getting ebooks.
- Enables freedom of usage with the ebooks: conversions, DRM-removal and using your purchased books with more freedom
- Adds ability to manage e-books better while allowing imports and exports

## SyncThing

[SycnThing](https://syncthing.net/) is an open-source, continouous file-synchronization tool. It is basically dropbox but open-source. And my pi is the synchronisation agent for my notes that is done using [Obsidian](https://obsidian.md/) to synchronise my work laptop, and my desktop. Since my desktop is not always on, this in-between setup allows for my work laptop to synchronise well with my desktop.

**Benefits**

- Freedom of synchronisation of my text-only notes
- Writing a linux service makes sure that the service auto-runs and the web-ui is always available on the default port on the local network
- Keeps my notes up-to-date without any issues across my systems

So, that is the current state of my home-electronics network. A raspberry pi that handles the advertisement blocking on the DNS level and a bunch of web-UI tools to help with library management of books and note synchronisation. Stay tuned for more in the Home Electronics series, hoping to add a bunch more of usefulness in the system in the future. 
