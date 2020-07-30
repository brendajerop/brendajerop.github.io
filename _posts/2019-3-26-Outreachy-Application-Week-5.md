---
layout: post
title: Outreachy Application Week 5
tags: [Outreachy Application]
---

I kept looking for tasks which are related to either documentation, the API or both. Anything that would help improve the skills I would require if I get selected for the internship.

I saw a task about writing unit tests and I picked it, even though I had never written unit tests before. I picked it because if I get selected, I would probably need to write unit tests for the demo app. Even if I don’t get selected, I’d have learnt how to write unit tests and that’s a good thing.

Writing unit tests turned out to be waay easier than I thought it would be. My patch was merged and I’m really glad that I picked that task because it forced me to learn something new. Working on this task encouraged me to go for other tasks which had initially looked difficult to me.

I saw a task about adding a new method to Addwiki’s mediawiki-api library, which is a PHP library for interacting with the MediaWiki Action API. The author of the task wasn’t sure which API module to use in order to get the result he wanted. I felt like maybe I’d be able to figure out the right module to use because I had been interacting with the API. However, I had never coded in PHP before.

I went through a short PHP tutorial in order to familiarize myself with the syntax and to my pleasant surprise it turned out to be quite similar to Java. I then forked and cloned the addwiki mediawiki-api repo and went through the code in order to familiarize myself with it. After a few hours, I felt like I had some idea of what was required and how to go about it.

## Accidents

I had cloned the repo to a folder owned by root and I found it annoying that I had to type my password every time I needed to access the repo. So I typed a command in my terminal to change the ownership of that folder and ended up changing ownership of other folders which I hadn’t intended. So I ran another command to change ownership back to root and literally everything in my home folder was owned by root now. I couldn’t access any of the folders because typing sudo anything in the terminal threw an error.

I googled for ways to fix this and all suggestions were along the lines of “You messed up with the permissions in your home folder so the only way to fix this would be to reinstall your operating system”. I really didn’t want to do a reinstall because I didn’t have a bootable DVD at that moment. Also, it was late into the night and most shops were closed so I couldn’t go out and buy one. I kept looking for more solutions online and I ended up making it worse. When I tried to restart my laptop, I got the error “The system is running in low-graphics mode”. Now that I couldn’t even access the desktop, a reinstall was inevitable. I didn’t sleep well that night.

The next morning I rushed to buy an empty DVD, burnt an Ubuntu image into it then I reinstalled my operating system. I couldn’t do a backup before reinstalling because I couldn’t even access the desktop so I lost EVERYTHING. Luckily, I always push my changes to a remote repo so I only lost local copies and all I had to do was clone them. Android Studio was also deleted in the process and honestly I don’t miss it.

## Doubting myself

I started thinking that I was being unrealistic to think that I could learn a new language and add a new method to a library using that language in less than a week. So I went back and did other tasks which were within the range of my abilities.

For some reason, I came back to the task again and this time I pushed my doubts away and I was able to find the appropriate API module to use for the task and I sent a PR. I received the first round of feedback from the project maintainer who said that my work looked great (yay!) but he requested some minor changes. I made the changes and committed them. My PR was finally merged.

## Submitting my final application

I submitted my final application and now I wait. Good luck to me and to all the other applicants like Eisheeta, Nikita and Edidiong. They all did a great job and kept me on my toes.