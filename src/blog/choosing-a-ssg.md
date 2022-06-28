---
title: Choosing a Static Site Generator
date: 2022-06-17
description: Documentation for a lab exercise to evaluate the developer experience of the most popular static site generators
---

## Table of Contents

1. [Introduction](#introduction)
2. [Methodology](#methodology)
3. [Discussion](#discussion)
4. [Conclusion](#conclusion)

## Introduction

By nature, once deployed, websites built using SSGs are very fast and user experience is very good regardless of which SSG you choose. That being said, this post will focus on my personal developer experience while working with five of the most popular SSGs: [Jekyll](https://jekyllrb.com/), [Hugo](https://gohugo.io/), [Eleventy](https://www.11ty.dev/), [Next](https://nextjs.org/) and [Gatsby](https://www.gatsbyjs.com/). Why did I bother going through the installation and entire tutorials for all of these tools? Because when all the tools have the same performance, it comes down to *personal preference*. Why rely on a total stranger for recommendations when you'll be the one working with the tool for the foreseeable future? I'd rather come to my own decision after doing my own experiment. By doing so, I gain first hand experience with all of the tools and hopefully discover or learn something in the process. How was I able to work with all the SSG's if they were based on and use different languages? Although SSG's were written in a language like Ruby, Go, or Javascript, the developer experience is mostly if not completely decoupled from the programming language.

## Methodology

Some people prefer to start with a near-finished project and go through its parts in an order of their choosing. I prefer to learn by building things from scratch so I went through the documentation for each of the SSG's and added a feature while reading about it. For all of the SSG's besides Hugo, there was either a "quick start" tutorial, a "step by step" tutorial or both. The Hugo docs contained only a quick start tutorial so I used a [third party step-by-step tutorial](https://cloudcannon.com/community/learn/hugo-beginner-tutorial/). If the finished product of a step-by-step tutorial lacked features, plugins or styling, I added those myself until the website was presentable and had a decent UI. If the SSG was developed by an organization that also had an affiliated hosting platform (i.e. [Vercel](https://vercel.com/), [Gatsby Cloud](https://www.gatsbyjs.com/products/cloud/), [Github Pages](https://pages.github.com/)), I'd spend some extra time to find out what the developer experience was like and how well they integrated with the SSG. I did all of this on an Intel powered Mac running Monterey 12.4, ZSH, Homebrew and VSCode.

## Discussion

The installation and set up for Jekyll, Hugo and Eleventy were more or less the same: install the gem/binary/package, create a predefined directory structure, and edit the configuration file.

### Jekyll

Jekyll's docs haven't been updated for Ruby versions 3.0 and higher so I needed to do some Googling to find out what to do (install the webrick gem). Jekyll also doesn't have live reloading by default so I created a shell script that included the --livereloading flag. Incremental regeneration (AKA hot reloading) is an "experimental feature" for Jekyll and I enabled it by adding a setting in the configuration file. Deploying the site with Github Pages was straightforward - (1) install the github-pages gem, (2) edit the configuration file, and (3) change some repository settings. Then you have the option to choose a custom branch as the publishing source which is something you might consider if you want to incorporate a continuous integration tool into the repository. Otherwise, the main branch is the publishing source by default and the live site is updated any time you push a change. For the purpose of this experiment, I just published to the default branch. Working with Jekyll was very rewarding. The whole experience felt like I was traveling back in time and experiencing the early stage of Web 2.0. Although the plugin library was incredibly robust, its lack of built-in convenience features had a slight impact on my developer experience. 

## Eleventy

Eleventy is the newest SSG out of the three having been released in 2020. It has the most newly updated user published content and site repositories out of the three making it a draw for beginner web developers or people exploring different SSG options after getting bored or unhappy with their current tool. The build times were very snappy and it came with all the modern developer convenience features that we've come to appreciate. Like Jekyll and unlike Hugo, I needed to optimize the SEO manually (new post about that soon), but it felt nice working in a Node environment and reassuring that Eleventy was relatively new and had a lot of community momentum behind it. 

## Hugo

Unlike Jekyll or Eleventy, Hugo is a binary that you download and run without setting up a developer environment or thinking about runtime dependencies. For those that are new to web development or working from Windows, this feature is undeniably huge, but since I already have version management for Ruby and Node, it wasn't a make or break type situation for me. Hugo doesnt support any plugins, but I couldn't find a feature that I wanted that wasn't already included. For people who prefer less moving parts, Hugo is incredibly robust, while being comepletely self contained and incredibly fast, and would be ideal for the "keep it simple" crowd. The directory structure wasn't too different from Jekyll and even has built in commands for adding new content. When you want to write a new blog post, simply run the command `hugo new` and by default will create a new file with some preconfigured front matter. 

## Conclusion

Ultimately I chose to use Eleventy to build this site and deploy it on Netlify. They play very nicely since the creator of Eleventy actually works for Netlify and built it as a side project. The user interface for Netlify was not as nice as Vercel, but it was still very easy to use and I had this site deployed in a matter of minutes. If you'd like to read about my experience with the more robust and substantial React frameworks, Gatsby and Next, please stay tuned for a new post about that topic coming soon!