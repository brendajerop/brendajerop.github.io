---
layout: post
title: Outreachy Application Week 4
tags: [Outreachy Application]
---

I worked on the second task that I had found, and it turned out harder than I thought it would. When a user is revision-deleted on a wiki and you query the user who made a certain revision using API:Revisions, it will return *userhidden:” ”* instead of user: *“brenda”*…so my task was to find modules which were affected by this and add a note about these hidden keys.

First, only admins can see which revisions have been deleted so I requested for permissions on testwiki to be an admin, then I made changes to a file and revision-deleted some parameters and then queried module Revisions to see which parameters were affected. I thought that was all until I found out that it wasn’t only module Revisions that was affected by these hidden keys. So I had to go hunting for these modules in the code…it turned out that there were 6 modules affected by the hidden keys.

## Surprises

Both of my PRs to the Wikimedia Commons Android app were merged! It was a pleasant surprise because I didn’t think much of them.

## Demo app

The project mentor finally replied that she loved my app idea and that I should include it in my proposal. She also sent me links that would be helpful in regards to design and refining my idea.

From the links she sent me and from the feedback she had given to another applicant who had created a demo app, I decided to change the layout of the demo app to a mobile layout. It be a better use of space since the app would not have a lot of content.

I then created mockup screens for the demo app to reflect the new layout.

## Submitting my proposal

The project mentor said that we were required to create drafts of our proposal on Phabricator and have them ready by Monday the next week. I had a google doc which I had been filling in with details of my proposal since early in the application period so that was left was to copy it to Phabricator and polish it up. I copied the proposal to Phabricator and requested for feedback from the mentor.