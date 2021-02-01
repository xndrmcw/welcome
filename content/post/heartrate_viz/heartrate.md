---
title: Using Fitbit heartbeat data to make a cute viz.


# Link this post with a project
projects: []

# Date published
date: "2021-02-01T00:00:00Z"

# Date updated
lastmod: "2021-02-01T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: true

authors:
- admin

tags:
- Visualization
---

<iframe width="700" height="600" frameborder="0" scrolling="no" src="//plotly.com/~alexandermcw/1.embed"></iframe>

It's not particularly difficult to create visualizations, but, from what I hear, it's pretty tricky to make good ones! That being said, I think this one isn't half bad! It pretty clearly illustrates what it's supposed to, it's not particularly bulky. You might argue that using a scatterplot for heartrate is weird, but I really like being able to mouse over the individual points.

This graph, surprisingly, was a bit of a force to get together. I'll walk through the steps I had to take to get to this point below! Even though there were some obstacles, it was a blast, and I recommend it to anyone looking to create a fun little viz project.


So, before you say it, I know! Fitbit provides a similar visualization in their own app. What they <b><i>don't</b></ do (for a reason I'm still not sure of) is allow you to download your heartrate data in a csv format! My initial goal with this project was to get familiar with animated visualizations, and I figured that creating a pulsing heartrate graph would be pretty sweet.

I couldn't find anything on the fitbit forums about downloading heartrate data. My guess is that HR data is pretty hard to come by, so maybe they don't want to just give it out willy-nilly. I dunno. It's kind of a bummer, though! Fortunately, I found a fantastic resource that does exactly what I was hoping for!

[**Check out Neil Ricci's Pulse Watch tool!**](https://iccir919.github.io/pulseWatch/public/index.html)

If you provide this website access to your fitbit account (you'll need your signin info), it'll prompt you with the option to choose either

{{< figure src="/media/heartrate_viz_photos/options.PNG" caption="Inter/Intra" >}}

I used a single day for this dataset, but I'll show some screenshots of both, just because it's a great website, and Neil did an amazing job with it.

{{< figure src="/media/heartrate_viz_photos/interday_hr.PNG" caption="Interday UI" >}}
{{< figure src="/media/heartrate_viz_photos/intraday_hr.PNG" caption="Intraday UI" >}}
