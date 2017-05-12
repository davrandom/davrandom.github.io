---
layout: post
title: Photo collage on linux
tags: []
categories: en photo collage linux
---
I was struggling searching for a software that made a collage from my pictures, mimicking a photo… and today I succeeded:

![]({{ root_url }}/images/5.jpg)

It’s not really something to be proud but it’s indeed a starting point.
The instructions are well described [here](http://linuxaria.com/article/photo-collage-mosaic-linux?lang=en) .

**As an example:**
to prepare the pictures

     $ metapixel-prepare -r sourcefolder destinationfolder --width=48 --height=48 

to create the mosaic

     $ metapixel --metapixel input.jpg output.png -l destinationfolder -s 10 

there are many options you can add. Try typing *metapixel* in your bash :)

ps: the [picture](http://www.flickr.com/photos/davrandom/6806261137/in/photostream) is taken from my [flickr account](http://www.flickr.com/photos/davrandom/)
