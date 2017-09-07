{% include online-assignment/intro.md %}

# Objective

You are a software engineer for an advertising technology company called Blue Banana. The company wants to enter the world of real-time bidding (RTB) and you are asked to implement a real-time bidder for mobile advertising campaigns.

# What is a real-time bidder?

A bidder is simply a platform which allows advertisers to bid on mobile traffic in real-time. The traffic comes from 3rd-party ad exchanges (you do not need to worry about what an ad exchange does).

The typical flow of a bidder is:

- Bidder receives and parses a bid request from an ad exchange.
- Bidder retrieves all the available campaigns from its campaign pool.
- Bidder filters out campaigns that do not match the targeting criteria.
- If there are matching campaigns then the bidder finds the highest paying campaign and submits a bid for that campaign. 
- Otherwise the bidder submits an empty response with no bid.
- When the exchange receives our bid it runs an auction and if we win then we get to show our ad in the mobile app traffic. 

This whole process repeats for every new request in real-time and usually takes less than 150ms!

Check the diagram below for an illustration of the bidding process.

[TODO: Diagram]

# Tasks

The assignment is split into seperate tasks. Each task builds on the work done for the previous ones. 

| Task Objective | Expected Completion Time |
|---|---|
| [Task 1:](#task-1) Implement the basic bidder flow | ~1 hour |
| [Task 2:](#task-2) Implement a basic pacing algorithm | ~2 hours |

## Task 1

You will need to implement the basic flow of a bidder which was described above.

### You are given the following

1. The [docs for the bidder API](http://docs.bidderapi.apiary.io/) which specifies the protocol between our bidder and the ad exchange.
2. The [docs for the campaign API](http://docs.campaignapi9.apiary.io/) which can be used to retrieve the available campaigns.
3. For the targeting matching you should use the country info contained in the bid request and check it against the list of *targetedCountries* for each campaign.
4. For the campaign ranking you should use the *price* info of the campaign.

## Task 2

For the final task we want to implement a basic pacing algorithm. The pacing controls the rythm by which we are alowed to bid for a given campaign. 

Take for example a pacing of 100 bids per minute. This means that for each campaign we are only allowed to bid at most 100 times per minute. If this threshold is exceeded for a campaign then no more bids from that campaign should occur until the minute has passed.

# Deliverables

In your uploaded solution you should include:

1. The complete working code (so that we can run your solution on our machines).
2. Step-by-step instructions on how to run your code and tests (how to compile, how to install dependencies, how to run code etc). 
3. Passing end-to-end tests for the test cases listed below.

## Test cases

| Number | Description | Expected input | Expected input | 
|---|---|---|---|
| 1 | Bidder should respond with a bid for the highest paying campaign if there is one | TODO | TODO |
| 2 | Bidder should respond without a bid if there no available or matching campaigns | TODO | A bid response with no body and status code 204 as specified in the [Bidder API](http://docs.bidderapi.apiary.io/). |
| 3 | If we set a pacing of 100 bids per minute per campaign then bidder should respect this pacing requirement | TODO | TODO |

# Mocking external dependencies

For your bidder implementation you depend on an external service exposing the [Campaign API](http://docs.campaignapi9.apiary.io/#). There is no instance of this service running therefore in your solution and tests, we expect to see this dependency mocked to simulate the real production functionality.

Please avoid hardcoding API reponses from external services! 

You are free to use any approach you like to implement mocking (mocking libraries such as Sinon.js, Mockito etc)

{% include online-assignment/assessment-criteria.md %}