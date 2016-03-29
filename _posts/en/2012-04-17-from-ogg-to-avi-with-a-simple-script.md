---
layout: post
title: From ogg to avi with a simple script
tags: []
categories: en scripts linux
---
A strange thing is that avidemux works with many video and audio formats, but not our beloved ogg. So some time ago searching around the web for a method to convert a ogg into some avi format and I found a small script. Since data corruption si always possible, I post the solution to the web for future memory.

If you want to **convert only one file at time**

    mencoder oggfilename.ogg -ovc xvid -oac mp3lame -xvidencopts pass=1 -o avifilename.avi

If you want to **convert a batch of files**

    #!/bin/bash <br>
    # ogv to avi <br>
    # Call this with multiple arguments <br>
    # for example : ls *.{ogv,OGV} | xargs ogv2avi <br>
    N=$#; <br>
    echo "Converting $N files !" <br> 
    for ((i=0; i<=(N-1); i++)) <br>
    do <br>
    echo "converting" $1 <br>
    filename=${1%.*} <br>
    mencoder "$1" -ovc xvid -oac mp3lame -xvidencopts pass=1 -o $filename.avi <br>
    shift 1 <br>
    done

where ogv2avi is the name of this script. (If its usage is not obvious, just ask)

Note: This is not my product, so the credit goes to someone else (don’t know who… I found this some years ago).
