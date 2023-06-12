---
title: "Shifting to Hugo"
date: 2023-06-10T21:49:49+05:00
author: "Ghassan Shahzad"
categories: 
  - General Guides
tags:
  - Website Development
  - Hugo
draft: true
---

I decided to shift my static Github Pages site to Hugo for a couple of reasons. First of all, I’d tried Jekyll a couple years back and admired the fact that, after a somewhat rough setup, it’s smooth sailing. My Jekyll site was barely touched after launch, except for whenever I created a new post. With my static site, I was always tinkering with something or the other. Another, more specific, benefit was templating and ‘partials’. For my static site, *whenever* I wanted to change my footer, I’d have to update it throughout every page I had. Maybe you can deal with this somehow, perhaps through JS, but I’m not in the mood to learn JS (currently I’m working on bringing my Python skills to scratch). 

This may lead you to a question, however. *Why did I go for Hugo instead of Jekyll then?*Well, because everyone (my go-to youtubers) use it!

## Start with a Theme!

You should consider Hugo themes as more than just a styling—they’re the base of a website. You have two options in this regards:

1. Create your own theme
2. Use one of Hugo’s many provided

I’m going to go through option 1 because it’s the one I took. I’d recommend it to you as well for a couple of reasons: it brings you far more knowledge of the ins and outs of Hugo than if you were to tinker with an existing theme, and it gives you a sense of accomplishment. 

To start, download Hugo. This is as simple as running `sudo dnf install hugo` if you’re on Fedora, like me. You should refer to the Hugo [docs](https://gohugo.io/documentation/) for your distro and any other distro-specific question you may have later. Once Hugo is installed

