{% include online-assignment/intro.md %}

# Context

Avocarrot is a mobile ad exchange, which on the demand side is connected to 3rd-party companies called Demand Side Platforms (DSP) and on the supply side is connected to mobile app developers. For this assignment we'll focus **only on the demand side**.

Each DSP can have one or more bidders connected to our exchange. You do not need to worry about the specifics of how DSPs and their bidders work.

[TODO INSERT DIAGRAM WITH AVOCARROT AND BIDDERS HERE] 

# Objective

As a front-end software engineer for Avocarrot, you are given the task of developing a front-end app that the DSP users can use to manage their bidders.

By the end of this assignment and by completing the tasks below you will have developed a (very simplistic) bidder management platform. 

# Tasks

The assignment is split into seperate tasks. Each task builds on the work done for the previous ones. 

| Task Objective | Expected Completion Time |
|---|---|
| [Task 1:](#task-1) Implement a page which allows the user to view a list of their bidders | ~1 hour |
| [Task 2:](#task-2) Extend the styleguide to include a bidder card component | ~1 hour |
| [Task 3:](#task-3) Implement a page which allows users to edit their bidders | ~2 hours |

## Task 1

### Objective

Implement a page which allows the user to view a list of their bidders.

### End result

Below you can see the mockup of how your page should look like after completing this task.

[TODO INSERT MOCKUP] 

### Styleguide

You do not need to write your own CSS for styling. We have already developed a styleguide which contains all the styling you will need for the exercise. The styleguide can be imported in your project.

You can find the styleguide [here](https://s3.amazonaws.com/avocarrot-style-guide/latest/avocarrot-skin/documentation/apps/getting-started/index.html).

### Bidder Management API

You'll need to retrieve bidder information from a remote API. Please find the docs for the Bidder Management API [here](http://docs.biddermanagement.apiary.io/).

Please note that there is no instance of this service running, therefore in your tests, we expect to see this dependency mocked to simulate the real production functionality.

You are free to use any approach you like to implement mocking.

{% include online-assignment/test-cases-intro.md %}

| Description | Expected input | Expected output | Parameters/Mocks |
|---|---|---|---|
| When visiting the bidder list page the user should be able to see a list of their bidders. | Visit the bidders list page | Your test should check that the correct info (name, endpoint etc) for each bidder is displayed. | Use the sample response provided [here](http://docs.biddermanagement.apiary.io/#reference/0/bidders-collection/get-all-bidders) for mocking the Bidder Management API response. |

## Task 2

### Objective

Extend the styleguide to include a card component. At the moment, the styleguide doesn't contain a card component like the one you implemented for the bidder list page in the previous task. Since this is a component which will be reused heavily, both in this app but also in other Avocarrot apps, we'd like you to write the neccessary CSS to implement this new component.

[TODO how we can be more specific that they should submit a css thing that can be reusable]

## Task 3

### Objective

For the final step in this assignment we'd like to allow DSP users to edit their bidders. By clicking on a bidder's card the user will be redirected to the edit page.

### End result

Below you can see the mockup of how your page should look like after completing this task.

[TODO INSERT MOCKUP]

{% include online-assignment/test-cases-intro.md %}

| Description | Expected input | Expected output | Parameters/Mocks |
|---|---|---|---|
| Clicking on a bidder's card the user gets redirected to the edit page for that bidder. | Visit the bidders list page and click on a bidder card | Your test should check that the user gets to the edit page for that bidder | N/A |
| User is able to edit a bidder's name and persist it to the remote API | When in the edit page the user changes the bidder name and clicks Save. | Your test should check that the page state has changed as well as that the remote API was called to persist the edit | N/A |

{% include online-assignment/deliverables.md %}

{% include online-assignment/assessment-criteria.md %}