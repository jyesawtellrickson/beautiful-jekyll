---
layout: post
title: Lead Generation with LinkedIn
tags: [linkedin, caterspot, startup, growth-hacks]
---

How do I generate leads for my business? 

It’s usually a question at the back of any salesman’s mind and it’s no easy feat. Generating a good quality pipeline will do wonders for your sales figures and help you to grow a business fast. For startups, it is crucial. What if I could tell you I could generate cold leads for any job, industry you want to target and get you 10% of the market?

In one of my previous roles we were looking to grow out our B2B leads and thinking about how best we could achieve rapid expansion into new markets without spending huge on marketing. For our business, we had found that there were certain types of clients who had high recurrency and high spend, we needed to find these people fast. We tried cold-calling but the problem is, it takes time and you’re often blocked very quickly. To get around this I turned to cold email, with some added tricks.

Say I want to find a secretary for a certain business in Hong Kong, how do I do that? At this point in time, most people would say LinkedIn. So I can search a job and a location and that lands me on a page with the relevant info. Great, now I want to do this, 100 times, nay, 10,000 times. I want to find every secretary there is in Hong Kong and I want to tell them about my business.

Now, LinkedIn restricts the amount of InMail I can send to 30 / month with the maximum somewhere around 100, so that’s not going to work. I need to turn to traditional email, but how do I get that elusive email from LinkedIn? Well, the trick is to use one of the many Email Guesser tools online. All that you require is the company / domain and the name.

I wrote up a quick script to access this from the page, downloaded 1000’s of pages with the help of an Upworker (see my article on Upwork) and I was good to go. 

Now, what to send in that cold email? The great thing up to this point is that I have a lot of information about the person I’m emailing. I have their full name, company, role, connections and even their photo. I set up a template that looks something like this:

```
Hi ${"First Name"}, I was referred to you as the person in charge of [WHAT YOU SELL] for ${"Company"}.<br><br>

I wanted to introduce you to <a href="[YOUR LINK]?utm_source=71533915&utm_medium=email&utm_content=${"Email Address"}">[YOUR COMPANY]</a>, [WITH DESCRIPTION].<br><br>

${"Search"}s from Google, Facebook, Uber, Netflix and thousands of others already use and love our service. I'd love for you to try us out, so I created a $40 voucher for you - simply use the code ${"Voucher"} at checkout.<br><br>

If you have any questions please don’t hesitate to reach out to me and I'd be happy to help.<br><br>

Cheers,<br>
Jye
```

To send this, I’ll be using a mail merge script I wrote (within Google Scripts) but you can also try out a basic one [here](https://yet-another-mail-merge.com/ "Yet Another Mail Merge"). These do the same thing, in that they send out an email by replacing the placeholders you have.

Awesome, let’s blast! Hold up. How are we going to track this? Being able to track things like open rate, click-through rate and response rate is very important if we want to learn anything about our customers, or even improve upon our template. You can use Google Analytics to get user events ([see this great article](http://www.lunametrics.com/blog/2013/06/17/email-tracking-google-analytics/) and then pull the data into Google Sheets using the Google Analytics plug-in.

So, does this work? It does. Using this we got an awesome click-through rate of over 30%, we had response at 6% and we even had some calls coming through. Since then, numerous have converted to long-term customers. Needless to say, I recommend you try this out if you’re targeting any particular roles / people.
