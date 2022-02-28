# Banking dirty dataset.



you will be working with a retail banking dataset stored in the banking DataFrame.
The dataset contains data on the amount of money stored in accounts, their currency, amount invested, account opening date and last transaction date 
that were consolidated from American and European branches.
# ***Data cleaning.***

## ***Data type constraint.***
    First we've to make sure that our dataset is in correct datatype.

***"birth_date", "account_opended" and "Last_transaction" columns*** are in object datatype but they contain dates. So, We've to convert them into ***datetime formate***.
However, since this data was consolidated from multiple sources, you need to make sure that all dates are of the same format. You will do so by converting this column into a datetime object, while making sure that the format is inferred and potentially incorrect formats are set to missing. As The 21-14-17 entry is erroneous and leads to an error.

## Uniformaty.
       Uniform currencies
        
we're tasked with understanding the average account size and how investments vary by the size of account, however in order to produce this analysis accurately, you first need to unify the currency amount into dollars.

After having unified the currencies of your different account amounts, you want to add a temporal dimension to your analysis and see how customers have been investing their money given the size of their account over each year. The account_opened column represents when customers opened their accounts and is a good proxy for segmenting customer activity and investment over time.


### ***Cross validation.***
### How our data is integrity?

   A common challenge is data integrity, or more broadly making sure that our data is correct
   inv_amount & Age columns
   
New data has been merged into the banking DataFrame that contains details on how investments in the inv_amount column are allocated across four different funds A, B, C and D.
Furthermore, the age and birthdays of customers are now stored in the age and birth_date columns respectively.
You want to understand how customers of different age groups invest. However, you want to first make sure the data you're analyzing is correct.
We'll do so by cross field checking values of inv_amount and age against the amount invested in different funds and customers' birthdays.
inv_amount column.

Find the rows where the sum of all rows of the fund_columns in banking are equal to the inv_amount column.

![inv 1](https://user-images.githubusercontent.com/84151016/156050685-a0d9babb-5b82-4187-855d-3db80fc8f5aa.jpeg)


Age column.

We will manually calculate customers' ages. But because our dataset has been collected in 2020, we will suptract the customers' ages from 2020.
Find all rows of banking where the age column is equal to ages_manual and then filter banking into consistent_ages and inconsistent_ages.

Awesome work! There are only 8 and 8 rows affected by inconsistent inv_amount and age values respectively. In this case, it's best to investigate the underlying data sources before deciding on a course of action!

Another way to verify or investigate the correctness of the age of customers.
We have the date of birth of each customer and it;s assumed that all those born in the same year nearly have the same age, and from this principle we'll extract the year in which all the customers were born and check whether the same customers were born in the same year same age or not.

Age
birth_year	Age	
1961	59	2
            63	1
1962	58	6
1963	57	4
1965	55	2
1966	54	2
1967	53	3
1968	52	3
            56	1
1969	51	2
1970	50	3
1971	49	2
1972	48	5
1973	47	3
1974	46	8
            50	1
1975	45	3
            49	2
1976	44	1
1977	43	1
1978	42	3
1979	41	1
1980	40	2
1981	39	2
1982	38	2
1983	37	2
1984	36	4
1985	35	1
1986	34	1
1987	33	2
1988	32	1
            36	1
1989	31	6
1990	30	3
            34	2
1991	29	3
1992	28	6
1993	27	3

As we can observe we have some samples born in the same year but with big variation in age, and this is so weird !
As in 1961	we have two customers have 59 years old and one has 63 years old, how could that possible !
three customers were born in 1968 and have 52 and that's right, what about the person with 56 years old and born in the same year. 
and the same for 1990, 1988, 1975

![age 1](https://user-images.githubusercontent.com/84151016/156052448-662907de-83da-45bf-aceb-667b7ea7ed3a.jpeg)

Doing the same for inv_amoubnt, we will create new column for investment amount validation.
