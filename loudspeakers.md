---
layout: page_w_picture
title: "Loudspeakers"
comments: true
sharing: true
footer: true
image: "loudspeakers_small.jpg"
---


## Table of Contents
1. [Intro](#Intro)
2. [Zero model](#Zero model)
3. [One model](#One model)


<a name="Intro"></a>

## Intro

Here I will publish my loudspeakers' designs with as much detail as possible. If you have questions or feel that some detail is missing, feel free to ask in the comments section below.

The name I chose for my loudspeakers, **/ear/nest**, should explain clearly what is the philosophy: they are **Earnest**, *honest*, I will publish as much details, measurements, ... as I can, and they are possibly *good*, an "**ear nest**".

<dl>
<a data-flickr-embed="true"  href="https://www.flickr.com/photos/davrandom/albums/72157671398454785" title="/ear/nest"><img src="https://c8.staticflickr.com/9/8399/28472807135_652047889c.jpg" width="500" height="281" alt="/ear/nest"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>
</dl>


<a name="Zero model"></a>

## Zero model

![model Zero (terrible mobile phone picture...)](https://farm2.staticflickr.com/1588/25864464542_67f3732361.jpg)

Sorry for the terrible picture, I will take some better ones soon.

The idea here was to prove that, with the limited tools I have, I am able to cut the wood, glue the box, cut a hole, mill the borders, screw the transducer and paint the whole thing. Given the size of the box, the target was to create a couple of surrounds and a central loudspeaker for my home theater. The expectations weren't too high, but after trying them in our critical listening room we were surprised and pleased by the incredible detail of the stereo image. For this reason I gave them to a couple of friends and I hope they will write a small review and I will probably carry out some measurements.


### Hardware
* [Tymphany TC9FD18-08 3-1/2"](http://www.parts-express.com/tymphany-tc9fd18-08-3-1-2-full-range-paper-cone-woofer--264-1062) full range paper cone woofer (from Parts Express)
* 1 cm thick plywood (from local LeRoy Merlin)
* [Square speaker wire spring terminal cup](http://www.parts-express.com/parts-express-square-speaker-wire-spring-terminal-cup--260-297) (from Parts Express)

### Design
It is a simple 12 cm cube (outer dimensions). The transducer is mounted from the inside, because it's meant to be like that.
The design is quite common, for example see Auratone (bigger) or Grover Notting CR-1 (same transducer size, smaller box 11 cm).

### Specs
![decent plots to be done](https://bytebucket.org/davrandom/misc_projects/raw/30d51c10abc1140003f4a449371c74b69c25cc8f/loudspeakers/zero/80dBC_2048taps_nosmooth.png)

I know I shouldn't publish a plot like this for a couple of reasons:

* People normally do smoothing to make their spectrum nicer (and in some areas of the spectrum it makes sense, because the window of the fourier transform has a fixed width and hence its resolution df/f it's frequency dependent).
* People normally do things to achieve a flat spectrum: e.g. adding passive filters, try several box designs. 

This is not my case, I was just curious to know if I was able to make a box and paint it, and by chance it also sounded. In the process I didn't cut any of my fingers! Unbelievable! The box is there and sounds surprisingly better than expected.
Now... yes it could be better. Having the time to make it better, the loudspeaker would benefit from having a passive filter to lower the peak around 2kHz. Or if you have a dsp before the speaker, you can measure and fix the thing easily.

Now, since this is an /ear/nest design, here you are a [link to the loudspeaker IR](https://bitbucket.org/davrandom/misc_projects/raw/30d51c10abc1140003f4a449371c74b69c25cc8f/loudspeakers/zero/80dBC_IR.wav) measured "close miking" (1m) the speaker by Xavi. Better measurements will come in the future...

### Comments
(waiting for comments from my testers...)

<a name="One model"></a>



## One model

![preliminary picture of One model](https://c6.staticflickr.com/9/8852/28472805085_358800bc17.jpg)

### Hardware
* MA 5.5" carbon fiber woofer (custom design), resonance at 50 Hz, 8 Ohm impedance
* [Sica LP 90.28 / N92 TW](http://www.sonoraspeakers.it/lp-90-28-n92-tw.html), 8 Ohm impedance
* 2x125 W B&O D-class amplifier [ICEpower 125ASX2](http://www.icepower.bang-olufsen.com/files/solutions/icepower125asx2_datasheet_1_3_20151203.pdf)
* 2 ch DSP by [freedsp](http://www.freedsp.cc)
* 1.9 cm thick MDF

Detailed specs to be published...

### Design
Two way bi-amplified active speaker with DSP, in a front-vented box.

Size: 22 cm W x 52 cm H x 36 cm D

### Pictures


### Electronics and related parts

#### Supports for DSP and amplifier

![DSP and amplifier supports](https://farm6.staticflickr.com/5708/30495918136_f4bfd6b863_b.jpg)

[(Link to others sizes of the same image.)](https://flic.kr/p/NsPy11)

The picture shows the freedsp classic board, the ice amplifier and two black supports. The supports are designed in openscad and printed with a BCN3D+ printer. The scad and stl are available here (put link).

If you don't have a 3D printer, I can print them for you. 