# Case Study🔥 - Identifying Bank’s Defaulter Customers🏦🏧

## Problem Statement
Banks rely significantly on the interest generated from loans, making the identification of defaulting customers a crucial aspect of risk management. A defaulter is a customer who either fails to pay instalments on time or is unable to make payments altogether. In this case study, our objective is identify potential credit card skippers by analyzing a year's worth of historical data.


## Data Schema
The dataset, contained in the "cards" file, comprises credit card payment clearance data for one year, functioning as a balance sheet for monthly dues and payments. Below is the schema for the dataset:

* customer_id: Unique identifier for each customer.
* first_name, last_name: Customer's first and last names.
* relationship_no: Relationship number assigned to the customer.
* card_type: Type of credit card (e.g., Visa, Mastercard, RuPay).
* max_credit_limit: Maximum spending limit allowed for the customer per month.
* total_spent: Total amount spent in the month or total dues.
* cash_withdrawn: Cash withdrawn from ATMs, included in the total spent.
* cleared_amount: Amount cleared by the customer in that month.
* last_date: Due date or payment date.


## Data Example

Consider the following data row:
* CT28383,Miyako,Burns,R_7488,Issuers,500,490,38,101,30-01-2018

This data represents Miyako Burns, with a relationship number R_7488 and an Issuers card type. In January 2018, Miyako had a maximum monthly spending limit of $500. Out of this, she spent $490 and withdrew $38 in cash. She cleared $101 of the amount, and the payment due date was 30th January 2018.


## Assumptions and Conditions

* The bill cycle is assumed to be of 30 days.
* All customers must pay the due amount on the last day of the month (30th or 31st).
* The dataset spans a year, resulting in 12 rows per customer.
* If a customer has not paid any amount in a month, the cleared_amount will be 0.


## Evaluation Criteria to figureout the skippers
The bank aims to identify potential defaulters based on specific conditions. Points are assigned to each customer according to the following criteria:

* Assign 1 point for short payment, where a short payment occurs when a customer fails to clear at least 70% of their monthly spends.
* Assign 1 point to the customer who has spent 100% of their max_credit_limit but did not clear the full amount.
* If a customer meets both conditions above in any given month, assign an additional 1 point.
* Sum up all the points for a customer and output the results in a file.

This methodology allows the bank to systematically evaluate and categorize customers based on their payment behaviors, facilitating the identification of potential risks and helping in risk mitigation strategies.

## Implementation
Please check the google-colab link or the beam file in repo. 


### Thank You😀
