It's commonly said that data scientists spend ***80%*** of their time ***cleaning and manipulating data*** and only ***20%*** of their time ***analyzing it***. The time spent cleaning is vital since ***analyzing dirty data can lead you to draw inaccurate conclusions and misleading results***. 
As Without making sure that data is properly cleaned in the ***exploration and processing phase***, we will surely compromise the insights and reports subsequently generated, and the ***results of any data analysis*** or ***machine learning model could be inaccurate***.

#### As the old says, ***garbage in garbage out***. 

#### Dirty data can appear because of duplicate values, mis-spellings, data type parsing errors and legacy systems. 
## Data type constraints
Luckily, ***Python has specific data type objects***  for various data types. This makes it much easier to manipulate these various data types in Python.

As such, before preparing to analyze and extract insights from our data, we need to make sure our variables have the correct data types, other wise we risk compromising our analysis. 

If there is ***any strip*** in the column, and is we want to do ***mathematics operation***, such as summing and multiplication, returns one ***large concatenated string*** containing each row's string not numerical outputs. 

## Numeric or categorical?
represents categories with a finite set of possible categories. This is called categorical data.
#### For example. ***marriage status***, ***takes never married***, ***married***, ***separated***, ***divorced***.

## Data range constraints 
If we have samples are ***well above the allowable range***. 
This is most likely ***an error in data collection or parsing***, and ***treating it is essential to have accurate analysis***. 

## How to deal with out of range data?
There's a ***variety of options*** to deal with out of range data. 

***The simplest option*** is to ***drop the data***. depending on the size of your out of range data, you could be losing out on essential information. 
***As a rule of thumb***, only drop data when a small proportion of your dataset is affected by out of range values, however you really need to understand your dataset before deciding to drop values. 

***Another option***, ***setting custom minimums or maximums to your columns***. We could also set the data to missing, and impute it.
 We could also, dependent on the business assumptions behind our data, assign a custom value for any values of our data that go beyond a certain range.
 
## Duplicate values 
	## ***Complete duplicates***.
It can be diagnosed when we have the same exact information repeated across multiple rows, 
	## ***Duplicates with discrepancies***.
If there are ***duplicate values for all columns except one column***, which leads us to think ***it's more likely a data entry error than an actual other sample***. 

duplicate data can also arise because of ***Apart from data entry*** and ***human errors*** or *** bugs and design errors whether in business processes or data pipelines***.
However, they often most arise from ***the necessary act of joining and consolidating data from various resources***. 

## How to treat duplicate values?
***The complete duplicates*** can be treated easily. All that is required is to ***keep one of them only and discard the others***. 

***Duplicate with discrepancies***. Apart from dropping rows with really small discrepancies, we can use a ***statistical measure to combine or aggregate each set of duplicated values***.

## Categories and membership constraints ***(uniqueness constraints)***.

categorical data represent variables that represent predefined finite set of categories.
***To run machine learning models*** on categorical data, they are ***often coded as numbers***. 

Since categorical data represent a predefined set of categories, they can't have values that go beyond these predefined categories. 
We can have ***inconsistencies in our categorical data*** for a variety of reasons. 
This could be due to ***data entry issues with free text vs dropdown fields***, ***data parsing errors and other types of errors***. 

  ### How do we treat these problems?
There's a ***variety of ways we can treat these***, with increasingly specific solutions for different types of inconsistencies.
Most simply, we can ***drop the rows with incorrect categories***. 
We can attempt ***remapping incorrect categories to correct ones***.

  ### the presence of too many categories that could be collapsed into a few ***(Value consistency)***.
      #### having values that slightly differ because of ***capitalization***. Not treating this could lead to misleading results. 
          To deal with this, we can ***either capitalize or lowercase***,  
      ##### ***leading or trailing white spaces***. 
                To deal with it, we can ***remove spaces***.
## Collapsing data into categories.

