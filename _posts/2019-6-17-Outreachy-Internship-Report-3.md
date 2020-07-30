---
layout: post
title: Outreachy Internship Report 3
tags: [Outreachy Internship]
---

I'm an Outreachy 2019 summer intern at Wikimedia working on improving the documentation of the MediaWiki Action API. I'm in the fifth week of my internship and in this blogpost, I will explain more about my project.

## First, clearing things up

So what/who is Wikimedia and is it in any way related to Wikipedia?

**Wikipedia** consists of a collection of free online encyclopedias which are available in different languages. When most people say Wikipedia, they actually mean English Wikipedia. There are other Wikipedias like French Wikipedia and German Wikipedia.

A **wiki** is a type of website that can be edited through the browser and more often than not, by anyone. A good example of a wiki is the English Wikipedia. Anyone can sign up on English Wikipedia and add or edit information.

A **wiki engine** is a software that powers a wiki, the same way a software like WordPress powers many blogs. The software that powers Wikipedia is called MediaWiki. It’s free for anyone to use and it powers many other wikis apart from Wikipedia. MediaWiki is open-source so anyone can contribute to its development and improvement. Wikis powered by MediaWiki will usually contain a “Powered By MediaWiki” branding at the bottom.

**Wikimedia** is the organization behind Wikipedia, MediaWiki and so many other projects. Wikimedia projects will usually contain “a Wikimedia project” branding at the bottom. Through these projects, Wikimedia's mission is to provide free educational content to the world.

## My Project
The MediaWiki Action API is a web service that provides access to wiki features like logging in, creating an editing a page, searching for a title and many more. It can be used to monitor a MediaWiki installation and even create a bot to maintain a MediaWiki installation. See [https://www.mediawiki.org/wiki/API:Tutorial](https://www.mediawiki.org/wiki/API:Tutorial) for more about the API.

My role is to improve the documentation of the API by:
* Re-writing it to follow a template.
* Adding code samples to demonstrate the use of the API modules.
* Developing a demo app based on some of the modules and creating a tutorial to explain its implementation.

By using a template, this project will make finding information about the API more intuitive and the code samples will make it easier for people to understand how to use the API.

The top 50 documentation pages had been improved previously so I'm required to improve atleast the next 20 documentation pages. So far, with the help of my mentor, I have improved the documentation of fourteen pages. My workflow consists of:
1. I create a separate git branch for each API module, write sample code and commit it. I then draft the documentation for the module in a wiki sandbox page. Once I've gone through my work severally and think the it's ready, I open a pull request for the module on GitHub and include a link to the documentation draft in the pull request description. An example of such a pull request is [https://github.com/wikimedia/mediawiki-api-demos/pull/125](https://github.com/wikimedia/mediawiki-api-demos/pull/125).
2. My mentor reviews the pull request and the documentation and if all looks good, she merges the pull request and I merge the documentation draft to the main namespace. If she requests any changes, I make them and the work is merged when it's ready.
3. After the draft is merged to the main namespace, I add the improved documentation to a list of improved pages and I delete the draft so that it doesn't clutter API documentation search results. An example of improved documentation is from [API:Import&oldid=3031432](https://www.mediawiki.org/w/index.php?title=API:Import&oldid=3031432) to [API:Import](https://www.mediawiki.org/w/index.php?title=API:Import&oldid=3265223).

Through this project, I have learnt how important documentation is and that good documentation can save a lot of time for the user. I have learnt how to include all the necessary information to a documentation without being too wordy, the different types of documentation structures and how important it is to understand the user.

Later on, I will develop a demo app using Python/Flask so I'm currently brushing up on my Python/Flask skills as well and learning any new technologies that I might require while developing the demo app, like how to use [Toolforge](https://wikitech.wikimedia.org/wiki/Portal:Toolforge) for hosting.

More information about my project and weekly mini-updates are available here [https://www.mediawiki.org/wiki/User:Jeropbrenda](https://www.mediawiki.org/wiki/User:Jeropbrenda).

## How to contribute to and be part of Wikimedia

What I love the most about Wikimedia is that it provides a platform for people with a wide range of skills to contribute. One can contribute through software development, documentation, translation, etc. This [page](https://www.mediawiki.org/wiki/How_to_contribute) explains all the ways you can contribute to Wikimedia and it also contains information on how to get started.