---
layout: post
title: "All-In on Hybrid Apps"
date: 2014-09-14 22:07
comments: true
published: false
categories: 
---

All-in on Hybrid Apps
An Evolving Relationship over a Dozen Years

You may know, dear reader, that the Hybrid App has captured the minds of a couple developers. What is a hybrid app? It’s an App, in the sense that you can download it through your favorite vendor’s App Store. But it’s built using web technologies like HTML, CSS, JavaScript.

There’s an interesting company called [Belly](www.belly.com) in Chicago which has thousands of iPads running their Customer Loyalty app across the country, and they are Hybrid Apps. And one of their (former) developers, Dave Arel, gave a talk at the JQuery Conf that I was just at, which made me think about my history with Hybrid Apps, and how my journey with them actually started in 2002 when I worked in Boston. I’d like to reflect upon what has drawn me to them and why I think they hold considerably more promise for the future than apps built in The Language of the Device.

So - I was working at a reputable cancer center in Boston in 2002, and I was writing data-driven web apps in Microsoft Technologies (ASP, MSSQL, etc.). Often, I’d want to run ad-hoc queries, and share those results with people. And I used a technology called HTML Components (HTC for short) to do this. You see, vanilla HTML web pages could not query databases directly, but if you renamed them from *.htm to *.htc - BOOM! - they had access to the file system, database connections, formatting disks, basically anything. So I’d write an HTC, email it around, and when users opened it and gave it their credentials - they had instant data-driven HTML tables they could print or do with whatever they needed. They could even hand-edit the SQL queries within as it was just HTML ! Thanks, Microsoft, for enabling this - it was tons better than creating a VB6 app with an InstallShield wizard that required Administrator approval, and couldn’t be user-tweaked.

Then there’s [this story](http://www.deanius.com/blog/2013/09/19/you-got-javascript-in-my-c-number-app-slash/) I wrote earlier, about how I pulled off developing multiple MS Office Addins in a short amount of time using HTML, Javascript, and the [KnockoutJS](www.knockoutjs.com) binding framework. That project made me the pride of a product owner, a VP, and a large percentage of my company’s customers, and helped develop a team of 6 out of my prototyping work of a couple of months. So clearly I’ve seen Hybridizing shorten development cycles, and I believe in using it whenever possible.

How does this relate to the present day? While some companies have floundered trying to use web technologies in mobile (Facebook), others have gone all-in and never looked back (Financial Times). So it’s clearly possible to do it right (or wrong) by using Web technologies to reach mobile users, whether mobile web, “Save to Home Screen”, or full-on app. Windows Phone has embraced this approach, and its app store has filled out remarkably despite being a latecomer. Why? Because more developers can build and support web-technologies than Objective-C or .Net, and if you don’t already know Java, you probably aren’t dying to learn it since there are more expressive languages out there whose markets are less - how shall we say it - saturated.

Personally, I’m all-in on Hybrid. Partly, it’s because it’s where i can best leverage my investment in learning Web technologies. Partly it’s because I expect all vendors will have to support writing apps in Web technologies in order to gain market traction. Mostly, it’s because I think it’s foolish to bet against the Web- the most democratizing and empowering platform for content and experiences yet seen. The Web brought you Dancing Baby, remember! I recognize that being able to sell an app in a Store is very important - the Web still has not got payments fully right yet - but that to me is an implementation detail - an afterthought - not a motivating factor in my choice of language, development platform etc..

Our immediate future looks brighter than ever. APIs available to the mobile browser, are richer than ever, and with Cordova/PhoneGap, the sky’s the limit. It’s not worth our time to learn Objective-C or Swift if we haven’t already, because we’re already AppStore-ready (or Play) with Web techs we already know, and limited only by our imagination. I’ll have a Hybrid App in both stores prior to my kid being born and we’re 3rd trimester already! Stay tuned for updates on this and other Hybrid technology news.

PS In full hand-waving manner, I’d like to debunk the myth that the Apple platform being based on Objective-C is about user experience. I don’t think it’s even about lock-in or lock-out. I think Jobs simply wanted to repeat the experience he had for NeXT, which was back in the day when you looked to the computer hardware vendor for the development environment for the platform. Without recognizing that a new de-facto standard solution had taken hold in the world (HTML, CSS, JS), he went on to create a microverse just for his products. Well, over 50% of programmers have never written Objective-C, and Swift isn’t going to change that. Apache Cordova has forced itself into the App Store, and there’s no going back, so raise a glass to the democratizing web! 




