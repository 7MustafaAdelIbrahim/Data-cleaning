
# <u>***Data cleaning***</u>.

It's commonly said that data scientists spend ***80%*** of their time ***cleaning and manipulating data*** and only ***20%*** of their time ***analyzing it***. The time spent cleaning is vital since ***analyzing dirty data can lead you to draw inaccurate conclusions and misleading results***. 
As Without making sure that data is properly cleaned in the ***exploration and processing phase***, we will surely compromise the insights and reports subsequently generated, and the ***results of any data analysis*** or ***machine learning model could be inaccurate***.
	As the old says "garbage in garbage out".
![image](https://user-images.githubusercontent.com/84151016/155360484-8d37b205-3d2d-4caa-aed3-f2dd103535a1.png)

#### Dirty data can appear because of duplicate values, mis-spellings, data type parsing errors and legacy systems. 

## Data type constraints
We have to make sure that data is in correct type.
Luckily, ***Python has specific data type objects***  for various data types. This makes it much easier to manipulate these various data types in Python.

As such, before preparing to analyze and extract insights from our data, we need to make sure our variables have the correct data types, other wise we risk compromising our analysis. 
If there is ***any strip*** in the column, and is we want to do ***mathematics operation***, such as summing and multiplication, returns one ***large concatenated string*** containing each row's string not numerical outputs.

![image](https://user-images.githubusercontent.com/84151016/155360939-fe1437b9-b4d0-4d46-ab70-c62c6c8d62c2.png)

##### Numeric or categorical ?
If it represents categories with a finite set of possible categories. This is called categorical data.
For example. ***marriage status***, ***takes never married***, ***married***, ***separated***, ***divorced***.

## Data range constraints 
If we have samples are ***well above the allowable range***.
This is most likely ***an error in data collection or parsing***, and ***treating it is essential to have accurate analysis***.

![24190018-18436faca7405759b074f6c4e544c2d3](https://user-images.githubusercontent.com/84151016/158670548-b3919eff-7465-4e7f-895d-a8835a7385a8.png)


   #### How to deal with out of range data?
There's a ***variety of options*** to deal with out of range data. 
The simplest option is to drop the data. 
depending on the size of your out of range data, you could be losing out on essential information. 	  
	As a rule of thumb.
	only drop data when a small proportion of your dataset is affected by out of range values.
	  
However, you really need to understand your dataset before deciding to drop values. 
Another option, setting custom minimums or maximums to your columns. 
We could also set the data to missing, and impute it.
We could also, dependent on the business assumptions behind our data, 
assign a custom value for any values of our data that go beyond a certain range.
 
## Duplicate values 
   ### Complete duplicates.
   It can be diagnosed when we have the same exact information repeated across multiple rows.
   ![complete duplicates](https://user-images.githubusercontent.com/84151016/155366890-f3690e9d-feae-47ad-9067-91b181fae3a4.jpeg)

   ### ***Duplicates with discrepancies***.
   If there are ***duplicate values for all columns except one column***, 
   which leads us to think ***it's more likely a data entry error than an actual other sample***.
   ![image](https://user-images.githubusercontent.com/84151016/155361152-c8ed89c5-bd77-4b7c-8189-50dd51f42dc3.png)

duplicate data can also arise because of ***Apart from data entry*** and ***human errors*** 
or *** bugs and design errors whether in business processes or data pipelines***.
However, they often most arise from ***the necessary act of joining and consolidating data from various resources***. 
![image](https://user-images.githubusercontent.com/84151016/155361237-9ce93848-5973-425a-91bf-61a7c8e7f5f9.png)

  ### How to treat duplicate values?
***The complete duplicates*** can be treated easily. All that is required is to ***keep one of them only and discard the others***. 

***Duplicate with discrepancies***. Apart from dropping rows with really small discrepancies, we can use a ***statistical measure to combine or aggregate each set of duplicated values***.

## Categories and membership constraints ***(uniqueness constraints)***.

categorical data represent variables that represent predefined finite set of categories.
***To run machine learning models*** on categorical data, they are ***often coded as numbers***.

![membership constaint](https://user-images.githubusercontent.com/84151016/155367201-4fd87463-3b76-441c-ae1e-a36b1f678d33.jpeg)

Since categorical data represent a predefined set of categories, they can't have values that go beyond these predefined categories.
  ### Why could we have inconsistencies in our categorical data ?
  
![why membership constaint](https://user-images.githubusercontent.com/84151016/155368158-dbf2a485-b408-4803-8517-54e031af7f54.jpeg)

We can have ***inconsistencies in our categorical data*** for a variety of reasons. 
This could be due to ***data entry issues with free text vs dropdown fields***, ***data parsing errors and other types of errors***. 

   ### How do we treat these problems?
There's a ***variety of ways we can treat these***, with increasingly specific solutions for different types of inconsistencies.
Most simply, we can ***drop the rows with incorrect categories***. 
We can attempt ***remapping incorrect categories to correct ones***.

![how to treat membership constaints](https://user-images.githubusercontent.com/84151016/155368225-5f971400-5959-4333-ab7e-12ea0aa94af7.jpeg)

   ### the presence of too many categories that could be collapsed into a few ***(Value consistency)***.
   -having values that slightly differ because of ***capitalization***. Not treating this could lead to misleading results. 
   To deal with this, we can ***either capitalize or lowercase***.
   -leading or trailing white spaces***. 
    To deal with it, we can ***remove spaces***.
    
    ![what type of error do we have in memnership consatint](https://user-images.githubusercontent.com/84151016/155373250-7eb3709d-9261-45a8-83b8-dafdc4a0c0f0.jpeg)

   ### Collapsing data into categories.
Sometimes, we may want to create categories out of our data, such as creating household income groups from income data column in the demographics DataFrames.

![24190379-59c36cf8215ee6ebb127f1fe9aa89a14](https://user-images.githubusercontent.com/84151016/158673629-162f541d-19ae-464c-89a8-946cdd2d4aed.png)


More explanition

![24039531-bec2ded0af5f430dc6d36d313f7f00ca](https://user-images.githubusercontent.com/84151016/158668826-48a52dc7-042a-4ad0-a83a-683a8f9e33f6.png)
![24039629-e0b088055fe14be3fbc8a5c468474eea](https://user-images.githubusercontent.com/84151016/158674381-309928a7-af63-4d78-8a9f-cfbfc4fb36c4.png)



## Clean text data.
	Cleaning text data and regular expressions.
![clean text data](https://user-images.githubusercontent.com/84151016/155368653-b3257987-eeed-4395-8389-896a4766d502.jpeg)

Common text data problems include handling inconsistencies, making sure text data is of a certain length, typos and others. 
Remove additional strips and special characters like dashes, for example phone numbers are aligned to begin with 00
But what about more complicated examples?  What if phone numbers can contain a range of symbols from plus signs, dashes, parenthesis and maybe more?!  

#### But what about more complex problems in text data ?!
Like in this figure.

![complicated examples + regular expression](https://user-images.githubusercontent.com/84151016/155368918-9547569c-6244-4644-b53d-01eb8d44a538.jpeg)

#### ***This is where regular expressions come in***. 
Regular expressions give us the ability to search for any pattern in text data, 
like only digits for example. They are like control + find in your browser, but way more dynamic and robust. 
more advanced data cleaning problems, such as uniformity, cross field validation and dealing with missing data. when left untouched, can skew your analysis.

## Unit uniformity.
Values are recorded in ***different units of measure***. It's a problem that could ***similarly skew our data***.  
For example, ***temperature data in Celsius and Fahrenheit*** merged together, or ***weight data in Kilograms and in stones***.
or ***Uniform currencies***, data on the amount of money stored in ***different currencies***. 
![uninformatiy](https://user-images.githubusercontent.com/84151016/155369078-e9e2c12d-a539-44c1-b624-20763db459b0.jpeg)

Verifying unit uniformity is imperative to having ***accurate analysis***. 
![uninformaty+ cilisious](https://user-images.githubusercontent.com/84151016/155369208-27b4cfb4-80d6-4282-a7e7-c86d3b58bdaf.jpeg)

You don’t have to memorize all different units of measure  you may encounter, A simple web search returns the formula for converting Fahrenheit to Celsius.

![tempreture data](https://user-images.githubusercontent.com/84151016/155369248-b37f0180-1b08-41c4-b614-7aca9ce867a4.jpeg)

### ***Dates in multiple formats***.

another common uniformity problem with date data. 
DataFrame containing birth dates for a variety of individuals. It may have been collected from a variety of sources and merged into one. 
one has the month/ day /year format, whereas anther one has the month written out. one more looks like a day /day /year format. 
![datetime formate](https://user-images.githubusercontent.com/84151016/155369625-30367f05-d9b1-4988-95ab-a4fe68e27936.jpeg)

### What is the best way to unify the formats for ambiguous values such as 2019-04-07?!
a common problem is having ambiguous dates with vague formats. For example, 03-08-2021 is this date value set in March or August? 
Unfortunately, there's no clear way to spot this inconsistency or to treat it. 

![ambigous dateformate](https://user-images.githubusercontent.com/84151016/155369977-0aed31b9-2bda-4a30-8396-a2ecb09300b1.jpeg)

Depending on the size of the dataset and suspected ambiguities, we can either convert these dates to NAs and deal with them accordingly.
If you have additional context on the source of your data, you can probably infer the format.
You don't have to memorize these formats, just know that they exist and are easily searchable! 

## Cross field validation.

![cross field validation](https://user-images.githubusercontent.com/84151016/155371585-c5ba0556-aab6-469d-9109-fa71a10ed6d2.jpeg)

If dataset have been collected and merged from different sources, and a common challenge is data integrity, or more broadly making sure that our data is correct.
This is where cross field validation comes in. It's the use of multiple fields in your dataset to sanity check the integrity of your data.

![image](https://user-images.githubusercontent.com/84151016/155361733-871d805e-2432-44f3-9c8e-f4e985afbc36.png)

   ### For example, flights dataset, this could be summing economy, business and first class values. 
Cross field validation is to make sure they are equal to the total passengers on the plane.
 This could be easily done in Pandas, by first subsetting on the columns to sum, 
 then using the sum method with the axis argument set to 1 to indicate row wise summing. 
 We then find instances where the total passengers column is equal to the sum of the classes. 
 And find and filter out instances of inconsistent passenger amounts by subsetting on the equality we created with brack.
 
   ### another example, birthdays and age values for a set of users. 
We can for example make sure that the age and birthday columns are correct by subtracting the number of years between today's date and each birthday. 

   #### What to do when we spot inconsistencies with cross-field validation ?
Just like other data cleaning problems, there is no one size fits all solution, 
as often the best solution requires an in depth understanding of our dataset. 
We can decide to either drop inconsistent data, set it to missing and impute it, or apply some rules due to domain knowledge. 
All these routes and assumptions can be decided upon only when you have a good understanding of where your dataset 
that comes from and the different sources feeding into it. 

## Completeness and missing data. 
What is missing data?
Missing data is one of the most common and most important data cleaning problems. 
Essentially, It's when no data value is stored for a variable in an observation, mostly commonly represented as NA or NaN, 
but it can take on arbitrary values like 0 or dot.

![why missingness](https://user-images.githubusercontent.com/84151016/155371870-28720b25-4918-4c9c-83e9-c687479ea290.jpeg)

Like a lot of the problems, it's commonly due to technical or human errors. 
Missing data can take many forms. 

	 The missingno package allows to create useful visualizations of our missing data.
	 We will talk about missingno package in Dealing with missingness folder in this repository.

### Missingness types
This leads us to missingness types. there are a variety of types of missing data.
#### • Missing Completely at Random data: 
is when there's missing data completely due to randomness, and there is no systematic relationship between missing 
data and remaining values, such data entry errors. 
#### • Missing at Random data: 
Despite a slightly deceiving name, It's when there is a systematic relationship between missing data and other observed values.
#### • Missing not at Random: 
There is a systematic relationship between a column's missing values and unobserved values.
![image](https://user-images.githubusercontent.com/84151016/155361796-9d6b9ece-d71a-4e24-aba3-091c11046b6b.png)

## How to deal with missing data?
There's a variety of ways of dealing with missing data.
   #### 1- dropping missing data.
   #### 2-imputing them with statistical measures such as mean, median or mode, 
   #### 3-imputing them with more complicated algorithmic approaches or ones that require some machine learning. 
	Each missingness type requires a specific approach, and each type of approach has drawbacks and positives.
