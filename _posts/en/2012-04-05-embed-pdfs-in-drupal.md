---
layout: post
title: Embed PDFs in Drupal
tags: []
categories: en pdf drupal
---
(preamble: I do many things over the web every day, search for solutions, find solutions, implement solutions… then I forget everything. So some posts like this are just a collection of things for future memory)

I am developing a website with Drupal and the client asked me if it is possible to embed a PDF viewer in a Drupal node (ok the question was not *that* precise …). I always answer “everything is possible… we have to understand if you need that!” … but this is another story.

So my problem is almost the one described [here.](http://drupal.org/node/154009)
There are several solutions (right now I have tried none of them), depending on the Drupal version you are using. For Drupal 7 there is a [straightforward solution,](http://drupal.org/project/pdf_reader) while for Drupal 6 is not so easy… I will talk then about Drupal 6.

One possible solution is to use [SWF tools](http://drupal.org/project/swftools) together with [FlexPaper.](http://flexpaper.devaldi.com/docs.htm) The trick is to “convert” the pdf to a swf via FlexPaper and then use ‘SWF tools’ module to display the swf produced by FlexPaper. This is not really easy to implement inside Drupal ([see this comment](http://drupal.org/node/154009#comment-4356032) that redirects to this [issue for swf tools](http://drupal.org/node/759198)).

Another possible solution is the [fileviewer module](http://drupal.org/project/fileviewer) … that later became the [PDF module](http://drupal.org/project/pdf_reader) for Drupal 7. I really don’t know if it works on Drupal 6… I will try the fileviewer module first, and then give a try to the fexpaper+swf tools.

HTH
d
