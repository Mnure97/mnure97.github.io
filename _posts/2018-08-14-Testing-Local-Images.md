---
layout: post
title: Analysis of New York MTA Turnstile Data
---
![Image test]({{ site.url }}/images/MTA.logo)

Using the turnstile data to find the top twenty subway stations with most traffic to Maximize gala attendance and contribution.
For our first project in Metis, we worked with New York City MTA Turnstile data to figure out which stations had the greatest number of traffic and suitable dates for each station and locating tech companies near to subway stations 
In this project we used Python Pandas Dataframe was mainly used to clean and organize data. Various functions including Groupby, loc method was used to group data into comparable format. And used pickle to improve our time complexity, Matplotlib and Seaborn was used to visualize the data and create graphs.
I will go through the project steps starting with cleaning the dataset to the data analysis, and the conclusion.


•	**The Project Challenge:**

WomenTechWomenYes(WTWY) has an annual gala at the beginning of every summer with their goal to increase the participation of women in technology and to concurrently build awareness and reach.
For this goal, WTWY is trying to deploy street teams to the New York City subway stations.
The street teams will collect email addresses and those who sign up are sent free tickets to the gala.
WTWY wants us to analyze the MTA data set and give recommendations on which subway stations to deploy their street teams for maximum signatures.


•	**Data Cleaning:**
1.	Creating a unique identifier for turnstiles in each station.

2.	Filtering out dates that are not in our scope.

3.	Sorting the Dataset by dates.

4.	Dropping unnecessary column.

5.	Solving outlier using IQR.

we used the turnstile data in 2019 for the month of May, notice that Entries and Exit columns are cumulative measures and are measured every four hours. In order to calculate the number of people who went through a specific station we subtracted each rows of the cumulative entries and exits. We will then add the subtracted cumulative entries and exits to form a column for “total traffic”.


•	**Data Analysis:**

After cleaning the data and creating the “total traffic” column we were able to start analyzing the data. Below are some graphs that can be used to give recommendations to WomenTechWomenYes(WTWY) on where to deploy their street teams.

 ![Image analysis]({{ site.url }}/images/topst.png)
Above is a bar char graph of the top 20 stations with the greatest number of traffic for the month of May in 2019.
 ![Image analysis2]({{ site.url }}/images/topdays.png)
the results above show which days in the week has the highest record of traffic for the first station “34st-Penn STA Station “, in order for the WTWY to get the greatest number of subscribers and possible donations, it makes sense to target stations with the greatest number of traffic.
 

As the map above shows 4 of our top ten stations are also located in the big tech sectors of new York , which gives a higher chance of targeting people working in the tech industry.

•	**Conclusion:**

For WTWY’s(WomenTechWomenYes) annual gala, we would recommend deploying street teams on 34st-Penn STA Station, 14st-Union SQ, Grand Central-42st, 34st-Herald SQ, 23 ST, Time-Square 42st, 42 ST-Port auth, 86 ST, 125 ST, 96 ST, CANAL ST, and 59st Columbus on the weekdays.



•	**Further Steps:**

There are few things we want to implement to improve the project in the future:
1.	Automate the process of locating the nearest stations to tech companies.
2.	Explore a larger scope from our data
3.	Determine the exact hours of the day where station is crowded the most.



![Image test]({{ site.url }}/images/AlanLeeShireGandalf.JPG)

