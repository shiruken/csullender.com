+++ 
draft = true
date = 2020-01-29T16:09:37-06:00
title = "Goodbye WordPress. Hello Hugo."
tags = ['Web', 'Design', 'Software', 'Tips & Tricks']
+++

After eight years of [using WordPress]({{< relref "hello-world" >}}), I finally decided it's time to rid myself of the [cumbersome, error-prone beast](https://www.quora.com/Why-is-WordPress-so-bad-and-are-there-any-real-alternatives) in favor of a static website. I rarely post blog entries anymore, so the convenience of the WordPress text editor and dynamic content has lost its appeal, especially since this website now primarily serves as a digital portfolio. After far too much research (i.e. perusing Reddit threads), I decided to use a static site generator to create and maintain the new website.

I already have some experience with static site generators, since my [Science GIFs archive](https://sciencegifs.csullender.com/) uses [GitHub Pages](https://pages.github.com/), which is powered by [Jekyll](https://jekyllrb.com/). As I was learning about the transition from WordPress, I ran across another Markdown-based static site generator called [Hugo](https://gohugo.io/) that claimed to be the "world's fastest framework for building websites." Unlike Jekyll, which requires Ruby to operate, Hugo is a compiled [Go](https://golang.org/) program that only requires the download of a single binary for easy setup regardless of operating system. While build times are irrelevant for small websites such as my own, I figured it would be a good experience trying a completely new framework.

![Hugo Logo](Hugo_Logo.png)

# Hugo Setup

Thanks to the magic of the [Homebrew](https://brew.sh/) package manager for macOS, installing Hugo is even easier than downloading the binary from their website:

```
brew install hugo
```

I generally followed the [Quick Start guide](https://gohugo.io/getting-started/quick-start/) to initialize the website and select a theme from the [expansive gallery](https://themes.gohugo.io/). Because I intended to turn my website into more of a digital portfolio and less of a blog, I wanted a theme with a minimalist static frontpage. I eventually settled upon the simple [Hugo Coder](https://github.com/luizdepra/hugo-coder) theme.

![Hugo Coder Theme Screenshot](hugo-coder_screenshot.png)

# Migrating from WordPress

In order to transition my WordPress content to Hugo, I utilized the [blog2md](https://github.com/palaniraja/blog2md) utility. This Node.js program takes the .xml file exported by WordPress' backup tool and converts each page and post into individual Markdown files, maintaining the formatting, timestamps, and tags reasonably well. Unfortunately I had to go through each entry and manually correct line breaks and update image urls to be compatible with Hugo's [directory structure](https://gohugo.io/getting-started/directory-structure/).

Instead of dumping all of my images into the `/static/image` directory, I opted to create individual subdirectories for each page ([Page Bundles](https://gohugo.io/content-management/page-bundles/)) to keep related content better organized.

```
content
└── posts
  └── hello-world
    ├── index.md
    ├── image_1.png
    ├── image_2.png
```

While this requires moving the migrated Markdown files from `hello-world.md` to `hello-world/index.md`, it permits easier linking to photos/files since they are now in the same directory.

```
![Image 1](image_1.png)
```


## Image Galleries

## Transfer Disqus Comments

# Automating Deployment with Travis-CI

# Integrating Dynamic Content