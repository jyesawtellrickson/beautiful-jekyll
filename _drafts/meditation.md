---
layout: post
title: Meditation Bot
tags: [meditation, python]
---

# Summary

# Mindfulness
Important for us

# Let's get Talkative
The ability to talk is critical for a mentor. To simulate voice I used the native Windows voices available throuh the Windows Client Speak module. On Windows 10 there are just two options, one for the UK and one for the US, both female. There's not a lot of customisation available but thankfully I was able to adjust the speed through the Rate attribute which allowed me to slow it down as is typical in a real meditation setting.

# New Language
To teach lessons, we need words to say, and these come in the form of scripted lessons. When sitting throuh a meditation session the general format is advice, long pause, advice short pause, etc., so we need a way to incorporate this into our bot. I decided to give the functionality when composing scripts so I created a simple function to parse each line and interpet different symbols as different pauses. When performing the lesson, the bot will then speek and then the system will pause for the assigned time.

The rules are pretty simple:
- # at the start of a line indicates a comment, and will be skipped (good for dividing sections)
- an integer at the end of line indicates the time to pause after the line has been read
- similarly, an integer on any empty line simply represents a long pause
- the symbols ",", "-" and "..." represent 1, 3 and 5 second pauses, respectively

# Building the Scripts
In order to source the scripts I researched different meditation methods online and found plenty of examples of prepared scripts. It's possible to simply copy-paste these into txt files but I also did a few edits to add in pauses where I think they would improve the sessions. It was really easy to add these in, and as I continue my medititation I'll keep improving on the library.

# Running the Bot
It's very easy to launch and run the bot:

 ```
from meditation import Guru
Bodhisattva = Guru()
Bodhisattva.choose_teaching()
# input lesson number
Bodhisattva.teach()
```

It's currently available on my Github https://github.com/jyesawtellrickson/meditation-guru/
