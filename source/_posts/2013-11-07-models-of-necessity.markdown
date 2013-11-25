---
layout: post
title: "Models of Necessity"
date: 2013-11-07 08:27
comments: true
categories: 
---

Throwing people into the deep end so that they may learn is a great idea, but we don't need to skip the steps of teaching them how to visualize success and understand what's actually going on.

Lets start with the deep-end swimming metaphor. As anyone who's treaded water can attest to, when you're doing it efficiently, the hands make a sculling figure-8 motion to generate lift. Now, if I want somebody to learn to stay afloat, I'm going to show them this motion and create a mental model in their head first. I'm still going to have them experientially practice it for themselves in the deep end. But I'm going to send them into the water with this idea already in their head, giving everyone a similar model of what is a successful to stay afloat. If I don't, some will learn to stay afloat with doggie paddle, some on their back, others doing whatever motion they stumble into. This is an unfortunate outcome which can be avoided.

The book [Refactor Your Wetware](http://pragprog.com/book/ahptl/pragmatic-thinking-and-learning) cites the need to engage both modalities of the brain, R-mode and L-mode. When you paint a picture for the students ahead of time, you are giving them a framework they can use to guide, and then sort through their deep-end experiences. When it comes to software - say, learning git - if you only show them series of ever more complicated git commands and procedures, without drawing a diagram of a tree graph, you are going to end up with students with incomplete mental models, who will be struggling over the most basic things for a long time.

I think no instruction in git is complete without a depiction of a tree with many branches. While learning, a drawing of the tree of commits can gain new branches as we add new commits with `git commit -m`, or remove them with `git reset HEAD^`, or switch a marker to another branch as we `git checkout branch_name`. This way the verbal side of the commands marries up to the imagery of the tree, and an intuition can develop, for what *is possible*. 

Why leave it to chance what mental model and practices the students will end up with, when there's really only one way that it works ?? We don't want to end up with [Cargo Cult](http://en.wikipedia.org/wiki/Cargo_cult_programming#Origin) ideas ! Also I don't want students to have to reverse-engineer the mental model of git from its commands - git sucks for that. Instead they should learn to be comfortable adding and removing nodes from the git tree, and most importantly - assessing their current state ! This is why `git diff --cached` and `git log -2` are indispensible to teach early.

There are lots of ways to teach and learn swimming and git. We've learned things about learning, and we should use those things to give students every possible advantage they can have.






















