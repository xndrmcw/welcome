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
## Alright, let's do this.

There I was, messing around on GitHub, looking at a list of the most starred repo's of all time. TensorFlow sat at #4. I've been putting off learning more about TensorFlow for a while now, so, in the spirit of writing another blog post, I thought now might be a good time to get familiar!

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

But Alexander, you might say,

## How does TensorFlow, a library of machine learning tools, help me as an amateur programmer?

Great question! If you're like me (a student,) you probably don't have much exposure to the many pragmatic uses of these tools! Don't worry, though - the internet is filled with information!

If you watched the videos from above, you're likely familiar with what a neural net is, how it works, and why it might be useful. If you didn't watch them, I suggest you reconsider!

Okay, so, assuming you've seen the video, you'll know what the MNIST database of handwritten digits is. If you don't, I'll do my best to explain it very simply. Take a look at the four numbers below:

<figure>
  <img src="mnist_digits.png">
  <figcaption>"The numbers Mason, what do they mean?""</figcaption>
</figure>

These are handwritten digits, uploaded as image files. They're 28 x 28 pixels, and each pixel in the image has a "light value" somewhere between 0 and 255. For example: the whitest pixels in the center of the image have a light value of 255. The darkest pixels on the outside have a light value of 0 (there's no light in those pixels, thus, no light value!)

<figure>
  <img src="mnist_5_values.png", height = "50%">
  <figcaption>Take a look at this image! You can see numbers in each pixel. These numbers range from 0 to 255, but we're going to transform those values in a little bit.</figcaption>
</figure>

There are 70,000 of these images, each painstakingly hand-labeled by a real person.

So, we have a huge collection of pictures of people's handwritten numbers, each with a corresponding label. What good is that, you might ask?

Well, with this dataset, we can use some tools to attempt to predict the label of each of the digits.

If we program our computer to take this image as an input:

<figure>
  <img src="mnist_5.png">
</figure>

Can we program it to predict the handwritten label that's associated with that image?

Let me rephrase:

## Can we teach a computer to recognize digits?

---
Short answer: yes.

Long answer: yeah, kinda. Can we, with a high degree of accuracy predict the labels associated with the images correctly? Yes, absolutely. In some cases, we can even get a 99% + degree of accuracy. Still, though, does the computer really "learn" what a 5 is? Does it know that 7 is one greater than 6? No.

All it "knows" is that certain pixel values and arrangements are associated with the labels it's been given. It's a smart labelling system, but that's all it is.

Does it really matter, though? Does a computer need to deeply "know" what those things are, in order for it to carry out commands? No, in this case, it doesn't. There would be no difference between a computer's performance in labelling and a human's.

Of course, there's a wide range of skills in which computers simply can't compare to humans.

<figure>
  <img src="landscape.png" height="50%">
  <figcaption>Here's something that might make you feel better! This is a map from Max Tegmark's book, Life 3.0, that illustrates the varying levels of difficulty that AI have performing certain tasks. It's an awesome book! Check it out. https://www.amazon.com/Life-3-0-Being-Artificial-Intelligence/dp/1101946598</figcaption>
</figure>

><p style="color:#ff9a17;">A computer can predict digits, do math, and win at chess, but it can't yet write consistently convincing and engaging literature. With time, though, who knows? Maybe your grandchild's favorite novel will be written by an intelligent machine at Google.</p>

---

So, now that we're familiar with the MNIST digits dataset, we can download the dataset, use some of the tools present in TensorFlow, and build ourselves a predictive model!

Instead of that, though, let's use a slightly more interesting dataset! The MNIST-Fashion database follows the exact same neural-net based process as the digit database, but rather than handwritten digits we have 70,000 hand-labelled images of clothing!

<figure>
  <img src="fashion_5x5.png" height="50%">
  <figcaption>Boom! They're a bit blurry, but that's to be expected when you're limited to a resolution of 28x28.</figcaption>
</figure>

TensorFlow provides a nice tutorial for building a predictive model using this model. Let's walk through it! Get ready for some `code!`

><p style="color:#ff9a17;">First, let's import the packages we need. If you don't have any of these installed, a quick google search will help you.</p>

        import tensorflow as tf
        import numpy as np
        import matplotlib.pyplot as plt

><p style="color:#ff9a17;">Next, we'll load in the dataset!</p>

        fashion_mnist = tf.keras.datasets.fashion_mnist

