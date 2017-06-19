---
layout: post
title: Facebook Chatbot
---

Source: https://github.com/jyesawtellrickson/facebook-chatbot/

In my past role at CaterSpot I was responsible for making sure those who need catering can find the products they need as quickly as possible. When it comes to catering, there is a lot to choose from and the menus can be very complicated, and this was especially true when you looked at our product. I wanted to simplify this process and give the user a more friendly approach. To do this, I created the CaterBot, a simple little bot which would present the information available on the platform direct to the user, natively through the Facebook Messenger Platform.

## Tech
To build the bot I started with a nice example that was created by Facebook to promote their new Messenger. You can find it [here](https://developers.facebook.com/docs/messenger-platform) as well as read more about their Messenger platform. The general idea is that whenever someone engages with the bot it will send a POST request to a webhook and then you respond with the message you would like to send to the user. It's quite powerful with different formats you can respond with inculding links, photos and videos.

The bot was coded in Javascript and hosted on [Glitch](https://glitch.com/), a neat platform for building small web apps.

## Data Source
The bot needs to provide the user with in-depth knowledge of the best caterers, the reviews they've received and present images of all the products - this is a lot of information! I wanted the information we provide the customer to always be up to date so we don't offer something that's currently unavailable or miss out on showing the latest and greatest so to do this I programmed the bot to scrape our website every time a request came in, this way it always had access to the exact information the customer would see if they visited our site. One problem with this is that it could be a bit slower when the website had a large amount a traffic or was for any reason running slowly.

Long term, I would have liked to setup a script to scrape all the required information and store it a convenient format which the bot could then query directly. The script could then be set to run daily to give a fairly accurate description of the available products. One thing to note on this, is that research has shown that users actually prefer to have delay when a bot is searching different sources as it seems to indicate the bot is working hard for them (I believe there is a nice study on this by Skyscanner).

## Chat Flow
The goal was to simplify the user journey and to achieve this in a quick and easy way I designed a very simple conevrsation flow to take the user on. The flow is this (see screenshots below for more detail):
1. Introduction
2. Format selection
3. Caterer selection
4. Food selection
The only language processing really required in this design was in the initial few messages when deciding what format of food the user is looking for. All other communication was guided through the use of pre-written messages that the user could choose from. The merit of this is it is easy to get up and running and you know the information is going to presented neatly to the user but the downside is that the user can feel closed in and like they are interacting with a robot (go figure!). When building your own bot, it's important to weigh up the pros and cons and choose what's right for your requirements.

## Traffic
How were users going to interact with the bot in the first place? We already had a good amount of traffic coming through Facebook Advertising and thanks to Facebook pushing the Messenger Bot, it is relatively cheap to buy clicks for the bot. How it works, is that when a user sees an advertisement for your company, they have the option to click "Chat Now" which will then launch the chatbot in the native Facebook Messenger, somewhere the user is already very comfortable and also able to navigate back to with ease. Another added benefit of this is that you can actually reach out to the user again after some time has passed to remind them of your service.

## Final
The final product was able to simplify the process taken by the user and rapidly speed up discovery while adding the appearance of a human touch and a customised choice. The setup cost for this was very little so I recommend you look into something similar for your business if you have the resources (or talk to me!).

## Screenshots

<img src="http://i.imgur.com/ByOcAno.png" width=250px><img src="http://i.imgur.com/9rErvBW.png" width=250px><img src="http://i.imgur.com/mrLJL9v.png" width=250px><img src="http://i.imgur.com/9aTv553.png" width=250px><img src="http://i.imgur.com/82c4fI5.png" width=250px>

