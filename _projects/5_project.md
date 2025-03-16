---
layout: page
title: Ubuntu Home Server
description: Coverting a old 2012 mac mini into a home media server
img: assets/img/JellyfinLogo.png
importance: 3
category: Fun
---

As I was trying to better learn Linux, I took it upon myself to set up a GUI-less Ubuntu server on my old family computer, a 2012 Mac Mini. It was a rollercoaster of learning and troubleshooting to get everything working as I wanted.

First, I did my initial research into what kind of OS I wanted to install. There are tons of server Linux distributions to choose from, but since I was a newbie, I leaned toward the most common and popular ones to make troubleshooting easier. I eventually narrowed it down to Ubuntu and Fedora. I ended up choosing Ubuntu because the media application I planned to install, Jellyfin, had a direct guide for Ubuntu, which made the process much simpler.

From there, I followed the standard procedure for installing a new OS. I made sure to back up any files I wanted to keep from the old Mac, then wiped the memory and prepared it for the USB stick containing the Ubuntu Server installer. Next, I went through the 10-minute process of selecting options for how I wanted the distribution set up. One key setting I had to keep in mind was ensuring the server was SSH-able. Since this was a GUI-less setup and I didn’t plan to keep a monitor attached to the Mac Mini, I needed a way to access the command terminal remotely. SSH allows me to control the machine completely—as long as I know the IP (local, in this case) and have the password—without ever physically touching it.

However, there were a few extra steps before I could use SSH. Specifically, once the Ubuntu server was fully set up and running, I modified a few settings, such as assigning a static IP to prevent it from changing, making it easier to connect to. I also plugged the Mac Mini directly into my router with an Ethernet cable for faster speeds (I may have also had some trouble getting it to connect to Wi-Fi remotely, so this was simpler and more reliable). With that done, all that was left was to install the applications I wanted to run. In this case, I pulled up the Jellyfin webpage and followed the guide to install it.

I had no issues installing Jellyfin and getting it to run, so the final step was to transfer the media I wanted onto the machine and set up a directory for Jellyfin to read from. I used FileZilla to remotely transfer files from my Windows desktop to the Ubuntu server. A word of advice: make sure you keep track of your server’s storage, and do not try to transfer more data than the server can store. I ended up bricking Jellyfin by overflowing its allotted memory, which caused it to crash every time I tried to boot the application.

This problem took almost six hours to solve. I tried to figure out what went wrong on my own, but eventually, I cracked and consulted the gurus on the Jellyfin forums, alongside reviewing the logs from my machine. Here, I was truly shown how much I still have to learn. Within 30 minutes, I received a message from a forum user—practically a god—providing a single command that solved all my problems with the press of the Enter key.

The moral of the story: forums are your friends, and the people who give advice there can actually use magic. Also, make sure you have enough storage for whatever you want to transfer to your home server. Currently, my Ubuntu server is still hosting Jellyfin, accessible to anyone on my Wi-Fi. In the future, I plan to install more applications to expand its functionality, such as Mealie, which stores and hosts recipes. Eventually, I plan to redo my system to use Docker, as, from my reading, it will provide significant value by making it easier to install new applications and troubleshoot issues.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/JellyfinExample.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/MacServer1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    on the left is a example of a page on Jellyfin, while the right is the ugly old mac mini plugged into the router.
</div>