><p style="color:#ff9a17;">Now, we'll use the load.data function. This call returns four values, so let's assign them to two tuples. </p>

        (train_images, train_labels), (test_images, test_labels) = fashion_mnist.load_data()

><p style="color:#ff9a17;">Cool! Let's also create a list of label names. The MNIST-fashion dataset only labels its  images with "1", "2",..."9", so let's add some actual words, so we know what we're looking at.</p>

        class_names = ['T-shirt/top', 'Trouser', 'Pullover', 'Dress', 'Coat',
                       'Sandal', 'Shirt', 'Sneaker', 'Bag', 'Ankle boot']

><p style="color:#ff9a17;">As a quick check that we're on the right track, let's check how many images we have, as well as the dimensions of said images.</p>

        print(train_images.shape)
        (60000, 28, 28)

><p style="color:#ff9a17;">Lovely! We have 60,000 images in our training set, all of dimension 28x28. Let's see what they look like! </p>

        plt.figure()
        plt.imshow(train_images[0])
        plt.colorbar()
        plt.grid(False)
        plt.show()

<figure>
  <img src="boot_plot.png">
  <figcaption>Take a look! Matplotlib defaults to using the viridis color scheme, but the original images are in a binary color scheme (black and white).
  How do we interpret the viridis scheme? Well, per the legend, if a pixel in the image is yellow, it has a light value of 255, and if it's purple, it has a light value of 0.</figcaption>
</figure>

><p style="color:#ff9a17;">I mentioned this before, but we want our range of pixel values to be from 0 to 1, not 0 to 255. So, let's divide!</p>

        train_images = train_images / 255
        test_images = test_images / 255

><p style="color:#ff9a17;">Awesome! Now we can build our model. This part of the code is a bit abstract, so I'm going to include a gif from 3Blue1Brown's video to attempt to showcase what's going on.</p>

        model = tf.keras.Sequential([
            tf.keras.layers.Flatten(input_shape=(28,28)),
            tf.keras.layers.Dense(128, activation='relu'),
            tf.keras.layers.Dense(10)

><p style="color:#ff9a17;">Okay, see where it says flatten? The gif below shows what "flatten" means in this context. Basically, instead of having a square image that's 28x28, we're going to transform the square into a single row, of length 784. If this doesn't make sense, watch the video! It's explained eloquently there.</p>

`{{< figure src="./flatten_gif.gif" link="./flatten_gif.gif" >}}`

><p style="color:#ff9a17;">From my limited understanding, the two "Dense" lines correspond to the last two layers of the neural net. Why 128 and 10? I don't know. Maybe someday I will, though!</p>

><p style="color:#ff9a17;">Next, we need to tweak a few settings, before we apply our model to the dataset. Optimizer, loss, and metrics are all parameters that you can configure if you know what you're doing. If you're like me, and you don't, just leave them be. At a very basic level, we want to minimize loss and have a reasonably high degree of prediction accuracy. Let's run the code and see what we get!</p>

        model.compile(optimizer='adam',
                      loss=tf.keras.losses.SparseCategoricalCrossentropy(from_logits=True),
                      metrics=['accuracy'])
        model.fit(train_images, train_labels, epochs=10)       
        Epoch 1/10
        1875/1875 [==============================] - 3s 1ms/step - loss: 0.6306 - accuracy: 0.7799
        Epoch 2/10
        1875/1875 [==============================] - 2s 1ms/step - loss: 0.3876 - accuracy: 0.8597
        ---
        Epoch 10/10
        1875/1875 [==============================] - 2s 1ms/step - loss: 0.2411 - accuracy: 0.9084
        313/313 - 0s - loss: 0.3499 - accuracy: 0.8750      

><p style="color:#ff9a17;">As you can see, the last epoch of our model achieved an accuracy rating of 90.84%! An epoch is just a training attempt. Let's see how our model does when we apply it to the test set! This is the part of the dataset that we left out, so the model has never seen it before.</p>

        test_loss, test_acc = model.evaluate(test_images, test_labels, verbose=2)
        print("\nTest Accuracy:", test_acc)
        Test Accuracy: 0.875

><p style="color:#ff9a17;">The model performs slightly worst on the test data (90.84% on training vs 87.5% on test.) This is to be expected!</p>
><p style="color:#ff9a17;"></p>
><p style="color:#ff9a17;"></p>



With TensorFlow, you can train a model to predict digits yourself! That's pretty cool, but the TensorFlow documentation page suggests you trying something with a bit more spice.
