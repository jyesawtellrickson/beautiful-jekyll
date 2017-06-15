---
layout: post
title: Reddit Crawler
tags: [data science]
---

# Creating a Reddit Crawler
As a Data Scientist I'm always looking for new sources of data and when it comes to social data there's no shortage. When working on a trend prediction project I wanted to try something different and decided to work with Reddit. I thought it would be a good source of data as it has short discussions with somewhat fleshed out ideas.

I started with the neat library PRAW which gives any easy access to Reddit's API for Python. Around this I wanted to build a class that would simply take a subreddit and some dates then feed me back all the submissions and comments.
