---
layout: post
title: "Database Constraints in a Post-Schema World"
date: 2013-12-14 08:49
comments: true
categories: 
published: true
---
TL;DR - see [this ScreenCast](http://www.screencast.com/users/chicagogrooves/folders/Jing/media/d4d6ab76-0369-487f-b741-11355be8afa4) about some good practices to adopt in applications running on PostgreSQL.

When it comes to web developers, we've become more and more abstracted from the databases we operate on, and more reliant on test automation to ensure certain behavior of our applications and their databases. Make no mistake - this is a Very Good Thing ! Still there is no substitute for data integrity rules enforced at the source. It may involve looking inside at the database, or 'under the hood' so to speak, but if that's what it takes, well you do it.
If your database had a switch that said "Never allow bad data in", and you failed to flip that switch early, you'd have noone but yourself to blame for not knowing about that switch.

In my previous post on Postgres datatypes, some of you may have been wondering "Why bother?" with database constraints ? Rails, in particular, is a framework that seems to have little respect for [DRI](http://en.wikipedia.org/wiki/Declarative_Referential_Integrity) , and even can have some famous issues with certain types of DRI turned on.
 
The reason to bother with constraints and specific datatypes in your (relational) database is that that's what your database was built to do for you, and it's the best place to do it ! The first letter in DRI stands for Declarative. If a Declaration is in place that a column meets certain constraints, then you can count on that declaration to essentially never fail, if you've written it right. The last letter is Integrity. The purpose of these declarations is to ensure integrity of the data. We all know the kinds of messes that arise when data is admitted into the DB that could have been kept out by simple rules initially.

If a person on your team is moving to turn some DRI switches in the database on (further constraining allowable data), this could be a Very Good Thing, which can give everybody a level of confidence in data going forward. A few good questions to ask:

  - Did they write tests to evaluate whether any existing application code breaks once these are turned on ?
  - Do new validations / error handling need to be added to applications to support these constraints ?
  - Are there other systems that talk to the database that need to be checked for possible breakage ? 
  - Are these constraints intended to apply to future database objects as well ? If so...
   - Is there a way for developers to easily add these new constraints ?
   - Is there an automated test to catch if they do not ? 

This is not a complete list by any means. But it is a finite list of concerns which, once satisfied should eliminate any F.U.D. around making a change not prescribed by a framework and thus apparently unconventional. Mind you, in the database world, declarative constraints are entirely conventional, so whether such a change represents "needless complexity" is a matter of perspective.

Summing up, there should be a barrier to making database changes, especially those which can cause application errors in unaware applications. But there is no substitute for Integrity being applied to your data as it enters. Whether or not you're a fan of strong-typing your code, or whether your favorite framework uses or eschews constraints, you must recognize that there's no substitute for database-enforced integrity. Garbage data can be as toxic as garbage code.
