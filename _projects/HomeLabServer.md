---
layout: page
title: HomeLab Server
description: Converted a old dell desktop into a homelab and docker management
img: assets/img/Homarr.jpg
importance: 2
category: Work
---

I got gifted an old dell desktop from a friend, and I saw it as the perfect oppertunity to truly create a homelab that goes just beyond the smaller projects I've done in the past. Even now it's a work in progress, but it's at a point now that I feel comfortable to show what I've done so far.

To begin, first had to buy a small cheap SSD because the hard drives that were had just lost their last leg. plus installing the OS onto a SSD provides fast boot speeds and tend to last a bit longer compared to hard drives. Once installed, I got my Ubuntu server ISO flashed onto a hard drive and went through the installation process. I won't bore you with the specific, but it went without a hitch, and now I had a desktop running the current ubuntu server, and ready to be SSH by my laptop in order to start configuation.

In some earlier researching I had decided to install a dashboard application called Homarr, which can be linked with docker to provide nice UI, especially if you install other applications into docker containers. As it currently stands, every major app I've installed is installed via docker, which provides some useful benofits. For starters, it creates a level of isolation between the system and the application, which can reduce applications messing with each other in unintended ways, and can even provide a level of security similar to a VM (Though it should be noted that it is NOT a VM, and while it provides similar benofits, it is not as isolating as a VM is). 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Homarr.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Screenshot of my Homarr dashboard
</div>

However, this natural isolation does have it's downsides. A major one is that it only can access directories and areas that you give it permission to, so for services that deal with data/media storage, you'll need to make sure they have proper access when setting up the container. Luckily, Docker Compose is a easy and simple way of doing that, especially for many of the langer applications that have guides on how to do it. 

Currently I have about half a dozen different applications installed via docker compose such as:

<ul>
  <li>A Media hosting platform</li>
  <li>A file hosting platform</li>
  <li>A image hosting platform (for pictures/videos from my phone)</li>
  <li>A Torrenting service for downloading Linux distros</li>
  <li>And much more</li>
</ul>  

However, currently I only had around 250GB from the SSD that I had bought, and if I truly wanted to use this homelab as a way to condense all of my files and media, I would likely need alot more storage, and I wanted to do it in a more secure way. So I had decided that I wanted to buy a couple of hard drives and set them up in a RAID formation, so that I could sleep comfortable at night knowing that even in the event of a hard drive failure, my data would still be save.

My local Micro center was nice enough to already have a sale on some nice 4TB of Server/RAID grade drives that was just what I was looking for. I ended up buying three and going with a RAID 5 formation, so I would get around 8TB of storage with one redunded drive. Futhermore, this would boost my read speed due data being spread among multiple drives. 

This did come at the cost of some write speed, and if I ever need to replace a drive it would take about 10 hours for the RAID to be reformated.

Again I won't go into too much detail about the process, as it was simple following a bunch of commands to configure the RAID formation and then set it up as a place I could mount directories to. From there it was a matter of created some directories there, and creating pathways to the different docker containers I wanted them to be able to read and write to.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/DellDesktop.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The desktop everything is running on
</div>

And now I have the perfect base for moving onto more interesting stuff. Perhaps in the future I'll upgrade the ram, but with it starting with 20GB, that should be more than plenty start working on future ventures like a docker network for pentesting practice, or setting up some VMs.
