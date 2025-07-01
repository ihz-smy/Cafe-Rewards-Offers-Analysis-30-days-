# Cafe Rewards Offers Analysis (30 days)

## Project Background and Overview
This analysis examines the behavior of Cafe Rewards members over a 30-day period, including their transactions and responses to promotional offers.

Customers receive offers once every few days and have a limited time to redeem them. These can be informational offers (simple advertisement of a product), discount offers, or "buy one, get one" (BOGO) offers. Each customer receives a different mix of offers, attempting to maximize their probability of making a purchase.

Every customer purchase during the period is marked as a transaction. For a transaction to be attributed to an offer, it must occur at the same time as when the offer was "completed" by the customer.

The KPIs we are investigating are these metrics: offers completed, completion rate, revenue and profile members based on these attributes: gender, age, income. Recommendations will be used by marketing team to better understand customer segmentation and to better allocate resources for future campaigns.

## Project Goals
1. Evaluate the Cafe's revenue in the 30-day period to identify successful offers
2. Identify patterns in offer completion rate to improve future campaigns
3. Provide recommendations for business growth through better marketing plans

## Data structure overview
- Offers: Reference the offers table with the offer_id, offer_type, difficulty, reward, duration and channels of each offer campaign
- Customers: Reference the customers with all members' information including when they became a member, gender, age and income
- Events: Each record represents one of the following interation between the customers and the offers: offer received, offer viewed, transaction and offer completed, documenting the customer_id, event, offer_id and the time of the interaction
![image](https://github.com/user-attachments/assets/af9313e9-5858-4e53-adc8-37d23d2fc235)

## Executive Summary
In the span of 30 days, 33579 offers were completed, divided by the total number of offers that members received, marks the completion rate of 55%. Offers with code 6 and 7 performed the best with completion rate at 67% and 70%, respectively. Both of them are discount offers. All discount offers performed relatively better than buy-one-get-one overall. Revenue remained quite stable throughout the week with a slight peak in Tuesday except for the 5th week. Members of the Cafe lean more to the older and wealthier side, the most significant age group is 35-50 and have a 40k+ income. Those that earn better were more likely to complete offers, the 80k+ group have a completion rate of 61%, almmost doubling 34% of the less than 40k group. 

## Insights deep dive
### Overall revenue
![image](https://github.com/user-attachments/assets/7c43cb56-a65d-47de-b3b4-ff27136dc564)
Revenue remained quite stable throughout the week and over the 30-day span, ranging from 50k to 77k. Every Tuesday except for the final week showcased a slight peak of the week. 

### Members demographic
![image](https://github.com/user-attachments/assets/2c9fb2e4-7338-4c2f-8aad-8b770cc24e97)
Revenue remained quite stable throughout the week with a slight peak in Tuesday except for the 5th week. Members of the Cafe lean more to the older and wealthier side, the most significant age group is 35-50 (~5700 members) and have a 60k+ income (~4600 members).

### Offers performance
![image](https://github.com/user-attachments/assets/560fcca5-5ed7-4382-b0cb-edc7bf5cf43b)
Offers with code 6 and 7 performed the best with completion rate at 67% and 70%, respectively. Both of them are discount offers. All discount offers performed relatively better than buy-one-get-one overall. Buy-one-get-one offer code 4, despite the lower diffuculty at 5 and higher reward at 5 compared to code 6, 7, was viewed by less people (roughly 4200 compared to 7300), confirming that discount offers are more attractive to members. Discount offer code 5 has very low completion rate (44%), possibly due to the highest difficulty, 20.


![image](https://github.com/user-attachments/assets/737ba417-e9bf-4f81-a303-85cee98dfa8c)


Although informational offers with code 3 and 8 can't have any offers completed, there actually were transactioned made that were possibly influenced by these offers


![image](https://github.com/user-attachments/assets/4fff3ea7-6fbd-4012-b03b-692f4fd7e1fb)


Gender and age don't seem to affect much on the completion rate, only that people at 80+ were much less likely to complete offers with the rate of 20%. Meanwhile, the completion rate and income seem to have a closer relationship, the 80k+ group have a completion rate of 61%, almmost doubling the 34% rate of the less than 40k group. 


## Recommendations
- Allocate resources more on discount offers and less on buy-one-get-one offers as members are more attracted to discount offers, as presented by the completion rates of each offers
- Take into consideration the difficulty level for future campaigns as offers that are too difficult may not perform well, given the 44% completion rate of the offer code 5
- Given that the cafe right now does not seem to have a rush day, run events, campaigns at weekend to attract more customers or leverage Tuesday and promote weekday activities
- Take into account the members demographic of older and wealthier people to build more suitable campaigns and offers in the future

## Technical details
- Excel (Power Query and Power Pivot): Data cleaning and visualization

## Caveats and Assumptions
- Data Completeness: 12% customers are in the unclassified gender, 13% outlier values of 91+ age, 12% missing income
- Timeline: The data doesn't provide when the 30-day period start in the week so the analysis assumes it's Monday
