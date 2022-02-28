# Banking dirty dataset.



you will be working with a retail banking dataset stored in the banking DataFrame.
The dataset contains data on the amount of money stored in accounts, their currency, amount invested, account opening date and last transaction date 
that were consolidated from American and European branches.
# ***Data cleaning.***

## ***Data type constraint.***
    First we have to make sure that our dataset is in correct datatype.

birth_date, account_opended and Last_transaction columns are in object datatype but they contain date. So, we have to convert them into datetime formate.
However, since this data was consolidated from multiple sources, you need to make sure that all dates are of the same format. You will do so by converting this column into a datetime object, while making sure that the format is inferred and potentially incorrect formats are set to missing. As The 21-14-17 entry is erroneous and leads to an error.

Uniform currencies

You are tasked with understanding the average account size and how investments vary by the size of account, however in order to produce this analysis accurately, you first need to unify the currency amount into dollars.

After having unified the currencies of your different account amounts, you want to add a temporal dimension to your analysis and see how customers have been investing their money given the size of their account over each year. The account_opened column represents when customers opened their accounts and is a good proxy for segmenting customer activity and investment over time.


### ***Cross validation.***
### How's our data integrity?

New data has been merged into the banking DataFrame that contains details on how investments in the inv_amount column are allocated across four different funds A, B, C and D.

Furthermore, the age and birthdays of customers are now stored in the age and birth_date columns respectively.

You want to understand how customers of different age groups invest. However, you want to first make sure the data you're analyzing is correct. You will do so by cross field checking values of inv_amount and age against the amount invested in different funds and customers' birthdays.

