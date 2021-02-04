---
title: How to Add Custom Animations to Specific HTML Elements in Hugo v. 0.80.0

image:
  focal_point: ""
  placement: 2
  preview_only: true

# Link this post with a project
projects: []

# Date published
date: "2021-02-04T00:00:01Z"

# Date updated
lastmod: "2021-02-04T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: true

design:
  columns: '2'

links:
- icon: youtube
  icon_pack: fab
  name: Video Tutorial
  url: https://github.com/xndrmcw/heartrate_vis

authors:
- admin

tags: ['Hugo Customization']


---

## I'm a little bit embarrassed by how long it took me to figure this out, but, as I've mentioned in other posts, I've never used HTML/CSS before, so this stuff is completely new to me!

Hello! If you're like me, that is:

>Using Hugo Academic 0.80.0

>Looking to Spice up Your Landing Page

>Confused

Look no further! I'm going to walk you through an example of how you can add animations to the navigation bar, but the same concept applies to nearly any element on the page.

<iframe src="https://giphy.com/embed/dM6nCTSrj1ZUMXGQst" width="480" height="198" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/dM6nCTSrj1ZUMXGQst">via GIPHY</a></p>


First, let's clarify what I'm referring to when I say navbar.

{{< figure src="navbar_1.PNG" >}}

This is your navbar! Let's say you're interested in adding a slick animation from https://animate.style/ to it.

Here's what you need to do:

## 1
Install GitHub desktop and clone your website's repository to your PC. If you don't know what that means, watch [this video](https://www.youtube.com/watch?v=8yqQeTbFZUg). This is just to make life easier - it's a lot easier to edit local files rather than through a browser.

Find your website's folder in 'Users/yourname/Documents/GitHub/yourwebsite'

<figure>
  <img src="directory_1.png">
  <figcaption>Bada-boom!</figcaption>
</figure>

## 2
Download [Atom](https://atom.io/) or any text editor of your choice. I like Atom, but it's also the only one I've ever used, to be fair. In atom, open your directory, and start looking around. Your window should look something like this:

<figure>
  <img src="atom_1.png">
  <figcaption>Note - if your file directory on the left disappears, press ctrl + \ to bring it back.</figcaption>
</figure>

## 3
If you're like me, you won't have a folder called "layouts" yet. Create the folder, and then create another folder within layouts called 'partials'.

<figure>
  <img src="atom_3.png">
  <figcaption>Ignore the folders called widgets and shortcodes, as well as the custom_js.html file. If you already have this directory, just continue onward!</figcaption>
</figure>

Now, here's the part that took me forever to figure out. We're going to use the HTML files provided by on the wowchemy github directory, found [here](https://github.com/wowchemy/wowchemy-hugo-modules/tree/d4ecdca0eb969bb046067f175ce03dce9e0637d9/wowchemy/layouts/partials). Scroll down on this page until you find "navbar.html" and save the file.

<figure>
  <img src="github_2.png">
  <figcaption>Scroll down until you get to navbar.html</figcaption>
</figure>

If you don't know how to save files from GitHub, you can just click the filename, and then on the subsequent page, click the "raw" button, and then press ctrl + s to save the page as an html file.

<figure>
  <img src="github_1.png">
  <figcaption>This might be obvious, but it wasn't to me, at first!</figcaption>
</figure>

## 4
Now that you have the navbar.html file in your downloads, move it to that layouts/partials folder that you made before. Now, double click the file, and Atom should open it as a text document that you can edit. Look at line ~15:

        <nav class="navbar navbar-expand-lg navbar-light compensate-for-scrollbar" id="navbar-main">
          <div class="container-xl">

            {{if $show_logo}}
            <div class="d-none d-lg-inline-flex">
              <a class="navbar-brand" href="{{ "/" | relLangURL }}">

and, before it, copy and paste the BELOW chunk of code:

        <head>
          <link
            rel="stylesheet"
            href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
          />
        </head>

This will add Animate.css, a library of ready-to-use, cross-browser animations, directly to your page.

This portion of the file should now look like

>this

        <head>
          <link
            rel="stylesheet"
            href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
          />
        </head>

        <nav class="navbar navbar-expand-lg navbar-light compensate-for-scrollbar" id="navbar-main">
          <div class="container-xl">

            {{if $show_logo}}
            <div class="d-none d-lg-inline-flex">
              <a class="navbar-brand" href="{{ "/" | relLangURL }}">

Next step!

## 5
Navigate to your root folder, and look for the folder labeled "assets". Open it, and, if it doesn't exist, create a new folder within assets called "scss". Within the folder "scss", create a new file called "custom.scss"
Your directory should look exactly like this!
<figure>
  <img src="atom_2.png">
  <figcaption>Note: Ignore the wowchemy folder in my directory.</figcaption>
</figure>

## 6
Open custom.scss, and take a look at your beautifully empty file. Let's get to work. I'm no CSS expert, but it doesn't take a genius to get this next part done. Copy + paste the following code into the file, and save.

        .navbar {
          animation: wobble 2s cubic-bezier(0.83, 0, 0.17, 1) both;
        }

If you want a different effect than the one I used, just swap `wobble` for the effect you'd like! If you'd like the animation to be shorter/longer, change `2s`. I'm not quite sure what `both` does (the other two options are forward and backward), so just leave it alone unless you know what you're doing (I certainly don't).

## 7
Lovely! Save your work, and open GitHub desktop, and push your changes to origin. Navigate over to your netlify/deploy page, and wait for your homepage to update.

<iframe src="https://giphy.com/embed/Z4SvjxhzXkHEeTTFpW" width="480" height="74" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/Z4SvjxhzXkHEeTTFpW">via GIPHY</a></p>
