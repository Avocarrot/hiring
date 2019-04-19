{% include header.html %}
{% include online-assignment/intro.md %}

# Objective

You are a data analyst for an advertising technology company called Blue Banana. The company manages advertiser campaigns and the people responsible for that are the account managers. A need for a new report has emerged from the account managers and you are asked to help with that.

# Context 

- Each account manager handles multiple advertising campaigns and the goal of a campaign is to acquire new users for the advertiser's mobile app.
- We track when a new user installs the advertised app and we call this event **conversion**.
- The advertiser pays us a fixed amount (called payout) for every campaign conversion. 
- The total amount an advertiser pays is called **spend**.
- Some conversions might be rejected because of fraudulent activity, expired events or any other reason so these conversions should NOT be used in our calculations.
- Some conversions might be duplicates and should NOT be used in our calculations.

# Problem

One of the biggest pain points for the account managers is that they want to know the total spend of the campaigns they manage. Currently, they have no access to any data or reports to do that.

You are asked to work on creating a report to find a solution to the problem above.

# Available data sets 

| Dataset Name | Description | Format | Download |
|---|---|---|
| Campaign info | It contains info about the campaign: the unique campaign id, the payout for each conversion and the account manager responsible for this campaign. This dataset requires to have [sqlite3](https://sqlite.org/index.html) installed on your computer. | .db (sqlite) | [Link](datasets/bluebanana.db) |
| Conversion events | The set of conversion events. Each event consists of the conversion id (which uniquely identifies a conversion) and the campaign id which identifies for which campaigns this conversion belongs to. | .csv | [Link](datasets/conversions.zip) |
| Rejected conversions | A list of conversion ids that are rejected for various reasons such as being fraudulent etc. | .txt | [Link](datasets/rejections.txt) | 

# Tasks

The assignment consists of 2 tasks.

| Task Objective | Expected Completion Time |
|---|---|
| [Task 1:](#task-1) Prepare a spreadsheet report displaying the total spend for each campaign | ~2 hours |
| [Task 2:](#task-2) Describe briefly the process followed to produce the report | ~1 hour |

## Timing assumptions

The time estimatations for the tasks above assume that you are familiar or have professional experience with combining data sets, scripting languages, SQL databases and basic spreadsheet tools.

## Task 1

Prepare a spreadsheet report where the user would be able to:

- See a list of campaigns along with their total spend. Each row is a different campaign and there are 3 columns: campaign id, total spend and account manager name.
- Filter by account manager name so they can focus on their own campaigns

### Important note

This position requires the knowledge of scripting languages such as Python or R. Therefore, it is highly reccommended to use these instead of tools such as PowerBI etc to implement the solution. 
In other words we want to see your scripting/coding skills :)

### Deliverables

- The final sheet report which satisfies the requirements described above.

## Task 2

Describe briefly the process followed to produce the report. Please document any important steps, tools or processes that you used to get to the final report.

Please keep this summary as short as possible in order to be able to stay within the time limits. 

### Deliverables

- A short summary explaining the process you followed to produce the report. This can be a text file, Google doc or anything similar.
- Any scripts or screenshots from tools used during the process.

# How to submit the assignment

You can send us an email with:

- either all the deliverables attached in a zip file
- Or if you used online tools such as Google Sheets etc you can send us the links 
