---
layout: post
title: Language App with Object Detection
tags: [100-ways-we-could-be-smarter, machine-learning, object-detection, app]
---

I'd like to run through my idea for a language app that incorporates object detection as a feature to help in the language learning process. 

# Problem To Solve
Learning a language is a difficult task [link]. Personally, I struggle to remember vocabularly unless I can practice it in my day-to-day life, but to do this I need to pull out my translator app and type it in English. This can become painful to do every time and I quickly lose interest in doing so. The language app solves this problem by making the task of checking your environment and learning the translations an easy task.

# Features
The main innovative feature of the app is the ability to detect objects in the environment. For example, if you take a photo of your living room, you'll see the translations for television, clock and remote placed directly on top of the image. These features are extended with synonyms and common phrases to provide the user a greater vocabulary to practice with while maintaining the memory-strengthening effect of the photo context.

Color Picker: A smaller feature for beginners is the color picker, which allows you to sample a colour on the screen and get instant feedback of the color translation. The translation is both simple, e.g. blue, and complex, e.g. aquamarine.

Emotion detection: A feature used to describe how people feel in a photo. If you take a photo of your friends the app can feedback happy, sad and similar emotions along with their translations.

Photo Collection: Users will be able to store their photos allowing them to strengthen fading memories.


# Limitations
Current object detection models are still trained on a limited corpus, with just 300+ categories. This is something which is being constantly improved and within a few years there will be models able to detect thousands of objects. In the meantime, this problem is solved by leveraging synonyms, similar words and common phrase patterns.

# Flow
The general flow to be used in the app
1. Take a photo of something.
2. Apply object detection to discover objects in the scene
3. For each object, display name in english and chinese
4. Next render the explore feature, so when you click on a word, it expands the word out into a sort of knowledge graph composed of a few things: Synonyms, Common Phrases, related Verbs / Adjectives / Nouns.
