# matplotlib-challenge

# Pymaceuticals Inc.


## Task

You've been given access to the complete data from their most recent animal study. In this study, 249 mice who were identified with squamous cell carcinoma tumors received treatment with a range of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals’ drug of interest, Capomulin, against the other treatment regimens.

The executive team has tasked you with generating all of the tables and figures needed for the technical report of the clinical study. They have also asked you for a top-level summary of the study results.

## Prepare the Data 

The datasets are merged into a single DataFrame. 

The number of mice are shown from the merged DataFrame. 

Each duplicate mice is found based on the Mouse ID and Timepoint. 

A clean DataFrame is created with the dropped duplicate mice. 

The number of mice are shown from the clean DataFrame. 

## Generate Summary Statistics 

The mean of the tumor volume for each regimen is calculated using groupby. 

The media of the tumor volume for each regimen is calculated using groupby. 

The variance of the tumor volume for each regimen is calculated using groupby. 

The standard deviation of the tumor volume for each regimen is calculated using groupby. 

The SEM of the tumor volume for each regimen is calculated using groupby. 

A new DataFrame is created with using the summary statistics. 

## Create Bar Charts and Pie Charts 

A bar plot showing the total number of timepoints for all mice tested for each drug regimen using Pandas is generated. 

A bar plot showing the total number of timepoints for all mice tested for each drug regimen using pyplot is generated. 

A pie plot showing the distribution of female versus male mice using Pandas is generated. 

A pie plot showing the distribution of female versus male mice using pyplot is generated. 

## Calculate Quartiles, Find Outliers, and Create a Box Plot 

A DatFrame that has the last timepoint for each mouse ID is created using groupby. 

The index of the DataFrame is reset. 

Retrieve the maximum timepoint for each mouse. 

The four treatment groups, Capomulin, Ramicane, Infubinol, and Ceftamin, are put in a list. 

An empty list is created to fill with tumor volume data. 

A for loop is used to display the interquartile range (IQR) and the outliers for each treatment group 

A box plot is generated that shows the distribution of the final tumor volume for all the mice in each treatment group. 

## Create a Line Plot and a Scatter Plot 

A line plot is generated that shows the tumor volume vs. time point for one mouse treated with Capomulin. 

A scatter plot is generated that shows average tumor volume vs. mouse weight for the Capomulin regimen. 

## Calculate Correlation and Regression 

The correlation coefficient and linear regression model are calculated for mouse weight and average tumor volume for the Capomulin regimen.

## Description

I started by importing the dependencies and setup the CSV files for merging. I merged the two files on the 'Mouse ID' as an outer join. I then previewed the initial DataFrame. To check for the number of mice in the study, I used the .nunique() as we specifically wanted to return the number. Using .loc and the .duplicated() function passing over the Mouse ID and timepoint columns, I was able to return the Mouse ID that is duplicated in the study. Using .loc and passing over the Mouse ID column again, this time specifying to look specifically for that Mouse ID to return all the data for that particular mouse. Using the .isin() function and setting a parameter of false, I was able to drop the the duplicates from the DataFrame and saved the result as a new DataFrame. I used .nunique() again to confirm the duplicate had been dropped. To get the tumor volume of each particular drug regimen and caculate the statistical summary requested, I grouped by the drug regimen column and calculated each statistical function. I then created a new DataFrame to display these results. To caculate the statistical summary using the aggregation method, I called on the drug regimen and tumor volume columns again grouping by the drug regimen then used the .agg() specifying the statistics requested. I got the the total counts of each drug used by using the .value_counts() function. I then plotted the results using the pandas method. I indexed the values of the drugs and got the values for each drug. Then plotted the results using the pyplot method. I got the counts of mice based on their gender. Then plotted to a pie chart using the pandas method. I also created another pie chart using the pyplot method. To calculate the final tumor volume of each mouse across four of the treatment regimens, I started by putting the treaments into a list. Then using the .isin() function, I created a new DataFrame using the drug regimen column and the drug list we had just created to isolate the drugs. To get the last timepoint for each mouse I grouped the newly created DataFrame by the Drug Regimen and Mouse ID columns. Using the .agg() over the tumor volume volume, using lambda x to take any number of arguments followed by iloc on the last column. I also had to reshape the dataframe as the data was not organized properly. I tried reindexing and I kept receiving an error. I found using the stack and unstack function I was able to fix this issue. I then created a blank variable to run my for loop in order to determine the IQR and if there may be any potential outliers. I used a for loop over f string print statements to diplay the values. I then ran a for loop in order to get the final tumor volumes into a blank list and drop any of the null columns. I then created a boxplot displaying the results. To generate the line plot of tumor volume versus time point for a single mouse treated with Capomulin, I started by using .loc on the drug regimen column specifiying the capomulin drug results. I took those results and used .loc again this time on the Mouse ID column looking specifically at Mouse "l509". I set my x axis as the timepoint and used the tumor volume to plot the line chart. To generate a scatter plot of mouse weight versus the average observed tumor volume for the entire Capomulin regimen, I first got the averages based on the Capomulin data I generated in the previous part of the analysis. I then created a scatter plot based on the weight and tumor volume columns. I caculated the correlation using scipy's stats pacakage based on the weight and tumor volume of the mice. I calculated the slope and line equation and created a new scatter plot with the information.

## References

Checking for duplicates in a pandas dataframe

https://stackoverflow.com/questions/50242968/check-for-duplicate-values-in-pandas-dataframe-column

Refrence on .isin() function to manipulate rows 

https://stackoverflow.com/questions/14057007/remove-rows-not-isinx

Reference on .agg() function

https://pbpython.com/groupby-agg.html

Reference on lambda function and using iloc

https://www.w3schools.com/python/python_lambda.asp

https://stackoverflow.com/questions/37512079/python-pandas-why-does-df-iloc-1-values-for-my-training-data-select-till#:~:text=If%20you%20say%20df.,means%20until%20the%20last%20column.

Reference on stack and unstack function

https://www.w3resource.com/pandas/dataframe/dataframe-stack.php

Reference on manipulation box plot outliers characteristics

https://stackoverflow.com/questions/65648502/how-to-change-outlier-point-symbol-in-python-matplotlib-pyplot
