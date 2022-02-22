---
title: "Hosting"
date: 2022-02-22T09:54:22+01:00
draft: false
---

As it's a tech blog, let's first have a look at the hosting stack !

You may be disappointed, no big deal here.

This blog is hosted on GitHub Pages, the free static hosting solution from GitHub. I am using [Hugo](https://gohugo.io/), a static blog engine. If you don't know it, have a look, it's awesome ! No need for SQL server, or backend server (php or others).

Each post is deployed through GitHub Actions, if you are curious, just go to [the repository of my blog](https://github.com/poolpix/blog), it's open. Of course, because there is nothing to hide, it's only blog posts that are available on the web anyway (also, GitHub pages is free only for public repos :D)

I am using [CloudFlare](https://www.cloudflare.com/) as a CDN, it's free and powerful. CloudFlare also gives a free security solution, but it's not needed as it this blog is only static content. The anti DDoS may be helpful someday, let's see !

If you have any question or remarks about anything, I'll be happy to answer on my [twitter](https://twitter.com/Poulpix)