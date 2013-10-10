---
layout: post
title: "We dont need no stinking WiFi! (Offline apps)"
date: 2013-10-10 11:02
comments: true
published: true
categories: 
---

So ladies and gentlemen, Meteor App #2 is online now, dubbed <a href="http://signmeup.meteor.com" target="_blank">SignMeUp</a>. 

The other day I was at the expo for a large sporting event, chatting up the various vendors in their booths, when one of them asked me if I'd like to sign up for their mailing list. I expressed my interest, he gestured toward an iPad in a nice stand with a sign-up web page. This is where it got embarassing for them. 

You see, they merely pointed me at a public page on their public website - in a room where thousands of visitors had completely saturated the little cellular connection there was, and where wifi was either also saturated, or poorly placed. You get the idea. The sign-up process was a debacle. We finally got the webpage loaded, and adding insult to injury, there was a Captcha I had to solve, which of course I did not get right the first time ! I stuck through it, but I know they lost several people due to this process. I know the expression goes "you can't take it with you", but when it's an iPad in a zone of little connectivity, and your signup app matters, you'd better take it with you ! 

So the way you do this is described below, and to see it in action, check out <a href="http://signmeup.meteor.com" target="_blank">SignMeUp</a>

First, while online, you visit the page in Mobile Safari (or any other browser on a tablet, mobile device or computer). The page saves any collected names and emails to HTML5 Local Storage. This collection persists in the browser (up to 2.5Mb), even if the browser or device is shutdown and restarted. An admin view lets you see all collected names and emails.

Secondly, the page and its static assets persist in the HTML5 Application Cache, so the browser will not lose them if you are offline. Even if you visit ``http://signmeup.meteor.com`` while in Airplane mode, you will not get the dreaded WSOD (white screen of death).  

Fortunately for me, the Meteor ``appcache``  package made it compelling to make even this simple one-page project into a Meteoric one. With a simple ``meteor add appcache``, the entire app persists, even if the device goes into airplane mode. The manifest files are written for you, invalidated as needed, and you and your customers get to grin and not even notice the lack of WiFi !

When combined with "Add to Home Screen", you get an offline application, without browser chrome, that doesn't need internet connectivity to function. In other words - an App, but without the pain of an App Store, and portable to any device with a few lines of CSS.

Feel free to use this page as you see fit - your data and others don't mingle because it never even gets sent to the internet. I hope this helps you make your data collection robust in the face of network uncertainty. Have fun with it !

