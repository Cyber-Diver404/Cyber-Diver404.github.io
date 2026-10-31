---
layout: page
title: Automating Discord Bot with n8n
description: Created a news bot using my local n8n install on my home server
img: assets/img/n8nLogo.jpg
importance: 2
category: Fun
---

What started me down this path was wanting to have a channel in my club's discord that posted daily news about topics related to cybersecurity. After some intial googling I stumbled upon n8n and decided that this would be the platform I do it with. 

Even before my inciting problem, I had been interested in experimenting with some of these workflow applications I had seen alongside my social media feed. n8n seemed the best, because I could locally host it on my homer server, there was alot of public resources I could pull from, and if I wanted to dig deeper, it supports integrating AI LLMs and agents which would allow me to built some cooler stuff down the line. (I eventually want to get around to building a n8n workflow that acts like the ship's computer from Star Trek: Next Generation).

With that in mind I set about getting my intial setup complete. With just a few clicks, I installed it using a docker container for easy update and isolation, and boom, I was ready to start poking random stuff untill I achived my goal. I watched some youtube videos that gave a brief walkthrough of how the UI works, some of the basic nodes that most workflows will touch, and I was ready to begin.

My starting Idea was to pick a couple common website that post reliable cybersecurity related news, use the RSS feeds to pull that data, clean it up, and then posted it in a specific discord channel dedicated to news articles. At for the most part, that is ultamately what I ended up on, just with a few additional tweaks for a better apperance and a cleaner output.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/n8nWorkflow.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Workflow in n8n
</div>

In the future I should be able to futher streamline it, as there is some minor redundancy in how I layed out the nodes, but currently it works well and createds the newsfeed I was looking for!

Here is how the workflow works:

1. at 8am every day the workflow is triggered
2. It will pull from 3 different RSS feeds that I have programmed in
3. It filters out any story that has already been posted by the bot
4. Then it will make sure to limit how many stories can come from a single source (reduce spam)
5. It then is sent to a webhook into my discord's channel dedicated for news sources

Overall I'm quite happy with the outcome, but I know as I learn the tool better, there will be more effective ways to do the same task I just did. I also am excited to mess around with hooking n8n up to my local Qwen mode I have running on the same server on a old 1660 super GPU I had as my first gaming PC. Though I want to get better at doing deterministic automation before I move onto have an AI reponsible for certain outcomes, due to the inherit risk that can have.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/discordWebHook.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Discord output
</div>


