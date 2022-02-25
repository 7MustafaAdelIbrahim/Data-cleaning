Dealing with missingness.


# ***Context.***
This dataset is originally from the National Institute of Diabetes and Digestive and Kidney Diseases. The objective of the dataset is to diagnostically predict whether or not a patient has diabetes, based on certain diagnostic measurements included in the dataset. Several constraints were placed on the selection of these instances from a larger database. In particular, all patients here are females at least 21 years old of Pima Indian heritage.
The datasets consists of several medical predictor variables and one target variable, Outcome. Predictor variables includes the number of pregnancies the patient has had, their BMI, insulin level, age, and so on.

# ***Acknowledgements.***
Smith, J.W., Everhart, J.E., Dickson, W.C., Knowler, W.C., & Johannes, R.S. (1988). Using the ADAP learning algorithm to forecast the onset of diabetes mellitus. In Proceedings of the Symposium on Computer Applications and Medical Care (pp. 261--265). IEEE Computer Society Press.

# ***Inspiration.***
I have worked on pima-indians-diabetes to practice on data cleaning problems specially dealing with missingness:
    Getting the reason for being missed.
    Understanding the pattern of missingness.
    Chosse the best imputation technique.
    
# Data cleaning.
    A summary of problems we have found in our dataset.

We've 768 entries, one row for each sample that is prone to be diabetic. We have alot of missingness

![class](https://user-images.githubusercontent.com/84151016/155798497-347f3553-0404-4aca-9e9b-a8407bd482a0.jpeg)

The largest proportion of samples are not diabetic.

![the distribution of missingness](https://user-images.githubusercontent.com/84151016/155798584-0bbd6bc1-2da7-4cf9-8f7b-77f58242a3b2.jpeg)

Intersting, we can observe that missingness in SkinThickness is Missing Not at Random. Let's dig deeper and find out more about missingness.

![the correlation of](https://user-images.githubusercontent.com/84151016/155798682-ad046c8f-c1ad-4447-9cfe-edb5cf37d1b3.jpeg)

Nullity correlation ranges from -1 to 1, where -1 means if one variable appears the other definitely does not, 0 means if variables appearing or not appearing have no effect on one another, 1 means if one variable appears the other definitely also does. As we can see there's a strong relation between missingnes in Skin_fold and serum_Insulin.

![full correlation](https://user-images.githubusercontent.com/84151016/155798743-37c380f0-084e-4293-9488-ab9703c3ca6b.jpeg)

To interpret this graph, read it from a top-to-down perspective. Cluster leaves which are linked together at a distance of zero. Skin Fold' and 'Serum Insulin' are highly correlated which is also clear from the heatmap graph, and can be mentioned as Missing Not at Random. The missingness of 'Glucose' appears to be similar to 'BMI' than to 'Diastolic_BP'. However, checking its matrix plot and the number of values only confirms the fact of their correlation is high only because both 'BMI' and 'Glucose' in specific have very few missing values. Hence, 'Glucose' can as well be considered as Missing Completely at Random.

![skin and insulin](https://user-images.githubusercontent.com/84151016/155798783-dbba1e0d-d45b-45d2-9ef9-5c48501c6237.jpeg)

The scatterplot of Serum_Insulin and skin illustrated above shows the non-missing values in purple and the missing values in red. The red points along the y-axis are the missing values of 'Serum_Insulin' plotted against their 'skin' values. Likewise, the points along the x-axis are the missing values of 'skin' against their 'Insulin' values. The bottom-left corner represents the missing values of both 'skin' and 'Serum_Insulin'.

# *** Imputing missingness.***

The KNN imputation technique uses the K-Nearest Neighbor algorithm for predicting the missing values, finding the most similar data points using all the non-missing features for a data point and calculates the average of these similar points to fill the missing feature. Here, K specifies the number of similar or nearest points to consider.

The MICE imputation is a very robust and complex model for imputing missing values. It imputes using multiple regressions over the data and takes the average value for filling in the missing feature for a data point.

A good way to analyze the performance of different imputations is to observe their density plots and see which one most resembles the shape of the original data.

![kde](https://user-images.githubusercontent.com/84151016/155798903-6b7d1075-58ff-4960-a236-c81aa7541e25.jpeg)

The KNN and MICE imputations are much more identical to the base DataFrame with the peak of MICE imputation being slightly shifted! So, better to use KNN imputation.



