---
layout: post
title: Repositories for Science software on Linux
tags: []
categories: en science software
---
(preamble: I do many things over the web every day, search for solutions, find solutions, implement solutions… then I forget everything. So some posts like this are just a collection of things for future memory)

Not always the ubuntu official repository has the newest software. Fortunately there are some people compiling the latest source code and sharing the packages. There are several technical options to achieve this. One “official” solution for Ubuntu is [lauchpad,](launchpad.net) where you can find many repositories with a lot of software.

In particular you may be interested in Maxima and Octave.

for **wxMaxima**:
\* you may want to read this first: https://help.ubuntu.com/community/Maxima
\* this is the repositoy in lauchpad https://launchpad.net/\~blahota/+archive/wxmaxima/+packages
\* and this is essentially the lines that you can cut and paste on your terminal to have the latest wxmaxima:

    sudo apt-add-repository ppa:blahota/wxmaxima
    sudo apt-get update
    sudo apt-get install wxmaxima

for **octave**:
\* this is the repositoy in lauchpad https://launchpad.net/\~mvanderkolff/+archive/octave-3.6
\* and this is essentially the lines that you can cut and paste on your terminal to have the latest wxmaxima:

    sudo apt-add-repository ppa:mvanderkolff/octave-3.6
    sudo apt-get update
    sudo apt-get install octave

for **latest texlive**

    sudo add-apt-repository ppa:texlive-backports/ppa
    sudo apt-get update
    sudo apt-get install texlive

Hope this helps
d
