---
styleguideUrl: https://s3.amazonaws.com/avocarrot-style-guide/latest/avocarrot-skin/documentation/apps/index.html
---
{% include header.html %}
{% include online-assignment/intro.md %}

# Objective

You are a software engineer for advertising technology company {{site.companyName}}. A fellow software engineer just implemented a new feature on our Bidder Management Dashboard and you are given the task of reviewing their code before releasing it to production.

Notes:

- We do not expect you to be an ad-tech expert so below you can find some quick context to get you started.

# Context

{{site.companyName}} is a mobile ad exchange, which on the demand side is connected to 3rd-party companies called Demand Side Platforms (DSP) and on the supply side is connected to mobile app developers. For this assignment we'll focus **only on the demand side**.

Each DSP can have one or more bidders connected to our exchange. You do not need to worry about the specifics of how DSPs and their bidders work.

![exchange-diagram](/static/exchange-diagram.jpg){:width="100%"}

# What does the codebase your colleague implemented do?

The code you are about to review is adding a new feature on our Bidder Management dashboard, which provides tools for our DSPs to manage their bidders. In this particular feature a new functionality is added so that users can view a list of their bidders.

The exact business requirements are summarized below.

1. When a user visits the ```/bidders``` page, then it should display the bidders split in different columns depending on their state, given that the client loaded the bidders successfully.
2. When a user visits the ```/bidders``` page, then it should display an error message given that the client failed to load the bidders.

Notes:

- These are the only requirements we are concerned with for now. 
- The implementation uses {{site.companyName}}'s [styleguide]({{page.styleguideUrl}}). All the styling you might need is included there.
- The bidder info is retrived via the [Bidder Management API](http://docs.biddermanagement.apiary.io/). 

# Tasks

The assignment consists of 2 tasks.

| Task Objective | Expected Completion Time |
|---|---|
| [Task 1:](#task-1) Review the code and add any feedback/comments/suggestions you may have | ~30 minutes |
| [Task 2:](#task-2) Implement your suggested improvements and implement end-to-end test cases to check that the business requirements are satisfied | ~2 hours |

## Timing assumptions

The time estimates for the tasks above assume that you are familiar or have professional experience with testing techniques and building basic web apps.

## Task 1

Review the code carefully and add any feedback/comments/suggestions you may have. 

Please feel free to suggest anything you think that can be improved. There is no limitation on what you can suggest so add your comments freely. Please do not forget to explain your reasoning behind your suggestions. 

### Where can I find the code to be reviewed?

1. You should have received a Github classroom link which will give you access to the repo to be reviewed. If you didn't then please click on your language of choice below:
    - [React](https://classroom.github.com/a/sQOFY9lb)
    - Angular (Work in progress)
2. When you accept the assignment a new repo will be created which is the one you will be working on. You have admin rights so you can do anything you want. This repo contains a branch called ```feat/view-bidders``` which contains the code that you will review.
2. Click on the Pull Request tab and create a new Pull Request with base branch ```master``` and source branch ```feat/view-bidders```. Use this Pull Request ONLY to add your code review comments.
3. Add your review comments in that Pull Request.

## Task 2

Implement your suggested improvements and end-to-end test cases to check that the business requirements are satisfied.

- Please create a new branch and implement your changes on that one so that it's easier for us to review your changes.
- You are free to change whatever you want in the entire codebase. You can install any dependencies you might need. There is absolutely no limitation.
- The codebase already contains some (failing) test code and fixtures. Again you can change whatever needs to be changed to make the tests run and verify that the app works as expected. Install anything you need. Change anything you need.   
- For your end-to-end test cases you will need to know how to communicate with the [Bidder Management API](http://docs.biddermanagement.apiary.io). 
- Your new changes should be implemented in a separate Pull Request.
- There is no need to implement unit tests, just the end to end tests!

### Styleguide

If you need to implement styling please use the CSS styling already implemented in {{site.companyName}}'s [styleguide]({{page.styleguideUrl}}). 

# Deliverables

At the end you should have TWO separate Pull Requests:

1. The original Pull Request which contains your review comments.
2. The new Pull Request that contains your changes. Feel free to add any interesting approaches or important points in the PR's description.
