---
title: Mortality is scary! Here's a visualization inspired by Isabella Benabaye to help confront the fear.

image:
  focal_point: ""
  placement: 2
  preview_only: True

# Link this post with a project
projects: ['lifespan_viz']

# Date published
date: "2021-02-02T00:00:01Z"

# Date updated
lastmod: "2021-02-02T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: true

design:
  columns: '2'

links:
- icon: github
  icon_pack: fab
  name: Isabella's Code
  url: https://github.com/isabellabenabaye/life-chart

- icon: github
  icon_pack: fab
  name: My Code
  url: https://github.com/xndrmcw/lifespan_viz

authors:
- admin

tags: ['Data Visualization']


---

<img src="/media/lifespan_viz_photos/life_in_months_final.png" height="60%">

## Welcome to my third post! I'm not sure how sustainable it is to keep numbering the posts, but oh well.

I haven't done much visualization work in R before, but when the opportunity lands right in my lap, it feels silly to pass it up! Isabella Benabaye wrote a post on how to install custom CSS elements and themes into the hugo academic theme, and I was really impressed by the style of her website, as well as the elements of that post. I kept looking through her website, and I was so impressed! Her visualizations are some of the most gorgeous I've ever seen - some people really just know how to paint a picture. Of course, I want as many people to see her website as possible, so here it is!

<p style="color:white;"><a href="https://isabella-b.com/">Isabella Benabaye!</a></p>

Anyway, I finished reading that post about hugo, and started perusing around her website. She's got a boatload of awesome projects and code to show you exactly how to create your own version! I saw her [life span waffle graph](https://isabella-b.com/blog/my-life-in-months/) and I thought it looked awesome, so I gave it a glance. It looked pretty straightforward, so I tried my hand at it!

><p style="color:#F9C59F;">I spent a lot of time troubleshooting.</p>

I was overconfident going in, and I think I fumbled around with some install package settings that I wasn't supposed to (I imported plyr instead of dplyr, and it messed everything up. Something to do with the count function, I don't know.) Oh well! After a good chunk of time spent twiddling with the code, I finally got a working chunk. If you want to see my code, [feel free!](https://xndrmcw.netlify.app/project/lifespan_viz)

After I generated the waffle graph, I realized that the default legend wasn't quite to my taste, so I spent a little while using GIMP (yes, I'm in college, yes, I'm broke,) to mess around and make things look a little nicer, and provide some clarity.

><p style="color:#F9C59F;">In all honesty, there's a good reason why I decided to create my own visualization of this sort. The passing of time is terrifying, especially when it's your last semester of college.</p>

This graph, to me, serves both as warning and motivator. I'm happy with the person I am today as well as the choices that I've made, but those choices *are* in the past, whether I like them all or not. I can't get back the time that I spent aimlessly. As much as I do miss the past, though, I know that new and exciting parts of life are coming soon. I'm not sure where I'm going to end up location-wise, but I know that I'll find happiness where I go. The key, I think, is that I need to actively search for that happiness. I'm through with sitting and waiting for opportunities to come to me. Enough of that.

><p style="color:#F9C59F;font-size: 34px;">All of this is behind me! I'll miss it. Even the awkward bits.</p>

<img src="/media/lifespan_viz_photos/gone.png" width="50%">


><p style="color:#F9C59F;font-size: 34px;">Fortunately, I've still got all of this left to go! No doubt there are going to be some awkward bits in there too, though...</p>

<img src="/media/lifespan_viz_photos/left.png" width="50%">

><p style="color:#EC7178;">Despite the anxiety that seems to arrive hand in hand with visualizations in which we can see our 'end' like those above, there's always a silver lining. If you're lucky enough to be "average," you can expect to see your late 70s.</p>
><p style="color:#EC7178;">Assuming you're 20, that's another 720 months of life. Think of all the amazing things that have happened to you in the small fraction of life that you've had (and by that I mean literally everything that you've ever experienced,) and take a minute or two to think about the fact that you're going to do it nearly three more times. Wow. </p>

><p style="color:#EC7178;"> If tomorrow, last week, last month, or even the last year wasn't amazing for you, that's okay. There are ebbs and flows in our paths, peaks and valleys on the road of life.</p>

><p style="color:#EC7178;">Peaks and valleys.</p>

{{< figure src="/media/lifespan_viz_photos/sunset.PNG" height="50%">}}
