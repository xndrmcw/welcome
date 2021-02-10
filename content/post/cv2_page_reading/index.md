---
title: OpenCV is so cool. This post is short, but (to me at least) magical.

image:
  focal_point: ""
  placement: 2
  preview_only: True

# Link this post with a project
projects: []

# Date published
date: "2021-02-09T00:00:01Z"

# Date updated
lastmod: "2021-02-09 T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: true

design:
  columns: '2'

links:
- icon: youtube
  icon_pack: fab
  name: sentdex's video
  url: https://www.youtube.com/watch?v=jXzkxsT9gxM&list=PLQVvvaa0QuDdttJXlLtAJxJetJcqmqlQq&index=6

- icon: github
  icon_pack: fab
  name: My Code
  url: https://github.com/xndrmcw/lifespan_viz



authors:
- admin

tags: ['Computer Vision']


---
## Oh, the things computers enable us to do.

<figure>
  <img src="bookpage.jpg">
</figure>

## Take a look at this image. Can you read what it says? Not really, right? Well, check this out. With the following chunk of `code`...

        import cv2
        import numpy as np

        img = cv2.imread('bookpage.jpg')
        retval, threshold = cv2.threshold(img, 12, 255, cv2.THRESH_BINARY)

        grayscaled = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

        gaus = cv2.adaptiveThreshold(grayscaled, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY,
                             115, 1)

        cv2.imshow('gaussian', gaus)

        cv2.waitKey(0)
        cv2.destroyAllWindows()

## Now you can!

<figure>
  <img src="gaussian.jpg">
</figure>

## Isn't that sick? Thanks to sentdex for the awesome video series on using CV2.
