{% include online-assignment/intro.md %}

{% include online-assignment/assessment-criteria.md %}

# Objective

You are a software engineer for an advertising technology company called Blue Banana. The company wants to enter the world of real-time bidding (RTB) and you are asked to implement a real-time bidder for mobile advertising campaigns.

# What is a real-time bidder?

A bidder is simply a platform which allows advertisers to bid on mobile traffic in real-time. The traffic comes from 3rd-party ad exchanges (you do not need to worry about what an ad exchange does).

The typical flow of a bidder is:

- Bidder receives and parses a bid request from an ad exchange.
- Bidder retrieves all the available campaigns from its campaign pool.
- If there are available campaigns then the bidder finds the highest paying campaign and responds back with a bid for that campaign. 
- Otherwise the bidder submits an empty response with no bid.
- When the exchange receives our bid it runs an auction and if we win then we get to show our ad in the mobile app traffic. 

This whole process repeats for every new request in real-time and usually takes less than 150ms!

Check the diagram below for an illustration of the bidding process.

[TODO: Diagram]

# Tasks

The assignment is split into three tasks. Each task builds on the things you have completed in the previous parts. The tasks are increasing in difficulty. 

## Part 1: Implement the basic bidder flow

You will need to implement the basic flow of a bidder which was described above.

You are given the following:

1. The [docs for the bidder API (bid request and bid response format)](http://docs.bidderapi.apiary.io/) which specifies the protocol between our bidder and the ad exchange.
2. The [docs for the campaign API](http://docs.campaignapi9.apiary.io/#) which can be used to retrieve the available campaigns.

### Test case 1: Bidder responds with a bid

**Expected input:** 

**Expected output:** 

### Test case 2: Bidder responds without a bid (no available campaigns)

**Expected input:** Use the same example bid request as in the previous test case.

**Expected output:** A bid response with no body and status code 204 as specified in the [Bidder API]((http://docs.bidderapi.apiary.io/))

## Part 2: Extend your bidder to be able to filter out campaigns based on targeting

You are asked to extend the functionality developed in Part 1 so that we can filter out campaigns based on targeting. 

You will notice that each campaign contains a targetedCountries array which contains the country codes that the campaign is targeting.

Based on the info contained in the bid request you should be able to filter out campaigns which do not target the country specified in the bid request.

### Test case 3:

You should fix [Test Case 1](#test-case-1) from the previous part which now should be failing since we added a constraint in the available campaigns.

## Part 3 (optional): Implement a basic pacing algorithm

For the final step we want to implement a basic pacing algorithm. The pacing controls the rythm by which we are alowed to bid for a given campaign. Take for example a pacing of 100 bids per minute. This means that for each campaign we are only allowed to bid at most 100 times per minutes. If this threshold is exceeded for one campaign then no more bids from that campaign should occur until the minute has passed.

# Deliverables

In your uploaded solution you should include:

- The complete working code (so that we can run your solution on our machines).
- Passing end-to-end tests for the test cases listed above.
- Step-by-step instructions on how to run your code and tests (how to compile, how to install dependencies, how to run code etc). 