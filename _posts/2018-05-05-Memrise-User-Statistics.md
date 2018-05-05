---
layout: post
title: Memrise User Statistics
tags: [competitor-research, data]
---

Memrise has gained a lot of popularity in 2017, receiving the App of the Year Award at Google I/O and acquiring over 10 million users with close to no marketing spend - no easy feat. Let's find out more about their users and how the company is actually performing.

## Data Source
To get data from this we will use Memrise's unofficial API. To discover what is available, it is possible to sign for an account and start to play around the page while observing the web traffic. Pretty quickly it can be seen that the data is exposed through an Ajax API. In particular, some of the useful endpoints are described below.

### Leaderboard
Endpoint: /ajax/leaderboard/course/COURSE_ID/?period=PERIOD&how_many=HOW_MANY&offset=OFFSET
Key response keys: {Points, Photo}

THe leaderboard endpoint summarises the points of all the users on a given Memrise course. While it doesn't contain a whole amount of information, some of this could be really useful.

The Points key corresponds to an integer representing the number of points a user has acquired while using Memrise. While this might not mean a lot on its own, we can translate points to number of lessons. This is achieved my completing a few lessons and measuring the average number of points achieved. As a rough estimate, one lession corresponds to 750 points. So if a user has acquired 7500 points, then they have completed around 10 lessons on the Memrise app. With this in mind, the Points value can be used as a proxy for the number of lessons a user has completed. The number of lessons can then be used as a measure for engagement on the app.

The Photo key is the URL where the given user's image can be found. Looking closer at some of these URL's we see they can take the form: 

https://static.memrise.com/img/100sqf/from/uploads/profiles/SophiaLi1d86_161124_0122_22.jpg

In particular, the file name is of the form 'USERNAME_DATETIME.jpy'. With this in mind, for some users we can estimate when they initially assigned up to the platform (assuming they uploaded a photo straight away and since didn't change). At this point we should also note that we need to be careful of bias when making conclusions, e.g. only those registering on web upload a photo.

Notice that the endpoint has a HOW_MANY & OFFSET parameter, which means that we can iterate through the database to get a list of all the leaderboard entries. After doing some testing it also seems that the HOW_MANY field is not limited, so the whole board can be queried at once by setting this number to be very high! (really need to patch that!)

Finally, notice that there is a COURSE_ID field, the users returned are for just one particular course, to get the whole database we need to query all course, combine the datasets and remove any duplicates.

### Courses
In the previous section there was a COURSE_ID field, to get these, we can query their courses endpoint:

Endpoint: /ajax/browse/?s_cat=SPEAKING&cat=LEARNING&page=PAGE
Key points: {Course ID, People, Length}

If we can populate a list of languages (not hard by going through the examples on their page), then we can use this endpoint to query a full list of the courses available.

As mentioned, this is useful for the previous endpoint, but also, we can use this to understand just how many courses are available on Memrise and how many students are signed up for each course. It is important to watch this, for example, if suddenly the number of courses increased, it would be an indicator that Memrise is putting more money into producing new content.

## Analysis
With the data points above, it would be interesting to look at the users' points in more detail. What is the distribution like? Heavily weighted to the lower end I would assume. If this is the case, is there a point where it starts to drop-off quickly? We could also calculate parts along the distribution curve, e.g. how far do 50% of users make it in, 75%? It could be that while Memrise has acquired 10 million users, most of them don't make it past 2 lessons, in which case we need to question the value of these users.

Remember that we naturally had the split by course for this data too? We could use this to calculate which courses are most engaging, i.e. courses with a higher median user points means they last longer before quitting. This could help form strategies for which languages / course content to go after.

What about the sign up dates? Memrise acquired most of its users in 2017 according to the news, does the data reflect this? Can we see virality in the data as would be expected from the supposed organic growth?

Regarding the courses, as with the user points, it would be good to look at the distribution of number of users in each course. How many courses actually have over 1K users? How many over 10K? 

## Conclusion
So we've seen that there is certainly some interesting information publicably avaialable on Memrise's website. In order to make this useful, it would be valuable to setup a process that collects the information on a daily level and monitors the changes in time. For competitors such as Duolingo and busuu this could be invaluable information and help to form a competitive strategy.
