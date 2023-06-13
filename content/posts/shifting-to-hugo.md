---
title: "Shifting to Hugo"
date: 2023-06-10T21:49:49+05:00
author: "Ghassan Shahzad"
categories: 
  - General Guides
tags:
  - Website Development
  - Hugo
  - Github Pages
draft: true
---

I decided to shift my static **Github Pages** site to Hugo for a couple of reasons. First of all, I’d tried Jekyll a couple years back and admired the fact that, after a somewhat rough setup, it’s smooth sailing. My Jekyll site was barely touched after launch, except for whenever I created a new post. With my static site, I was always tinkering with something or the other. Another, more specific, benefit was templating and ‘partials’. For my static site, *whenever* I wanted to change my footer, I’d have to update it throughout every page I had. Maybe you can deal with this somehow, perhaps through JS, but I’m not in the mood to learn JS (currently I’m working on bringing my Python skills to scratch). 

This may lead you to a question, however. *Why did I go for Hugo instead of Jekyll then?*Well, because everyone (my go-to youtubers) use it!

## Start with a Theme!

You should consider Hugo themes as more than just a styling—they’re the base of a website. You have two options in this regards:

1. Create your own theme
2. Use one of Hugo’s many provided

I’m going to go through option 1 because it’s the one I took. I’d recommend it to you as well for a couple of reasons: it brings you far more knowledge of the ins and outs of Hugo than if you were to tinker with an existing theme, and it gives you a sense of accomplishment. If you want to use someone else’s theme, most of them have instructions on how to create a new site and add their theme. Otherwise, refer to [this](https://gohugo.io/getting-started/quick-start/) Hugo guide (and tweak as necessary).

To start, download Hugo. This is as simple as running `sudo dnf install hugo` if you’re on Fedora, like me. You should refer to the Hugo [docs](https://gohugo.io/documentation/) for your distro and any other distro-specific question you may have later. Once Hugo is installed, you need to run two commands:

```bash
hugo new site MYSITE
hugo new theme MYTHEME
```

where MYSITE and MYTHEME are the names of your to-be website and its theme. CD into your site and open the `config.toml` file. There are a couple of options you should set right off the bat:
```toml
baseURL = 'https://ghassbomb.github.io/'
languageCode = 'en-us'
title = 'Ghassan Shahzad'
theme = 'shahugo'
author = 'Ghassan Shahzad'
```

I personally also like to set a couple of other options:

```toml
[params]
	description = 'A blog and a portfolio in equal measure, with book notes, content reviews, and history, among other interests…'

[taxonomies]
  category = 'categories'
  tag = 'tags'

[frontmatter]
	date = ['date']
	publishDate = ['publishDate']

[markup.goldmark.renderer]
	unsafe= true

[menu]
  [[menu.main]]
    name = "Home"
    url = "/"
    weight = 1
  [[menu.main]]
    name = "Archives"
    url = "/archives"
    weight = 2
  [[menu.main]]
    name = "Projects"
    url = "https://github.com/ghassbomb"
    weight = 3
  [[menu.main]]
    name = "Tags"
    url = "/tags"
    weight = 4
  [[menu.main]]
    name = "Categories"
    url = "/categories"
    weight = 5
  [[menu.main]]
    name = "About"
    url = "/about"
    weight = 6
```

Let’s explain what the purpose of this file is first. The `config.toml` is basically a global variable dump. When you have certain things you have to set in your site templates code, but you don’t wanna go deep into the files every time you wanna change it, you just use Hugo’s templating language and place one of the variables defined in `config.toml` instead. This is also necessary if you wanna publish your theme, so that your theme users don’t have to get their hands dirty.

Now onto the options themselves: the first codeblock is self-explanatory. Asides from the author variable, all of these are default variables. The base url is used for things like HREFs, and title is of course for your head and headers. The theme variable allows you to choose which theme you want to deploy the site with—you might have multiple in your themes folder. You can also specify a theme using the `hugo -t THEMENAME` command instead. The author variable is used (by me) as a default variable to put in markdown frontmatters. It is not strictly necessary unless you’d like to have author names in your posts.

The `[params]` ‘category’ is basically where you will define **all** of your custom variables. For now, it contains the description variable which we will use as a meta description and in our homepage. The taxonomies variable basically defines what sort of ways you want to sort and group your content. Personally, I put one broad ‘category’ for each article—this one has the ‘General Guides’ category—and then an assortment of tags to clear things up a bit. The `[frontmatter]` category is a bit of a messy hack on my part, and I will leave it out. The `[markup.goldmark.renderer]` variable is used to render HTML specified in Markdown files. Finally, I’ve created a sort of ‘list’ of menu files that I will have Hugo’s templating language loop over to create my navbar.

For now, we’re done with the site itself. CD into `themes/THEMENAME` and let’s mess around with the `templates` folder. The templates folder basically contains the HTML base for your site. It is scattered over a bunch of files, however, which are tied together using Hugo’s templating language—a glue language, basically.

```bash
./layouts
├── 404.html
├── _default
│   ├── baseof.html
│   ├── list.html
│   ├── _markup
│   │   └── render-link.html
│   └── single.html
├── index.html
├── partials
│   ├── footer.html
│   ├── header.html
│   ├── head.html
│   └── metadata.html
└── shortcodes
    └── archive.html 
```

For customizing this stuff, refer to zeolearn’s [guide](https://www.zeolearn.com/magazine/develop-a-theme-for-hugo). But, once you’re done, you can move over to the `/static` folder. This is where you will leave your images, CSS, fonts, JS, etc. Create a `css` folder and a `style.css` file within. This you can customize as you would normally. My CSS file is just plain CSS. Asides from FontAwesome, I also use no JS—Hugo’s templating covers all my needs in regards to scripting. You should also paste your `favicon.ico` into this folder.

