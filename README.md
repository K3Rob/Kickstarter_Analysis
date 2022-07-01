# Kickstarter_Analysis

## Purpose of this data ##

The purpose of this analysis was to explore the trends within Kickstarter’s data and find any patterns regarding the successfulness of campaigns for theater plays. The client has a proposal for a play that she wants to produce, and wants to know how best to get it funded, and the likelihood of it being funded. From this data I have created an analysis of when during the year the best times to start a campaign are and an analysis of what the success looks like for campaigns based on goal amount.

## Analysis ##

### Finding outcomes by Launch Date ###
One of the first things necessary was to convert the time stamp to standard date formats for human interpretation. We used the following formula created in a new column at the end of the original data set.
> =(((J2/60)/60)/24)+DATE(1970,1,1)
Following this the data set was filtered through a pivot table by the Parent Category of Theater for all years. We then compared the count of outcomes by the month and sorted the columns ascending. A line chart was made from this table and saved as an image file for future use.

### Outcomes Based on Goal ###
On a new work sheet a list of 12 goal ranges was created and compared by the number of successful, failed, and canceled projects. A countifs function was used that counted the number of plays within a range by outcome. Below are a couple samples of the function used.
> =COUNTIFS(Kickstarter!$R:$R,"Plays",Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F, "successful")
> =COUNTIFS(Kickstarter!$R:$R,"Plays",Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<5000", Kickstarter!$F:$F, "successful")
The count of plays in each range, regardless of outcome, was then totalled in a 3rd column and used to calculate the percentage of each outcome per range. These percentages were then charted on a line graph to create better visualization of the data and then saved as an image file for future use. 

## Challenges ##

### Use of Formulas and Defining Variables ###
Some of the possible challenges in creating this is making sure to have all the parameters in the countifs functions. Omission of any one parameter will cause issues with the data set and can lead to discrepancies. Likewise, the basic parameters of a large table based on a function like countifs need to all be relatively close to the same with only one or two variables in the function changing or the whole table may be corrupted with data that can’t be interpreted correctly.

### Correlations Within the Data ###
There are some area's to explore within the data that may give better explanitory data. For example an exploration into the correlation between the goal amounts and the time of year, or even the length of campaign in relation to outcomes may be in order. This analysis is a general overview at a glance and does not cover deaper implications of the data set. 

## Results ##
Based on the Table *Theater Outcomes by Launch* the best time to start your campaign is in either May or June and the worst month is December.
From *Outcomes Basted on Goals* the campaigns most likely to succeed had goals under 5000 USD.
This data is likely skewed and may have some significant outliers that need addressed.
Some further analysis ideas inclued success based on length of campaign, and goal amounts based on the time of year.
