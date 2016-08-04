---
layout: post
title: Apfter updating ruby gems jekyll stops working
category: web metapost memo
comments: true


---

Today I updated the ruby gems because I installed a new gem and thought that it passed a long time since the last time I updated them...

The rule should be 'if it works, don't touch it'... but... I did.

Searching for a solution, I actually [found one](https://talk.jekyllrb.com/t/updated-gems-now-jekyll-auto-regenerate-is-broken/1574/5)!

To fight obsolescence I will copy anthonyjsmith solution here:

*As you're building a GitHub Pages site, I suggest making a file in the same folder as _config.yml called Gemfile with this as the contents:*

```
source 'https://rubygems.org'
gem 'github-pages'
```

*Then run these commands:*

```
gem install bundler
bundle install
bundle exec jekyll serve -V
```

*The bundle exec in the last command makes sure you run the same version of Jekyll as on GitHub Pages, and the -V gives verbose output, which might give you some clues if things go wrong.*

The End. HTH
