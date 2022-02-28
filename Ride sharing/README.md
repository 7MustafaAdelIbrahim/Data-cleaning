Bicycle ride sharing dataset in ***San Francisco***.
It contains information on the start and end stations, the trip duration, and some user information for a bike sharing service.

## inspiration.
I have worked on this dataset to practice at data cleaning problems.

# Data cleaning probleams found in this dataset.

## 1- Datatype constrains.
We've to make sure that our columns are in correct datatype.
The data type of duration column is object, but it contains numerical data, which represents bicycle ride sharing duration time in minutes. So, we have to convert it into numeric to avoid misleading results when trying to extract some statistical summaries, as mathematical operations such as summing and multiplication lead to string concatenation, not numerical outputs. But first let's strip "minutes" from the column in order to make sure pandas reads it as numerical.

The user_type column contains information on whether a user is taking a free ride and takes on the following values.
1 - for free riders.
2 - for pay per ride.
3 - for monthly subscribers.
But the data type of user_type column is int64, we have to convert it to category, as the summary statistics are much more aligned with that of a categorical variable, discussing the number of observations, number of unique values, most frequent category instead of mean and standard deviation.

We have conveted user_birth_year to datatime instead of object type.
Luckily, Python has specific data type objects for various data types that you're probably familiar with by now. This makes it much easier to manipulate these various data types in Python.

'Unnamed: 0 column does not contain any useful or certain information, so we'll drop it due to memory space reasons.

## check for duplicates.
A new update to the data pipeline feeding into ride_sharing has added the ride_id column, which represents a unique identifier for each ride.
The update however coincided with radically shorter average ride duration times and irregular user birth dates set in the future. Most importantly, the number of rides taken has increased by 20% overnight, leading you to think there might be both complete and incomplete duplicates in the ride_sharing DataFrame.
Let's confirm this suspicion by finding those duplicates.

We've alot of samples that are completely duplicates (42 samples), and some samples are duplicated with small discrepancies across the columns.
For completely duplicates, simply we are goning to drop it.

##### user_gender.
Just 1.4% from our samples that have not been recorded truely, So we'll replace this with the most frequent which is male in this case.

![user_gender](https://user-images.githubusercontent.com/84151016/156053633-3b06be0b-93f6-48d9-9b8c-ba83fcf6d5e6.jpeg)


Each statiion_A_name has a different id, and since we have 9 places and 9 ids,then there is no problem with statiion_A_name.
Our dataset is already from San Francisco, So having San Francisico in each station A name does not add value or certain information. So, we'll drop it.

'Powell St BART Station (Market St at 4th St)'
and 'Powell St BART Station (Market St at 5th St)'
are two different stations with very small differencies in street number 4th and 5th.
So let's collabse them into one category or one station.
![station a id](https://user-images.githubusercontent.com/84151016/156053690-e56cb676-5d34-4710-a859-3bd734808434.jpeg)

![station A id 11](https://user-images.githubusercontent.com/84151016/156053715-cd6f6422-06ef-470b-af00-7d114d2ef271.jpeg)


### Exploratory data analysis.

What's the realtion between user gender and type ?

![user gender and type](https://user-images.githubusercontent.com/84151016/156053778-b9009f4d-073a-4bf8-a718-0e85f08b896f.jpeg)


