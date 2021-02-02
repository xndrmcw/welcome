---
title: Mortality is scary! Here's a visualization inspired by Isabella Benabaye to help confront it.

image:
  focal_point: ""
  placement: 2
  preview_only: false

# Link this post with a project
projects: []

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

## Welcome to my third post! I'm not sure how sustainable it is to keep numbering the posts, but oh well.

I haven't done much visualization work in R before, but when the opportunity lands right in my lap, it feels silly to pass it up! Isabella Benabaye wrote a post on how to install custom CSS elements and themes into the hugo academic theme, and I was really impressed by the style of her website, as well as the elements of that post. I kept looking through her website, and I was so impressed! Her visualizations are some of the most gorgeous I've ever seen - some people really just know how to paint a picture. Of course, I want as many people to see her website as possible, so here it is!

><p style="color:white;">
<a href="https://isabella-b.com/">Isabella Benabaye!</a>
</p>

Anyway, I finished reading that post about hugo, and started perusing around her website. She's got a boatload of awesome projects and code to show you exactly how to create your own version! I saw her [life span waffle graph](https://isabella-b.com/blog/my-life-in-months/) and I thought it looked awesome, so I gave it a glance. It looked pretty straightforward, so I tried my hand at it!

><p style="color:#F9C59F;">I spent a lot of time troubleshooting.</p>

I was overconfident going in, and I think I fumbled around with some install package settings that I wasn't supposed to (I imported plyr instead of dplyr, and it messed everything up. Something to do with the count function, I don't know.) Oh well! After a good chunk of time spent twiddling with the code, I finally got a working chunk. If you want to see my code, [feel free!](https://xndrmcw.netlify.app/project/lifespan_viz)

After I generated the waffle graph, I realized that the default legend wasn't quite to my taste, so I spent a little while using GIMP (yes, I'm in college, yes, I'm broke,) to mess around and make things look a little nicer, and provide some clarity.

In all honesty, there's a good reason why I decided to create my own visualization of this sort - the passing of time is terrifying.

><p style="color:#F9C59F;">Especially when it's your last semester of college.</p>

This graph, to me, serves as a warning and a motivator. I'm happy with the person I am today as well as the choices that I've made, but those choices *are* in the past, whether I like them all or not.

><p style="color:#F9C59F;">All of this</p>

![viz](/media/lifespan_viz_photos/gone.png)

><p style="color:#F9C59F;">is behind me!</p>


[**Check out Neil Ricci's Pulse Watch tool!**](https://iccir919.github.io/pulseWatch/public/index.html)

If you provide this website access to your fitbit account (you'll need your signin info), it'll prompt you with the option to choose either inter or intra day data, as you can see below.

{{< figure src="/media/heartrate_viz_photos/options.PNG" caption="Inter/Intra" >}}

I used intraday, because I was only interested in one day, but I'll include screenshots of both, because it's a great website, and Neil did an amazing job with it.
>## Intra-day HR!
{{< figure src="/media/heartrate_viz_photos/intraday_hr.PNG" >}}

>## Inter-day HR!
{{< figure src="/media/heartrate_viz_photos/interday_hr.PNG" >}}


As for the actual coding - I used Python! Python is popular for data viz, and, in my experience, for good reason. The plotly package ([install guide & documentation found **HERE!**](https://pypi.org/project/plotly)) was fantastic - I had to learn the ins and outs as I went, but I didn't have any significant issues. I love their gradient color scales. The one I selected was arbitrary, I just thought it was nice to look at. If you don't like this one, here's some others they offer, as well as a [hyperlink](https://plotly.com/python/builtin-colorscales/) to the page where you can find a full list!

{{< figure src="/media/heartrate_viz_photos/gradient_colorscales.PNG" >}}

Plotly allows you to export your graphs as jupyter notebook and standalone HTML files, but it also allows for online hosting through the [**Chart Studio Cloud Platform!**](https://chart-studio.plotly.com/) I might make a post that walks line by line through my code to create this visualization later, when I get more comfortable with using Hugo (the GitHub-oriented (is that a thing? GitHub-oriented?? whatever) website builder I'm using).

Anyway, plotly was an easy package to use, and the cloud platform was great! It allowed me to export my visualization as an HTML iframe, which I easily popped into the Hugo config files. I have very little experience with HTML, but learning how to format this very blog post gave me a nice crash-course. I'm learning ways to be more efficient as I go. In the beginning, I was manually editing things in GitHub in browser, and that felt pretty terrible. Switching to the desktop app was great. I'm thinking that I must be missing another piece of the puzzle, though. Having to deploy my website through netlify and waiting for the website to load every time I want to see my changes is pretty rough. Oh well, I'll figure the rest out as I go!

Just as a fun little tradition, I'm going to include either a photo I've taken or that I really like in each of these blog posts.

>This post's photo is...

{{< figure src="/media/heartrate_viz_photos/dinos.PNG" >}}
