# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).

![Assignment1 - model Design](https://github.com/JessilynnKim/sql/assets/166756942/11a52906-c39f-4725-b1bd-5544944de6b4)


## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.
![Assignment1 - model Design - Question2](https://github.com/JessilynnKim/sql/assets/166756942/1e934484-d505-43a3-9867-5cb0e96eac04)



## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._

Bonus: Are there privacy implications to this, why or why not?
``


Type 1 slowly changing dimension is where existing values are overwritten by new values and history is not retained. In this case, if customers are updating address, most up to date address will be in the latested record. 
Type 2 slowly changing dimension is where you add new row for the new value while maintaining existing row. This way, you have historical data and changes. In this case, if customers are updating addresses, there will be additional record which is the same for everything  but the changed field. For both types, there should be login and timestamp when the changes have been updated. Type 2 allows for auditing function and able to check if there were data issues and where the data issue occurred. Keeping customer address may lead to privacy issue. In order to avoid any issues relating to privacy, there should be customer ID and other personal detail that are not directly linked to customer address in order to minimize privacy issues but still able to get customer detail when required. 

```

## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
Your answer...
```
My ERD has simple Sales table that covers all relevant data I think is needed for Sales table. In the AdventureWorks Schema, Orders are divided into Order Detial and Order Header. This is similar to how my current company's ecommerce order reportings are done. I would not change this as often, simple reporting requires additional data table joining to get wholistic view of the sales and what has occcurred on certain day.
Employee Table in AdventureWOrks Schema has additional data compared to my Employee table. it contains information that will be useful but information such as MaritalStatus and Gender for the purpose of identifying Employee who completed sales is unnecessary. 


# Criteria

[Assignment Rubric](./assignment_rubric.md)

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `June 1, 2024`
* The branch name for your repo should be: `model-design`
* What to submit for this assignment:
    * This markdown (design_a_logical_model.md) should be populated.
    * Two Entity-Relationship Diagrams (preferably in a pdf, jpeg, png format).
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sql/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `model-design`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-3-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
