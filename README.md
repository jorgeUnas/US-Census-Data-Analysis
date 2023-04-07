# US Census Data Analysis

### Project Overview 
This project includes data from all counties' US census in 2015, available in Kaggle. Tableau Public was used to get some interactive visualizations in order to answer 3 main questions:
1. In which states do people have the best transportation?
2. How does poverty look in the US and what is the correlation between unemployment and poverty for each state? 
3. Which states have the highest income per capita in the US?

This is the link to the Dashboards in Tableau Public: https://public.tableau.com/app/profile/jorge.humberto.unas.daza/viz/USCensusDemographicData_16760729843730/USCensusAnalysis 

### 1. Where is the best transport?
**Summary:**

This is an interactive dashboard containing a box plot and a dot plot. The box plot displays the interquartile range, the median values and the outliers of the average commute time for the counties in every state. There is a filter to show the top-N states in both charts. By default, this filter is set to show the 5-top states in terms of less commute time. According to this plot the state with the more efficient transportation is Alaska with a median commute time of 8.8 min. The box plot is useful to analyze the counties with transportation issues in this top-N states. For example, the county Matanuska-Susitna Borough (median commute time of 34.0 min) is an outlier for Alaska and this is related to the increase of traffic due to population increase in recent years (for further information consult the first link in resources).
 On the other hand, the dot plot shows the average percentage of people that use any of the transport means included in the dataset (public transport, carpool, drive and other transport). The box plot acts like a filter for the dot plot to select which state(s) visualize so by default this plot also shows the top-5 states. It looks like the pattern of the dots for the states is very similar, except for Alaska where the average percentage of people using carpool and other transport means (possibly bikes) is higher and this can influence positively the transport efficiency by reducing traffic. 
 
 <img src="https://github.com/jorgeUnas/US_Census_Data_Analysis/blob/main/Where%20is%20the%20best%20transport.png" alt="Where is the best transport?"> 
 
 **Design:**

I decided to use a box plot instead of a bar chart because I was interested in analyzing the presence of outliers and offer a better representation of the central tendency using the median instead of the mean. The presence of outliers was expected in this dataset because in some counties can be different traffic issues, different road conditions, the people can use alternative transport means and so on. It was also used a dot plot to compare the quantity of users of different transport means. This kind of plot shows more than one metric per category (in this case each state) which made it more suitable for this analysis than a bar chart. Moreover, every different metric is associated with a different dot color using a color-blind pattern and a color blindness Simulator to check the suitability of the colors (see the 2nd link below).  

**Resources:**

https://matsugov.us/outreach/transportationroads
https://www.color-blindness.com/coblis-color-blindness-simulator/
https://www.usnews.com/news/best-states/slideshows/10-states-with-the-best-transportation 


### 2. How does poverty look in the US?
**Summary:**

This is an interactive dashboard containing a map and one scatter plot. There is a filter beside the map to select the top-N states in terms of the most poverty rates. By default, this filter is set to show the top-5 states or in other words the 5 poorest states in US. According to this map the poorest state is Puerto Rico and in general the top-5 states are located in the south-east area of the US. There is also a tooltip for each state showing the non-white ethnicity breakdown. From these tooltips, it is observable that the proportion of black people in the 5 poorest states is higher than the other non-white ethnicities (Hispanics, Asians, Native Americans, Native Alaskans, Native Hawaiians and pacific Islanders) except to Puerto Rico where the population is predominantly Hispanic.  
On the other hand, it exists a significative positive correlation (See the scatter plot) between unemployment rate and poverty rate for the 5 poorest countries (R<sup>2</sup> = 0.98) which does not suggest that one of these factors causes the other.

<img src="https://github.com/jorgeUnas/US_Census_Data_Analysis/blob/main/How%20does%20poverty%20look%20in%20US.png" alt="How does poverty look in US?"> 

**Design:**

The top-n poorest states were displayed in a map with the intention of stablish a cluster analysis. For example, it can be said that the 5 poorest states are grouped in the south-east area of US or the 17 poorest states are in the south-east and south-west areas (check using the filter). A divergent color pattern was used to show the poverty rate in every state and a color vision deficiency (CVD) Simulator was used to facilitate the visualization of this metric for color-blindness people (see the 2nd link in resources).
Pie charts were appended in the tooltips to show the percentage of each non-white populations in every state (taking the sum of those populations as the total). White populations were excluded from this plot because this is one of the ethnic groups with the less poverty rate nationwide (See the first link in resources). Calculated fields were created to get the number of people from every ethnicity group (e.g. [Black]*[Total Pop]/100 for the amount of black people in every county). The colors in the pie charts were selected using the color-blind pattern in-built in tableau.
Zero labels for the axes were excluded in the scatter plot to better visualize the tendency among the points and optimize the space inside this plot. 

**Resources:**

•	https://www.statista.com/statistics/200476/us-poverty-rate-by-ethnic-group/
•	https://www.color-blindness.com/coblis-color-blindness-simulator/ 

### 3. Where are the best salaries?
**Summary:**

•	This is an interactive dashboard containing a bubble plot and a treemap plot. There is a filter beside the bubble plot to select the range of mean income per capita and visualize the states included in this range. By default, this filter is set from $33.8K to $47.7K and shows the top-5 states by mean income per capita. A divergent orange scale indicates that District of Columbia was the state with the highest income per capita in 2015 ($47.7K) followed by Connecticut ($37.0K). 
Looking at the treemap it can be stated that the people working in professional positions are the most in US. Although, this plot shows the proportion (by the square sizes) and the amount of people working in every job sector in USA by default, it is also possible to see the same information for a specific state or group of states by using the bubble chart as a filter. For example, by selecting District of Columbia it can be noticed that this state has greater proportion of employees in professional positions compared to other job sectors.


<img src="https://github.com/jorgeUnas/US_Census_Data_Analysis/blob/main/Tops%20states%20by%20income%20per%20capita.png" alt="Where are the best salaries?"> 

**Design:**

A bubble plot was useful to visually compare the mean income per capita. A divergent color scale was used to give a quick idea of this metric in every state and not saturate the visualization with numbers. In this case the filter acts just over the bubble plot and the interactivity of the treemap depends on the state(s) selected in the bubble plot. 
The treemap plots is an appealing alternative to the pie charts because the rectangles are easier to interpretate than the angles and there is more space in rectangles to organize the labels, including more information and defining the color-coding without saturating the visualization. The numerical values used to design the treemap were the number of people in every job sector so new calculated field were created (e.g. [Professional]*[Total Pop]/100 for the number of professionals) and aggregated using SUM(). 

**Resources:**

https://en.wikipedia.org/wiki/List_of_U.S._states_by_adjusted_per_capita_personal_income 
https://medium.com/nerd-for-tech/how-treemaps-are-better-than-pie-chart-5f8709057fbc#:~:text=What%20is%20a%20Treemap%3F,of%20the%20measure%20they%20represent. 

