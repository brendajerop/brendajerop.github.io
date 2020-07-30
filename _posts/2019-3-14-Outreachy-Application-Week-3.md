---
layout: post
title: Outreachy Application Week 3
tags: [Outreachy Application]
---

The project mentor suggested that we look at other documentation-related issues at Phabricator since there weren’t any more microtasks. I think this was a good move to make us explore other parts of Wikimedia. Besides, adding more microtasks would mean more pull requests to review and she has a alot on her hands right now (there are so many applicants).

## Second thoughts

At first, I thought that I could maybe make Android Studio work by disabling most plugins and basically turning it into a text editor. This kinda worked while typing (although I missed the auto-completion feature) but Gradle build took forever and that was the final straw for me. I commented on the issue that I wouldn’t be able to work on it anymore because of complications with my laptop and that someone else could take it up.

Anyway, the PRs I sent last week weren’t a waste in a way because I may still be able to record them as contributions in my application(one was approved by one reviewer). Though I doubt they’ll be merged. In this case, it would be a waste since the whole point of the contribution is to improve open source software, which I wouldn’t have done. I’ll only be increasing the work of reviewers, which isn’t nice. Maybe I should just close those PRs.

## Back to exploring

I looked at documentation-related tasks on Phabricator and found two that were about modifying the documentation of the Mediawiki API…easy. However, the sections that needed modifying were in the auto-generated docs and I had no idea how to go about modifying them.

So I asked the project mentor how to go about it and she nicely replied that she wouldn’t be able to make of what was required at that moment because of the PRs that she had to review.

So I kept looking at other tasks and found two that I could work on without much guidance. They were also related to the Outreachy project so they’d give me more experience and make me comfortable with Wiki markup.

One of the tasks was about writing documentation on how to add citations if an extension called Citoid has been configured in your wiki. I completed the first draft, sent it, received feedback, implemented it, second draft, feedback, and I was finally asked to merge it to the mainspace. In the process I learnt about Mediawiki’s guide to technical documentation, which I followed and it made a big difference. I also got better at wiki markup and learnt about qqx and auto-translating messages. The people who reviewed my work, @Trizek-wmf and @WhatamIdoing-wmf were really nice and patient with me.

The other task was about documenting the most used undocumented Templates on Wikimedia Commons, and modifying the documented ones to use a template called TemplateBox if they don’t already do so. This task gave me a better understanding of how templates work and how to use them. I also got better at wiki markup. I already sent my draft for one template and I’m waiting for feedback.

## Magic

While lurking around on Phabricator, a commit with changes to a file that contained the auto-generated documentation magically appeared on my screen. I honestly can’t remember how I found it. Anyway, I set up my own Mediawiki installation and made changes to the file to ensure that it was the correct one and sure enough, the changes were reflected on the wiki. I played a lot with my Mediawiki installation, making changes to the code here and there in order to see the effect.

I then learnt how to use Gerrit and sent a patch, which was merged. Initially, the build tests failed and I kept typing “recheck” to retrigger the tests because I couldn’t figure out what I could have possibly broken. Anyway, the reviewer must have noticed my frustration and assured me that the failure was unrelated to my patch, and that the qunit tests were broken. He later retriggered the tests and they passed. Such a newcomer-friendly community.

Wikimedia is very welcoming of new contributors. They have a bot send you a welcome message when you send your first contribution and the project owners are also added as reviewers. You can also filter patches by new owners.

## Finally…

I’d say that this was the most intense week since the application period started. I had to learn so much- from setting up my own Mediawiki installation, (I tried with vagrant thrice and it failed, but at least I got to see a unicorn on my terminal. I finally decided to use Xampp, which was a breeze to set up) to learning how to use gerrit (I can’t believe I didn’t mess anything up in my first patch. Anyway, it’s all thanks to a great tutorial that I found on the wiki).

Sometimes I’d panick at the thought of not being selected, but I thought about how much I’ve learnt and about the cause, which is contributing to FOSS whether or not I get selected.