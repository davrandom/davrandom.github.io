---
layout: post
title: Texmaker can’t find dictionary
tags: []
categories: en latex science software howto
---
Today I am —desperately— writing a report. I have time until midnight.
Obviously I have to work from home, with a different pc. And obviously I’m running into some missing pieces ;)

First problem, Texmaker complains about missing dictionary.
Googling around I found two interesting pages:
[Texmaker Error : Can’t open the dictionary](http://copiancestral.wordpress.com/2012/02/13/texmaker-error-cant-open-the-dictionary/) by *copiancestral*
[Configuring the spell checker](http://www.xm1math.net/texmaker/doc.html#SECTION03)

Carefully brewing the two I found my solution.

### First: locate your dictionary .aff

(You need findutils installed)
So type in your terminal

    locate *.aff

You should get a list of dictionaries like this (depending on your installation):

    elijah@seldon:~$ locate *.aff
    /usr/share/hunspell/en_AU.aff
    /usr/share/hunspell/en_GB.aff
    /usr/share/hunspell/en_US.aff
    /usr/share/hunspell/en_ZA.aff
    /usr/share/hunspell/es.aff
    /usr/share/hunspell/it_IT.aff
    /usr/share/myspell/dicts/en-GB.aff
    /usr/share/myspell/dicts/en_GB.aff
    /usr/share/myspell/dicts/en_ZA.aff
    /usr/share/myspell/dicts/it-IT.aff
    /usr/share/myspell/dicts/it_IT.aff

If not you have to install the desired myspell dictionary with your preferred package manager.

### Then: tell Texmaker where to find the correct .aff file

Open *Configure Texmaker* \> *Editor* \> *Spelling dictionary* and put the path to the desired **.aff file**.
It should work now.
