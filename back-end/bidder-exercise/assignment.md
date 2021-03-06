{% include header.html %}
{% include online-assignment/intro.md %}

# Objective

You are a software engineer for an advertising technology company called Blue Banana. The company wants to enter the world of real-time bidding (RTB) and you are asked to implement a real-time bidder for mobile advertising campaigns.

# What is a real-time bidder?

A bidder is simply a platform which allows advertisers to submit bids to buy mobile ad space in real-time. A bidder receives bid requests from 3rd-party ad exchanges and responds back with a bid response. This bid then competes with bids from other bidders in a real-time auction at the exchange. The highest bid (in terms of bid price) wins and gets to show its ad. You can see this process illustrated below.
  
![auction-process](/static/auction-process.jpg){:width="100%"}

For this assignment we will focus on building a bidder so you do not need to worry about what happens at the ad exchange. If we zoom into what a bidder does then the typical flow is outlined below:

- Bidder receives and parses a bid request from an ad exchange.
- Bidder retrieves all the available campaigns from its campaign pool.
- Bidder filters out campaigns that do not match the targeting criteria.
- If there are matching campaigns then the bidder finds the highest paying campaign and submits a bid for that campaign to the ad exchange. 
- Otherwise the bidder submits an empty response with no bid.

![bidder-process](/static/bidder-process.jpg){:width="100%"}

# Tasks

The assignment consists of one task.

| Task Objective | Expected Completion Time |
|---|---|
| [Task 1:](#task-1) Implement the basic bidder flow | ~2 hours |

## Timing assumptions

The time estimates for the tasks above assume that you are familiar or jave professional experience with testing techniques and building basic web apps.

## Task 1

### Objective

You will need to implement the basic flow of a bidder which was described above.

### You are given the following

1. The [docs for the bidder API](http://docs.bidderapi.apiary.io/) which specifies the protocol between our bidder and the ad exchange.
2. The [docs for the campaign API](http://docs.campaignapi9.apiary.io/) which can be used to retrieve the available campaigns.
3. For the targeting matching you should use the country info contained in the bid request and check it against the list of *targetedCountries* for each campaign.
4. For the campaign ranking you should use the *price* info of the campaign.

### Mocking the Campaign API

Your bidder implementation depends on an external service which exposes the [Campaign API](http://docs.campaignapi9.apiary.io/#). There is no instance of this service running, therefore in your tests, we expect to see this dependency mocked to simulate the real production functionality.

You are free to use any approach you like to implement mocking.

{% include online-assignment/test-cases-intro.md %}

| Description | Expected input | Expected output | Parameters/Mocks |
|---|---|---|---|
| Bidder should respond with a bid for the highest paying campaign that matches the targeting criteria. | [Sample Bid Request](test-cases/test-case-1-input.json) | [Expected Bid Response](test-cases/output.json) | Use [this response](test-cases/mock-campaign-api-response.json) for the Campaign API mock. | 
| Bidder should respond without a bid if there no available or matching campaigns. | [Sample Bid Request](test-cases/test-case-2-input.json) | Bid response with no body and status code 204 as specified [here](http://docs.bidderapi.apiary.io/#reference/0/ask-bidder-to-submit-a-bid/bid-response-without-a-bid). | Use [this response](test-cases/mock-campaign-api-response.json) for the Campaign API mock. |

{% include online-assignment/deliverables.md %}

{% include online-assignment/assessment-criteria.md %}
