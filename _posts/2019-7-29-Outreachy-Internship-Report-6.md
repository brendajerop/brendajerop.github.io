---
layout: post
title: Outreachy Internship Report 6
tags: [Outreachy Internship]
---

It's the eleventh week of my internship and I'm in the third phase of my internship, which is working on a demo app that demonstrates the usage of more than one MediaWiki Action API module. The demo app I've been working on has the following features:
* Lists the current day's holidays and observances from Wikipedia.
* Allows searching for holidays of other dates other than the current date.
* Allows authentication into Wikipedia in order to add a new holiday.

Screenshots
-----------

 |  |  | 
--- | --- | --- | ---
![](/assets/screenshots/list-holidays.png) | ![](/assets/screenshots/search.png) | ![](/assets/screenshots/login.png) | ![](/assets/screenshots/add.png)


Implementation
--------------
Wikipedia has a page for each date, whose title contains the month name and date number, e.g. [February 1](https://en.wikipedia.org/wiki/February_1). The page for each date(let's call it a date page) has common sections which are _Events, Births, Deaths and Holidays and observances_. There may be other sections for special dates, but the sections I've mentioned are common for all date pages. 

When the demo app is loaded, it uses Python's _datetime_ module to get the current date. It then sends a request to MediaWiki Action API's [Parse](https://www.mediawiki.org/wiki/API:Parse) module to get the parsed html of the text in the _Holidays and observances_ section, in the date page. The html is then edited to a uniform format for easy styling using a html parser known as [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/).

When the search button is clicked and the user chooses a date to search for, the date page to be parsed is updated and holidays for that date are fetched.

The app also allows adding of new holidays. However, since all the known holidays are probably already on Wikipedia, new holidays added through the app are added to [this page](https://test.wikipedia.org/wiki/Holidays_and_observances) on Test Wikipedia, which is [a wiki for developers to test their code without breaking all of Wikimedia and blowing up the world](https://test.wikipedia.org/wiki/Main_Page).

The page is protected so that only auto-confirmed users can edit it so adding new holidays will require logging in. The app uses [API:Login's](https://www.mediawiki.org/wiki/API:Login#Method_2._clientlogin) _clientlogin_ action to authenticate the user into Wikipedia and if the login is successful, the user will be redirected to a page where they can add a new holiday. If the login fails, the user will get an alert that the operation failed, and the cause of the failure.

At the _Add holiday_ page, there is prompt to enter the date of the holiday to add and the description of the holiday. A request to edit the page is sent through [API:Edit](https://www.mediawiki.org/wiki/API:Edit) and if the addition is successful, the user is redirected to the homepage, where the holidays listed are for the date which a new holiday was just added to. Holidays added through the app are formatted in bold so as to differentiate them from the "actual holidays".

I've just opened a pull request for the demo app so as it's is being reviewed by my mentor, I'll spend the week drafting a step-by-step tutorial to explain its implementation.