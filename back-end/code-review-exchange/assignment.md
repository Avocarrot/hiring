{% include header.html %}
{% include online-assignment/intro.md %}

# Objective

You are a software engineer for an advertising technology company called Blue Banana. A fellow software engineer just implemented a (super) simple ad exchange and you are given the task of reviewing their code before releasing it to production. 

Notes: 

- We do not expect you to be an ad-tech expert so below you can find some quick context to get you started.

# What is an ad exchange?

An ad exchange is a platform which facilitates the buying and selling of ads in real time.

- On one side of the ad exchange we have the mobile apps which send requests to our exchange to sell their traffic. 
- On the other side, the exchange communicates with bidders which submit their bids for the traffic if they are interested in buying it.

The ad exchange receives the bids and the highest bidder wins the auction and gets to show their ad. The flow is summarized in the diagram below.

![auction-process](/static/auction-process.jpg){:width="100%"}


# What does the codebase your colleague implemented do?

The codebase you are about to review is expected to implement the flow described above. The exact business requirements are summarized below.

1. Given that the ad exchange receives a request for bids from a client, then it should respond with status 200 and a body containing the bid with highest price, when at least one of the bidders sent a bid. 
2. Given that the ad exchange receives a request for bids from a client, then it should respond with status 204 and an empty body, when none of the bidders sent a bid. 

Notes:

- The requests to the bidders should be fired in parallel to avoid high latency.
- If a bid request to a certain bidder fails then the exchange should dismiss that bid and continue its flow with the rest of the bidders.

# Where can I find the codebase?

The assignment is implemented in various popular programming languages so that you can choose the one that you feel more comfortable with. 

- [Java]()
- [Go]() 
- [Nodejs](https://github.com/Avocarrot/mx-nodejs)
- [Python]()
- [PHP]()

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

Please feel free to suggest anything you think that can be improved. Let us know the reasoning behind your suggestions. 

## Task 2

Implement your suggested improvements and implement end-to-end test cases to check that the business requirements are satisfied.

- You are free to change whatever you want in the entire codebase. You can install any dependencies you might need. There is absolutely no limitation.
- The codebase already contains some (failing) test code and fixtures. Again you can change whatever needs to be changed to make the tests run and verify that the app works as expected. Install anything you need. Change anything you need.   
- For your end-to-end test cases you will need to know how to communicate with the bidders. The API documentation for this purpose can be found [here](https://bidderapi.docs.apiary.io).

# Deliverables

When you are done implementing your changes create a new Pull Request and submit your assignment.
