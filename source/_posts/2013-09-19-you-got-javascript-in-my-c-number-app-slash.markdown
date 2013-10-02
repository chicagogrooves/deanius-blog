---
layout: post
title: "You got JavaScript in my C# app!"
date: 2013-09-19 15:24
comments: true
categories: 
---

If you've used any web-based software that you rely upon on a daily basis, like CRM, you know how important quick access to your information in that web app can be. Many CRM's like SalesForce- even the open source Sugar CRM - have provided addins that integrate with desktop software like Outlook and Excel in order to put the website's features close at-hand. 

To that end, and with my previous C# skills in mind (even though I was hired for my Ruby on Rails skills) I was asked to head up development of such an Excel addin for my former company. In the end, I created two addins, one each for Outlook and Excel, and the one-person team that I was became a 6 person team due to the success of the products. Within a year from my first code, almost 70% of the firm's clients were using the addins I started. Read on, or see the notes at the bottom for technical details on how this was accomplished.

The decisive architectural choice I made was to do as much of the addin as possible in HTML5, CSS and Javascript. I used C# for hosting, installation, and server communication, but the Web UI delivered interactivity and style. Javascript components that users were familiar with from the company website, could be used directly, whether or not an equivalent existed in WPF or .Net. The UI could be, and was, developed without the need for Visual Studio. And the app could be maintained by a larger percentage of the company's staff - nearly 100% knew HTML, only about 5% were .Net-savvy.

The products were successful, not just for their look feel and interactivity, but because they were able to ship in a short time frame by using technologies with faster iteration times. LiveReload and a browser are a much faster iteration environment than Visual Studio's compile/launch cycles. For updating installed addins, HTML files and app resources could be sourced from a server for central updating, with less fuss and administrator involvement than the Windows Update (even Click-Once). 

Can this approach work for apps as well ? Maybe, but mobile devices can be less forgiving than desktop apps. I'll write another post about the state of the Web/App divide. I'd like to think that the ease of building and updating benefits I described would transfer over, but the Stores are trying very hard to discourage it for their own commercial reasons. 

For now I'll just keep increasing the reach of my coding skills by using the most broadly applicable technologies to build solutions. The hundreds of happy customers of my former company have not been complaining.

---

Technical details: A WebControl was embedded in the addin. Due to security restrictions, I could not source a page from the file system or a remote URL directly from the WebControl - so the content was fetched by .Net and injected ala document.write. The Knockout JS framework was used for interactivity. The WebControl had a C# instance of a view model set as the ObjectForScripting property so that JS could talk to C#. Some marshaling code was written so that code which updated the C# ViewModel would automatically update the JS viewmodel, and knockout would re-render the page.

All in all this worked very well, and I would heartily recommend this architecture going forward. Changes I'd make would be around the C#-JS communication layer to make it simpler. Also, having asynchronicity supported in the C# side as well as the JS side led to some interesting debugging episodes.


