{% include online-assignment/intro.md %}

# Objective

You are a software engineer for an advertising technology company called Blue Banana. The company wants to enter the world of real-time bidding (RTB) and you are asked to implement a real-time bidder for mobile advertising campaigns.

# What is a real-time bidder?

A bidder is simply a platform which allows advertisers to bid on mobile traffic in real-time. The traffic comes from 3rd-party ad exchanges (you do not need to worry about what an ad exchange does).

The typical flow of a bidder is:

- Bidder receives and parses a bid request from an ad exchange.
- Bidder retrieves all the available campaigns from its campaign pool.
- Bidder filters out campaigns that do not match the targeting criteria.
- If there are matching campaigns then the bidder finds the highest paying campaign and submits a bid for that campaign to the ad exchange. 
- Otherwise the bidder submits an empty response with no bid.

This whole process repeats for every new request in real-time and usually takes less than 150ms!

Check the diagram below for an illustration of the bidding process.

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

{% include online-assignment/deliverables.md %}

# End-to-end test cases

| Description | Expected input | Expected output | Parameters |
|---|---|---|---|
| Bidder should respond with a bid for the highest paying campaign that matches the targeting criteria. | [Sample Bid Request](test-cases/test-case-1-input.json) | [Expected Bid Response](test-cases/output.json) | Use [this response](test-cases/mock-campaign-api-response.json) for the Campaign API mock. | 
| Bidder should respond without a bid if there no available or matching campaigns. | [Sample Bid Request](test-cases/test-case-2-input.json) | Bid response with no body and status code 204 as specified [here](http://docs.bidderapi.apiary.io/#reference/0/ask-bidder-to-submit-a-bid/bid-response-without-a-bid). | Use [this response](test-cases/mock-campaign-api-response.json) for the Campaign API mock. |
| If we have reached the pacing threshold for a campaign then bidder should not bid with it | [Sample Bid Request](test-cases/test-case-1-input.json) | TODO | Set pacing for campaigns at 100 bids per minute |

# Mocking external dependencies

Your bidder implementation depends on an external service which exposes the [Campaign API](http://docs.campaignapi9.apiary.io/#). There is no instance of this service running therefore in your solution and tests, we expect to see this dependency mocked to simulate the real production functionality.

Please avoid hardcoding API reponses from external services! 

You are free to use any approach you like to implement mocking (mocking libraries such as Sinon.js, Mockito etc)

{% include online-assignment/assessment-criteria.md %}