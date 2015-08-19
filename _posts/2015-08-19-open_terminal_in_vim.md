---
layout: post
title: Open a terminal IN Vim
tags: [memo, tips]
category: memo
comments: true

excerpt: Sometimes you really want to open a terminal IN Vim. Here is how you do that!

---

I was searching for a way to open a shell in Vim and I got many answers.
Essentially all the juice is listed [here](http://stackoverflow.com/questions/1236563/how-to-run-a-terminal-inside-of-vim).
First I will list the ones that are possible but that are not *my* answer:

```bash
:! somecommand [ENTER]
```

or

```bash
:! bash (or your favourite shell) [ENTER]
```

But no... this is not what I wanted. I wanted a *real* terminal **inside** (a tab of) **Vim**... so the answer is [ConqueTerm](https://code.google.com/p/conque/). Enjoy!

HTH

d
