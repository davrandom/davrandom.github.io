---
layout: post
title: Speech recognition under Linux
tags: []
categories: en linux applications
---
(preamble: I do many things over the web every day, search for solutions, find solutions, implement solutions… then I forget everything. So some posts like this are just a collection of things for future memory)

I was searching for something like Dragon Naturally Speaking under Linux… well this doesn’t seem to exist yet (apart from running DNS under wine). If you have different information please comment.

I found this [nice article on Archlinux wiki](https://wiki.archlinux.org/index.php/Speech_Recognition#Speech_Recognition) with a nice list divided by types of speech recognition (copying from there):

-   **Text-To-Speech** As it sounds, Text-To-Speech (or TTS) will manipulate a string of text into an audio clip. There are several programs available that perform TTS, some of which are command-line based (ideal for scripting) and others which provide a handy GUI.

-   **Simple Voice Control/Commands** This is the most basic form of Speech-To-Text application. These are designed to recognize a small number of specific, typically one-word commands and then perform an action. This is often used as an alternative to an application launcher, allowing the user for instance to say the word “firefox” and have his OS open a new browser window.

-   **Full dictation/recognition** Full dictation/recognition software allows the user to read full sentences or paragraphs and translates that data into text on the fly. This could be used, for instance, to dictate an entire letter into the window of an email client. In some cases, these types of applications need to be trained to your voice and can improve in accuracy the more they are used.

I am mostly interested in the last one … from what I can understand none of them is yet completely working (in the sense of DNS does).
I downloaded [Simon](http://simon-listens.org/) but not tried yet. From what I can see [here](http://simon-listens.blogspot.it/2012/05/simon-usability.html) they’re at 0.3.80 release while [here](http://sourceforge.net/projects/speech2text/) you can download the 0.3.0 version… guess some svn/git compiling is required to obtain the most recent version.

Quoting from [here:](http://en.wikipedia.org/wiki/Speech_recognition_in_Linux)
“Recently, there has been a push to get a high-quality native GNU/Linux speech recognition engine developed. As a result, numerous projects dedicated to creating GNU/Linux speech recognition solutions were established. One major hurdle is the compilation of a speech corpus to enable production of acoustic models. In response, VoxForge, which aims to collect transcribed speech for the use with free and open-source speech recognition engines under the GPL license, was set up.”
*\_
I gave a look also to [VoxForge](http://www.voxforge.org/) and it’s a project to*collect\_ transcribed speech, to build up open source “speech libraries” ([speech corpus](http://www.voxforge.org/home/docs/faq/faq/what-is-a-speech-corpus-or-speech-corpora)). So this is only a piece of what I’m searching for, but it’s important to mention that **everyone can help this project simply reading some text**… [checkout here.](http://www.voxforge.org/home/read)

**Has anyone there an experience with OSS software doing full dictation/recognition?**
