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

- The requests to the bidders should be fired in parallel since the calls are independent and therefore we can avoid high latency.
- If a bid request to a certain bidder fails then the exchange should dismiss that bid and continue its flow with the rest of the bidders.

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
    - [Java](https://classroom.github.com/a/tJkWEwrP)
    - [Node.js](https://classroom.github.com/a/6477OM7L)
    - [Ruby](https://classroom.github.com/a/XaYZ5VRN) 
    - Python (Work in progress)
    - Go (Work in progress)
    - PHP (Work in progress) 
2. When you accept the assignment a new repo will be created which is the one you will be working on. You have admin rights so you can do anything you want. This repo contains a branch called ```feat/ad-exchnage``` which contains the code that you will review.
2. Click on the Pull Request tab and create a new Pull Request with base branch ```master``` and source branch ```feat/ad-exchange```. Use this Pull Request ONLY to add your code review comments.
3. Add your review comments in that Pull Request.

## Task 2

Implement your suggested improvements and end-to-end test cases to check that the business requirements are satisfied.

- Please create a new branch and implement your changes on that one so that it's easier for us to review your changes.
- You are free to change whatever you want in the entire codebase. You can install any dependencies you might need. There is absolutely no limitation.
- The codebase already contains some (failing) test code and fixtures. Again you can change whatever needs to be changed to make the tests run and verify that the app works as expected. Install anything you need. Change anything you need.   
- For your end-to-end test cases you will need to know how to communicate with the bidders. The API documentation for this purpose can be found [here](https://bidderapi.docs.apiary.io).
- Your new changes should be implemented in a separate Pull Request.
- There is no need to implement unit tests, just the end to end tests!

# Deliverables

At the end you should have TWO separate Pull Requests:

1. The original Pull Request which contains your review comments.
2. The new Pull Request that contains your changes. Feel free to add any interesting approaches or important points in the PR's description.

Please do not merge or close the requests mentioned above.