Sometimes, we may want to create categories out of our data, such as creating household income groups from income data column in the demographics Data Frame
Cleaning text data and regular expressions. 
Common text data problems include handling inconsistencies, making sure text data is of a certain length, typos and others. 
Remove additional strips and special characters like dashes, for example phone numbers are aligned to begin with 00
But what about more complicated examples?  What if phone numbers can contain a range of symbols from plus signs, dashes, parenthesis and maybe more?!  
This is where regular expressions come in. Regular expressions give us the ability to search for any pattern in text data, like only digits for example. They are like control + find in your browser, but way more dynamic and robust. 
more advanced data cleaning problems, such as uniformity, cross field validation and dealing with missing data. when left untouched, can skew your analysis. 
Uniformity
Values are recorded in different units of measure. It's a problem that could similarly skew our data, which is unit uniformity.  
For example, temperature data in Celsius and Fahrenheit merged together, or weight data in Kilograms and in stones, 
Uniform currencies which means that it contains data on the amount of money stored in accounts
dates in multiple formats. Verifying unit uniformity is imperative to having accurate analysis. 
You don’t have to memorize all different units of measure  you may encounter, A simple web search returns the formula for converting Fahrenheit to Celsius.
another common uniformity problem with date data or Uniform dates
 DataFrame containing birth dates for a variety of individuals. It may have been collected from a variety of sources and merged into one. one has the month/ day /year format, whereas anther one has the month written out. one more looks like a day /day /year format. 
YYYY-mm-dd and YYYY-dd-mm. What is the best way to unify the formats for ambiguous values such as 2019-04-07?
You don't have to memorize these formats, just know that they exist and are easily searchable! 
However, a common problem is having ambiguous dates with vague formats. For example, 03-08-2021 is this date value set in March or August? Unfortunately, there's no clear way to spot this inconsistency or to treat it. Depending on the size of the dataset and suspected ambiguities, we can either convert these dates to NAs and deal with them accordingly. If you have additional context on the source of your data, you can probably infer the format.
Video2
Cross field validation
cross field validation for diagnosing dirty data. 
If dataset have been collected and merged from different sources, and a common challenge is data integrity, or more broadly making sure that our data is correct.
This is where cross field validation comes in. It's the use of multiple fields in your dataset to sanity check the integrity of your data. 
For example, flights dataset, this could be summing economy, business and first class values and making sure they are equal to the total passengers on the plane.
 This could be easily done in Pandas, by first subsetting on the columns to sum, then using the sum method with the axis argument set to 1 to indicate row wise summing. We then find instances where the total passengers column is equal to the sum of the classes. And find and filter out instances of inconsistent passenger amounts by subsetting on the equality we created with brack
Here's another example, birthdays and age values for a set of users. We can for example make sure that the age and birthday columns are correct by subtracting the number of years between today's date and each birthday. 
What to do when we spot inconsistencies with cross-field validation ?
Just like other data cleaning problems, there is no one size fits all solution, as often the best solution requires an in depth understanding of our dataset. We can decide to either drop inconsistent data, set it to missing and impute it, or apply some rules due to domain knowledge. All these routes and assumptions can be decided upon only when you have a good understanding of where your dataset comes from and the different sources feeding into it. 
Completeness and missing data. 
What is missing data?
Missing data is one of the most common and most important data cleaning problems. Essentially, It's when no data value is stored for a variable in an observation, mostly commonly represented as NA or NaN, but can take on arbitrary values like 0 or dot.
 Like a lot of the problems, it's commonly due to technical or human errors. 
Missing data can take many forms, so let's take a look at an example. 
7. Missingno
The missingno package allows to create useful visualizations of our missing data. 
 Missingness types
This leads us to missingness types. there are a variety of types of missing data. It could missing completely at random, missing at random, or missing not at random. 
•	Missing Completely at Random data: is when there's missing data completely due to randomness, and there is no systematic relationship between missing data and remaining values, such data entry errors. 
•	Missing at Random data: Despite a slightly deceiving name, It's when there is a systematic relationship between missing data and other observed values.
•	Missing not at Random: There is a systematic relationship between a column's missing values and unobserved values.
For example, when it's really hot outside, the thermometer might stop working, so we don't have temperature measurements for days with high temperatures. However, we have no way to tell this just from looking at the data since we can't actually see what the missing temperatures are. 
How to deal with missing data?
There's a variety of ways of dealing with missing data.
1-	dropping missing data.
2-	imputing them with statistical measures such as mean, median or mode, 
3-	imputing them with more complicated algorithmic approaches or ones that require some machine learning. Each missingness type requires a specific approach, and each type of approach has drawbacks and positives.
