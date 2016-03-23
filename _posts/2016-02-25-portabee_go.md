---
layout: post
title: Running Portabee GO v1 from MacOs
category: nerdiness memo tips
comments: true

excerpt: I'm finally entering the world of 3D printing. After having printed a small piece and payed quite some money, I decided to go for neighbouring resources. A colleague of mine has a small Portabee Go v1, so I decided to try it out.

---

I'm finally entering the world of 3D printing. After having printed a small piece and payed quite some money, I decided to go for neighbouring resources. A colleague of mine has a small Portabee Go v1, so I decided to try it out.

Since it resulted quite hacky to get it printing something, I decided to take some notes for future reference.

Todo list:

* install software as documented by portabee (if you are under MacOs install 2014 version of printrun, the 2015 doesn’t work)
* open cura 
* open model
* export gcode
* from the created gcode remove line: M109 S210.000000
* remove also the last lines where the carried is moved to home position:
* open gcode in printurn
* (in printrun) 
* connect
* reset TWICE
* start the fan: M106
* set temperature
* print


Changing values of printing velocity in Cura helps a lot with the quality of the print (to be honest, quite low for this model of printer).
HTH


