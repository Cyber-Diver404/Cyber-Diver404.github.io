---
layout: page
title: Ubuntu Home Server
description: Coverting a old 2012 mac mini into a home media server
img: assets/img/1.jpg
importance: 3
category: fun
---

As I was trying to better learn linux, I took it upon myself to set up a GUI-less Ubuntu server on my old family computer, a 2012 mac mini. It was a rollercoster of learning and troubleshooting in order to get everything to work as I wanted. 

First, I did my intial research into what kind of OS I wanted to install. There are tons of Server Linux distros to choose from, but since I was a newbie, I leaned towards the most common and popular, so it would be easier to troubleshoot online. I eventually narrowed it down just to ubuntu and Fedora. From there I ended up choosing ubuntu, because the media application I was going to install, Jellyfin, had a direct guide for Ubuntu, so that made it pretty easy.

From there I followed the standard procidure for installing a new OS. I make sure I had any files I wanted off the old mac, then I wiped the memory and prepared it for the USB stick that had the ubuntu server installer loaded. From there I went through the 10min process of selecting options for how I want the distro set up. A key setting I knew I had to keep in mind was making sure it was SSH-able. Since This is GUI-less and I don't plan to keep a monitor attached to the mac mini, I need a way to access the command terminal remotely, and the primary way of doing that is via SSH. It allows me if I know the IP (local in this case) and have the password to the machine I have complete control over machine without ever physically touching it. 

But there were a few extra steps before I could SSH. Specifcally, once the Ubuntu server was fully set up and running, I modified a few settings, such has the IP to prevent it from changing so it would be easier to boot into. I also plug it directly into my router with a ethernet cable for faster speed (I also may have had some trouble getting it to connect to wifi remotely, so this was simplier and easier). Now all that was left was to install whatever applications I wanted to run, so in this case I pulled up the Jellyfin webpage and followed the guide to install it.

From there I had no issue installing it and getting jellyfin to run, so all that was left was to transfer whatever media you wanted onto the machine and set up a directory for it to read from. In this case I used FileZilla to remotely transfer the files from my windows desktop to the Ubuntu server. A tip of advice, make sure you keep track of your storage on the server, and DO NOT try and transfer more data than what could be stored. As I ended up bricking Jellyfin specificly by overflowing it's alloted memory, which cause it to crash whenever you booted the application. 

This would take almost 6 hours to solve, as I tried to figure out what went wrong, and eventually I cracked and consulted the Gurus of the Jellyfin forums alongside the logs from my machine. Here I was trully show just how much I still need to learn, as within 30 minutes, I was sent a message from god, giving me a single command prompt that solve all of my problems with a single enter key.

Moral of the story, forums are your friends, and the people who give advice there can actually use magic. Also make sure you have enough storage for whatever you want to tranfer to your home server. Currently my ubuntu server is still hosting jellyfin, accessable to all who are on my wifi. In the future I plan to install some more applications to widen what it offers, such as mealie, which stores and hosts recipes. Eventually I plan to redo my system to use the docker system, as from my reading that will provide a ton of value in making it easier to install new stuff and troubleshoot. 



<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>




