# US Census Data Analysis

### Project Overview 
This project includes data from all counties' US census in 2015, available in Kaggle. Tableau Public was used to get some interactive visualizations in order to answer 3 main questions:
1. In which states do people have the best transportation?
2. How does poverty look in the US and what is the correlation between unemployment and poverty for each state? 
3. Which states have the highest income per capita in the US?

This is the link to the Dashboards in Tableau Public: https://public.tableau.com/app/profile/jorge.humberto.unas.daza/viz/USCensusDemographicData_16760729843730/USCensusAnalysis 

### 1. Where is the best transport?
- Summary: 
This is an interactive dashboard containing a box plot and a dot plot. The box plot displays the interquartile range, the median values and the outliers of the average commute time for the counties in every state. There is a filter to show the top-N states in both charts. By default, this filter is set to show the 5-top states in terms of less commute time. According to this plot the state with the more efficient transportation is Alaska with a median commute time of 8.8 min. The box plot is useful to analyze the counties with transportation issues in this top-N states. For example, the county Matanuska-Susitna Borough (median commute time of 34.0 min) is an outlier for Alaska and this is related to the increase of traffic due to population increase in recent years (for further information consult the first link in resources).
 On the other hand, the dot plot shows the average percentage of people that use any of the transport means included in the dataset (public transport, carpool, drive and other transport). The box plot acts like a filter for the dot plot to select which state(s) visualize so by default this plot also shows the top-5 states. It looks like the pattern of the dots for the states is very similar, except for Alaska where the average percentage of people using carpool and other transport means (possibly bikes) is higher and this can influence positively the transport efficiency by reducing traffic. 
 - Design:
I decided to use a box plot instead of a bar chart because I was interested in analyzing the presence of outliers and offer a better representation of the central tendency using the median instead of the mean. The presence of outliers was expected in this dataset because in some counties can be different traffic issues, different road conditions, the people can use alternative transport means and so on. It was also used a dot plot to compare the quantity of users of different transport means. This kind of plot shows more than one metric per category (in this case each state) which made it more suitable for this analysis than a bar chart. Moreover, every different metric is associated with a different dot color using a color-blind pattern and a color blindness Simulator to check the suitability of the colors (see the 2nd link below).  
•	Resources:
https://matsugov.us/outreach/transportationroads
https://www.color-blindness.com/coblis-color-blindness-simulator/
https://www.usnews.com/news/best-states/slideshows/10-states-with-the-best-transportation 


### 2. How does poverty look in the US?
### 3. Where are the best salaries?
