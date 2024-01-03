# Case Study🔥 - Identifying Bank’s Defaulter Customers🏦🏧

## Problem Statement
Banks rely significantly on the interest generated from loans, making the identification of defaulting customers a crucial aspect of risk management. A defaulter is a customer who either fails to pay instalments on time or is unable to make payments altogether. In this case study, our objective is identify potential credit card skippers by analyzing a year's worth of historical data.

# For Loan defaulters:
Banks face challenges in managing loan defaulters, and identifying potential risks is crucial for effective risk management. This project focuses on analyzing monthly instalment data to categorize customers as potential loan defaulters.



## Data Schema for credit card 
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


# For Loan defaulters
The loan file provides detailed information about monthly instalments, due dates, amounts, and actual clearances. The data schema includes the following fields:

* customer_id: Unique identifier for each customer.
* first_name, last_name: Customer's first and last names.
* customer_category: Category of the customer (e.g., Personal Loan, Medical Loan).
* loan_id: Unique identifier for each loan.
* loan_category: Category of the loan (e.g., Personal, Medical).
* due_date: Due date for the instalment.
* due_amount: Amount due for the instalment.
* payment_date: Date of actual payment.


# Loan management policy 
* Personal Loan: Full and timely payments are expected. Late payments or amounts less than due aren't accepted.
* Medical Loan: Late payments are accepted, but they should be the full instalment and not less than the due amount.



## Data Example for credit card skippers

Consider the following data row:
* CT28383,Miyako,Burns,R_7488,Issuers,500,490,38,101,30-01-2018

This data represents Miyako Burns, with a relationship number R_7488 and an Issuers card type. In January 2018, Miyako had a maximum monthly spending limit of $500. Out of this, she spent $490 and withdrew $38 in cash. She cleared $101 of the amount, and the payment due date was 30th January 2018.


## Assumptions and Conditions for credit card skippers

* The bill cycle is assumed to be of 30 days.
* All customers must pay the due amount on the last day of the month (30th or 31st).
* The dataset spans a year, resulting in 12 rows per customer.
* If a customer has not paid any amount in a month, the cleared_amount will be 0.


# Assumptions for Loan defaulters
* For Personal Loans, the dataset may not have 12 rows for each customer, as entries may be absent for months where payments are not made before the due date.
* For Medical Loans, it is assumed that there will be an entry for every month.

## Evaluation Criteria to figureout the skippers
The bank aims to identify potential defaulters based on specific conditions. Points are assigned to each customer according to the following criteria:

* Assign 1 point for short payment, where a short payment occurs when a customer fails to clear at least 70% of their monthly spends.
* Assign 1 point to the customer who has spent 100% of their max_credit_limit but did not clear the full amount.
* If a customer meets both conditions above in any given month, assign an additional 1 point.
* Sum up all the points for a customer and output the results in a file.


## Identifying Loan Defaulters
* Medical Loan Defaulters: Customers with a total of 3 or more late payments.
* Personal Loan Defaulters: Customers who have missed a total of 4 or more instalments OR missed 2 consecutive instalments.



This methodology allows the bank to systematically evaluate and categorize customers based on their payment behaviors, facilitating the identification of potential risks and helping in risk mitigation strategies.

## Implementation
Please check the google-colab link or the beam file in repo. 


### Thank You😀
