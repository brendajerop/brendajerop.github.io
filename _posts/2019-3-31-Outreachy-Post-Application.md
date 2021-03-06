---
layout: post
title: Outreachy Post-Application
tags: [Outreachy Application]
---

Most of the first week was spent looking for a Wikimedia project to contribute to. I wanted a project that I’d dive deep into, learn from it and be able to make meaningful contributions and not just good-first-bugs.

I narrowed down to two projects, Pywikibot and Addwiki. They are both libraries that consume the MediaWiki Action API so I felt that I may have a good starting point because of my previous interaction with the API. They would also help me get a better understanding of the API.

In the end, I went with Addwiki. There was a task about documenting its undocumented classes and I decided to take it on because it would be a good way for me to fully understand the library’s codebase. I sent PRs for about thirteen classes and about ten of them were merged.

The documentation is mostly me telling myself what the library’s classes do as much as it is me telling it to others. I’m still new to PHP so I’m kind of not used to the PHP-serializable response that I get when using the classes. So what I do is query a module using Python just like I do when writing code samples for the API, then I compare the Json response to the output of the classes. This helps me better understand the classes and I also get to interact with many API modules first hand. I’m also getting better at documentation.

One thing I’m starting to understand is how important it is to be patient when contributing to open source. In most cases, the maintainers of the project will be volunteers who are in a different timezone and who have other things to do. So it’s really important to be patient. I’m also starting to get over the excitement of getting a PR merged and starting to put into careful consideration the quality rather than the quantity of my contributions.