## ***Airlines in San Francisco Airport.***
    Keeping it descriptive

To further understand travelers' experiences in the San Francisco Airport, the quality assurance department sent out a qualitative questionnaire to all travelers 
who gave the airport the worst score on all possible categories. 
The objective behind this questionnaire is to identify common patterns in what travelers are saying about the airport.
Their response is stored in the survey_response column. Upon a closer look, you realized a few of the answers gave the shortest possible character amount without much substance.

## ***Data cleaning.***
    We've 2477 entries, One row per each fight. and we have no missingness.

- While collecting survey respondent metadata in the airlines DataFrame, the full name of respondents was saved in the full_name column. However upon closer inspection, 
we found that a lot of the different names are prefixed by honorifics such as "Dr.", "Mr.", "Ms." and "Miss".
we created two new columns named first_name and last_name, containing the first and last names of respondents respectively.
Before doing so however, you need to remove honorifics.

- "Unnamed: 0" and "id" columns does not contain usefulm or even certain information. So, we'll drop those columns for memory space reasons.
we got the unique values of 'cleanliness', 'safety', 'satisfaction', 'dest_region', 'dest_size' columns. 
And we found:  
    1- The dest_region column has inconsistent values due to capitalization and has one value that needs to be remapped.
    2- The dest_size column has only inconsistent values due to leading and trailing spaces.

- By looking at boarding_area column, we found that there is "Gates" strip and it is object datetype although it contains numbers.
So, we removed "Gates" strip from boarding_area column.

- The airlines DataFrame contains the day and wait_min columns, which are categorical and numerical respectively. The day column contains the exact day a flight took place, and wait_min contains the amount of minutes it took travelers to wait at the gate.
To make your analysis easier, we'll create two new categorical variables:
wait_type:
    'short' for 0-60 min, 'medium' for 60-180 and long for 180+.
day_week:
    'weekday' if day is in the weekday, 'weekend' if day is in the weekend.

- we extracted the year from dept_time column and crerate new feature, but we fouund out that all flights in our dataset occurred in 2018. So, the year column that we have just created does not cotain any useful information. So, droped it again. And Just tow days have been recorded. we droped "dept_time" column too.

## ***Exploratory data analysis.***
These types of feedbacks are essential to improving any service.
Coupled with some wordcount analysis, you can find common patterns across all survey responses in no time!

We tried to answer som questions, Like:
- Are waiting-type rates affected by the day of travel ?
- Are satisfaction rates affected by waiting time ?
- What is the relation between cleanliness and satisfication ?
- ....... and more.

![table](https://user-images.githubusercontent.com/84151016/155775458-35c34f5d-1aa8-4339-8210-dd66e5b248e8.jpeg)



We noted that the satisfaction rates of passengers distinguish and vary according to the degree of cleanliness, as the dissatisfaction increased completely with the passengers who registered completely unclean, and vice versa.
<br> Not: not exist means we don't have samples recorded with these values.

![cleanliness and satistfiction](https://user-images.githubusercontent.com/84151016/155775494-681bcf55-8964-422f-8e6e-d04efc7bf7f5.jpeg)

