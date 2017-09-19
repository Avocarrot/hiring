{% include online-assignment/intro.md %}

# Context

Avocarrot is a mobile ad exchange, which on the demand side is connected to 3rd-party companies called Demand Side Platforms (DSP) and on the supply side is connected to mobile app developers. For this assignment we'll focus **only on the demand side**.

Each DSP can have one or more bidders connected to our exchange. You do not need to worry about the specifics of how DSPs and their bidders work.

[TODO INSERT DIAGRAM WITH AVOCARROT AND BIDDERS HERE] 

# Objective

As a front-end software engineer for Avocarrot, you are given the task of developing a web app that the DSP users can use to manage their bidders.

By the end of this assignment and by completing the tasks below you will have developed a (very simplistic) web app for bidder management. 

# Tasks

The assignment is split into seperate tasks. Each task builds on the work done for the previous ones. 

| Task Objective | Expected Completion Time |
|---|---|
| [Task 1:](#task-1) Create re-usable components to display bidder information and state | ~1 hour |
| [Task 2:](#task-2) Implement a route which allows the user to view a list of their bidders | ~1 hour |
| [Task 3:](#task-3) Implement a route which allows users to edit their bidders | ~2 hours |

## Task 1

### Objective

Create re-usable components to display bidder information and state. These components will be used later in the assignment.

### End result

Below you can see the mockup of how these components should look like.

### Styling

You should write your own HTML and CSS for the components but please check out Avocarrot's [styleguide](https://s3.amazonaws.com/avocarrot-style-guide/latest/avocarrot-skin/documentation/apps/getting-started/index.html) for guidelines about colors and typography.

## Task 2

### Objective

Implement a route which allows the user to view a list of their bidders.

### End result

Below you can see the mockup of how your page should look like after completing this task.

[TODO INSERT MOCKUP] 

### Styleguide

For this task you should re-use the components created in the previous one. However, for the rest of this task you can use the CSS styling already implemented in Avocarrot's [styleguide](https://s3.amazonaws.com/avocarrot-style-guide/latest/avocarrot-skin/documentation/apps/getting-started/index.html). The styleguide can be imported in your project.

### Bidder Management API

You'll need to retrieve bidder information from a remote API. Please find the docs for the Bidder Management API [here](http://docs.biddermanagement.apiary.io/). Note that for simplicity you do not need to provide any authentication/authorization info. Assume that your calls are already authenticated.

Please note that there is no instance of this service running, therefore in your tests, we expect to see this dependency mocked to simulate the real production functionality.

You are free to use any approach you like to implement mocking.

{% include online-assignment/test-cases-intro.md %}

| Description | Expected input | Expected output | Parameters/Mocks |
|---|---|---|---|
| When visiting the bidder list route the user should be able to see a list of their bidders. | Visit the bidders list route | Check that the correct information (name, endpoint etc) and state for each bidder is displayed. | Use the sample response provided [here](http://docs.biddermanagement.apiary.io/#reference/0/bidders-collection/get-all-bidders) for mocking the Bidder Management API response. |

## Task 3

### Objective

For the final step in this assignment we'd like to allow DSP users to edit their bidders. By clicking on a bidder's card the user will be redirected to the edit route.

### End result

Below you can see the mockup of how your page should look like after completing this task.

[TODO INSERT MOCKUP]

{% include online-assignment/test-cases-intro.md %}

| Description | Expected input | Expected output | Parameters/Mocks |
|---|---|---|---|
| When clicking on a bidder's card the user should get redirected to the edit route for that bidder. | Visit the bidders list route and click on a bidder's card. | Check that the user was redirected to the edit route for that bidder. | N/A |
| User should be able to edit a bidder's name and persist it to the remote API. | Visit the edit route of a bidder, change the name and click Save. | Check that the page state has changed as well as that the remote API was called to persist the edit. | N/A |

{% include online-assignment/deliverables.md %}

{% include online-assignment/assessment-criteria.md %}