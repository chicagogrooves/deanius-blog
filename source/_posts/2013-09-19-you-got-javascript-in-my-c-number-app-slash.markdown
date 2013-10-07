---
layout: post
title: "You got JavaScript in my C# app!"
date: 2013-09-19 15:24
comments: true
categories: 
---

People who use Microsoft Office tools on a daily basis often like to get to data that is stored on websites directly through their Excel, or Outlook. My former company was in the business of managing financial and CRM data for their clients, and while there was a fabulous website on which they could work with their data, salespeople wanted access to it in Outlook, analysts wanted the data in Excel, and everyone wanted to style up pie charts and line graphs.
 
To that end, and with my previous C# skills in mind I was asked to head up development of addins for Outlook and Excel, to connect to the company's data. It went really well, and within a year from my first code, almost 70% of the firm's clients were using the addins I started. Talk about the right solution at the right time ! The one-person team that I was became a 6 person team due to the success of the products. 

While many people and decisions had factors in this success, one decision I made that I think helped it out, was to build as much of the addin as possible in HTML5, CSS and Javascript. This is something you don't just generally do - all the information you see online says you build addins in C# or VB.Net ! I still used C# for hosting, installation, and server communication, but the Web UI delivered interactivity and style. Javascript components that users were familiar with from the company website, could be used directly, whether or not an equivalent existed in WPF or .Net. The UI could be, and was, developed without the need for Visual Studio. And the app could be maintained by a larger percentage of the company's staff - nearly 100% knew HTML, only about 5% were .Net-savvy.

One thing this really helped was getting fast feedback cycles. LiveReload and a browser are a much faster iteration environment than Visual Studio's compile/launch cycles, especially for addins. Even when the addin was 'installed', HTML files and app resources could be sourced from a server for central updating. This reduced Administrator involvement compared to the usual Windows Update methods. To me, being Agile means you need tight feedback loops, even while developing.

Can this approach work for apps as well ? Maybe, but mobile devices have different constraints than desktop apps, and sometimes App Stores have their own rules. I'd like to think that the ease of building and updating benefits I described would transfer over, but the Stores are trying very hard to discourage it for their own commercial reasons.

For now I'll just keep increasing the reach of my coding skills by using the most broadly applicable technologies to build solutions. The hundreds of happy customers of my former company have not been complaining.

---

Technical details: A WebControl was embedded in the addin. Due to security restrictions, I could not source a page from the file system or a remote URL directly from the WebControl - so the content was fetched by .Net and injected ala document.write. The Knockout JS framework was used for interactivity. The WebControl had a C# instance of a view model set as the ObjectForScripting property so that JS could talk to C#. Some marshaling code was written so that code which updated the C# ViewModel would automatically update the JS viewmodel, and knockout would re-render the page. All in all this worked very well, and I would heartily recommend this architecture going forward. 

