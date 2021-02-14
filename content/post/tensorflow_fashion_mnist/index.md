---
title: Getting to Know TensorFlow with Zalando's Fashion-MNIST Dataset.

image:
  focal_point: ""
  placement: 2
  preview_only: True

# Link this post with a project
projects: []

# Date published
date: "2021-02-11T00:00:01Z"

# Date updated
lastmod: "2021-02-11 T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: true

design:
  columns: '2'

links:
- icon: laptop-code
  icon_pack: fas
  name: TensorFlow Tutorial
  url: https://www.tensorflow.org/tutorials/keras/classification
- icon: github
  icon_pack: fab
  name: Zalando's MNIST-Fashion Github Repo
  url: https://github.com/zalandoresearch/fashion-mnist


authors:
- admin

tags: ['Keras', 'TensorFlow', 'Machine Learning', 'Image Classification']


---
## Okay, here we go.

There I was, tooling around on GitHub. I was looking at a list of the most starred repos of all time, just for fun. There, to my excitement, at #4 all-time, sat TensorFlow. I've heard it mentioned plenty of times (youtube, stackoverflow, etc), and, as such, knew that I should probably have some degree of familiarity. So, I decided to familiarize myself!

## But where to start?

><p style="color:#ff9a17;">I guess a place as any would be with a working definition of what exactly TensorFlow is, and how it came to be.</p>

## So, what is TensorFlow?

TensorFlow is an open-source software library for machine learning.

><p style="color:#ff9a17;">Well, okay, cool, but what does that really *mean*? I'll try my best to break it down...</p>

Back in the early 2010's, Google Brain (a team of very smart AI researchers at Google) put together a compendium of machine learning tools. It was used widely by programmers at Google in both research and commercial capacities. It was called...

## DistBelief

><p style="color:#ff9a17;">TensorFlow is a cooler name, IMO. So, anyway, what does all that stuff above mean?</p>

Put simply: DistBelief was pretty good at what it did. What exactly did it do? Hard to say. But Google's engineers liked to use it.

><p style="color:#ff9a17;">But, as with anything, there was room for improvement. So. Google execs assigned a few academic studs to make DistBelief into something that was Dist-Unbelieveable! Sorry... Anyways, Jeff Dean was one of those folk, although there were certainly other computer scientists working their tushies off as well! Jeff and the team transformed DistBelief into...</p>


<figure>
  <img src="featured.png">
  <figcaption>TensorFlow!</figcaption>
</figure>


><p style="color:#ff9a17;">This new version of DB was faster and more robust. After a few years, Google released TensorFlow 1.0 to the public! You can install and import it with your favorite Python IDE, as well as C++, Java, and a  few others.CHeck it out @ https://www.tensorflow.org/learn</p>


Once it's imported, you have access to a bunch of fancy-shmancy machine learning tools! You can build, deploy, and make predictions with models, all from the comfort of your laptop! It's pretty sweet, honestly.

## Quick side note! This video series on neural networks by 3Blue1Brown is amazing! He makes complex subjects digestible and exciting. I highly recommend.
[![Video 1!](https://img.youtube.com/vi/aircAruvnKk/0.jpg)](https://www.youtube.com/watch?v=aircAruvnKk)

## But Alexander,

you might say,

## How does TensorFlow, a library of machine learning tools, help me as an amateur programmer?

Great question! If you're like me (a student,) you probably don't have much exposure to pragmatic uses of these tools! This isn't a problem, though - the internet is filled with information!

If you watched the videos from above, you're likely familiar with what a neural net is, how it works, and why it might be useful. If you didn't watch them, I suggest you reconsider!

Okay, so, assuming you've seen the video, you'll know what the MNIST database of handwritten digits is. If you don't, I'll do my best to explain it very simply. Take a look at the four numbers below:

<figure>
  <img src="mnist_digits.png">
  <figcaption>"The numbers Mason, what do they mean?""</figcaption>
</figure>

These are handwritten digits, uploaded as image files. They're 28 x 28 pixels, and each pixel in the image has a "light value" somewhere between 0 and 1. For example: the whitest pixels in the center of the image have a light value of 1. The darkest pixels on the outside have a light value of 0 (there's no light in those pixels, thus, no light value!)

There are 70,000 of these images, each painstakingly hand-labeled by a real person.

So, we have a huge collection of pictures of people's handwritten numbers, each with a corresponding label. What good is that, you might ask?

Well, with this dataset, we can use some tools to attempt to predict the label of each of the digits.

If we program our computer to take this image as an input:

<figure>
  <img src="mnist_5.png">
</figure>

Can we program it to predict the label that's going to be associated with that image?

## Can we teach a computer to recognize digits?

Short answer: yes.

Long answer: yes, but not really. We can, with a high degree of accuracy (99%+ with some algorithms) predict the labels associated with the images correctly. But, does the computer really "learn" what a 5 is? Does it know that 7 is one greater than 6? No, not really. It knows that certain pixel values correspond to 5's, 6's, and 7's, but, in this case, that's all. It's a smart labelling system, but that's all.

Does it really matter, though? Does a computer need to deeply "know" what those things are, in order for it to carry out commands? No, in this case, it doesn't. There would be no difference between a computer's performance in labelling and a human's.

Of course, there are things that humans can do that computers just can't compare to yet.

<figure>
  <img src="landscape.png" height="50%">
  <figcaption>Here's something that might make you feel better! This is a map from Max Tegmark's book, Life 3.0, that shows the difficulty that AI has with varying problems. The tasks with the highest elevation are AI design, Science, and Theorem Proving. Awesome book! Check it out. https://www.amazon.com/Life-3-0-Being-Artificial-Intelligence/dp/1101946598</figcaption>
</figure>

With TensorFlow, you can train a model to predict digits yourself! That's pretty cool, but the TensorFlow documentation page suggests you trying something with a bit more spice.
