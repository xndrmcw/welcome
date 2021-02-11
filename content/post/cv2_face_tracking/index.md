---
title: Face & Eye Tracking with CV2!

image:
  focal_point: ""
  placement: 2
  preview_only: True

# Link this post with a project
projects: []

# Date published
date: "2021-02-10T00:00:01Z"

# Date updated
lastmod: "2021-02-10 T00:00:00Z"

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
  url: https://www.youtube.com/watch?v=88HdqNDQsEk&list=PLQVvvaa0QuDdttJXlLtAJxJetJcqmqlQq&index=16


authors:
- admin

tags: ['Computer Vision', 'CV2']


---
## If you're as unfamiliar with cv2 as I was before this project, I think this'll be cool to look at.

<figure>
  <img src="face_tracking.gif">
</figure>

## Boop! The accompanying `code`...

        import cv2
        import numpy as np

        face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_alt.xml')
        eye_cascade = cv2.CascadeClassifier('haarcascade_eye.xml')

        cap = cv2.VideoCapture(0)

        while True:
            ret, img = cap.read()
            gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
            faces = face_cascade.detectMultiScale(gray, 1.3, 5)
            for (x,y,w,h) in faces:
                cv2.rectangle(img, (x,y), (x+w, y+h), (255, 0, 0), 2)
                roi_gray = gray[y:y+h, x:x+w]
                roi_color = img[y:y+h, x:x+w]
                eyes = eye_cascade.detectMultiScale(roi_gray)
                for (ex, ey, ew, eh) in eyes:
                    cv2.rectangle(roi_color, (ex, ey), (ex+ew, ey+eh), (255, 255, 255), 2)
            cv2.imshow('img', img)
            k = cv2.waitKey(30) & 0xff
            if k == 27:
                break

        cap.release()
        cv2.destroyAllWindows()

## How sick is that? Again, thanks to sentdex, as well as the opencv documentation team (whoever you are!)
