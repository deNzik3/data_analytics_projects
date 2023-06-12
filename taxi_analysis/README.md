# Taxi Data Analytics | Data Analyst Project

## Table content
- [Introduction](#introduction)
- [Project organization](#project-organization)
- [Skills and technologies](#skills-and-technologies)
- [Final report](#final-report)
- [Taxi Explorary Data Analysis](#taxi-explorary-data-analysis)
- [Taxi database model](#taxi-database-model)
- [Big query analysis](#big-query-analysis)
- [Machine Learning model](#machine-learning-model)

## Introduction
[taxi](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page) <- link to the information web page

I will analyze the data, build a database model, and make a conclusion based on the data obtained. I will also create a visual dashboard in Power BI. I will go through all the stages of data analysis.

The New York City Taxi and Limousine Commission (TLC), created in 1971, is the agency responsible for licensing and regulating New York City's Medallion (Yellow) taxi cabs, for-hire vehicles (community-based liveries, black cars and luxury limousines), commuter vans, and paratransit vehicles. The Commission's Board consists of nine members, eight of whom are unsalaried Commissioners. The salaried Chair/ Commissioner presides over regularly scheduled public commission meetings and is the head of the agency, which maintains a staff of approximately 600 TLC employees.


Yellow and green taxi trip records include fields capturing pick-up and drop-off dates/times, pick-up and drop-off locations, trip distances, itemized fares, rate types, payment types, and driver-reported passenger counts. The data used in the attached datasets were collected and provided to the NYC Taxi and Limousine Commission (TLC) by technology providers authorized under the Taxicab & Livery Passenger Enhancement Programs (TPEP/LPEP). The trip data was not created by the TLC, and TLC makes no representations as to the accuracy of these data.



## Project organization
```
├── data                                : Folder with the datasets I used
      └── README.md
      └── taxi+_zone_lookup.csv
├── LICENSE                             : MIT License        
├── BigQuery_analysis_PySparkSQL.ipynb  : Data Analysis using PySparkSQL
├── ML_building_taxi.ipynb              : The way to create an ML model
├── README.md                           : Project description
├── data_documentation.pdf              : Documentation for the dataset
├── final_report.jpg                    : Final report about project
├── linear_regression_model.pkl         : Linear Regression model
├── taxi_model.png                      : ERD data model diagram
├── taxi_EDA.ipynb                      : Quick Data Analysis to understand the dataset
├── taxi_database_building.ipynb        : Building a model and dividing a dataset into tables
└── taxi_model.png                      : ERD data model diagram
```


## Skills and technologies
* Python
* SQL
* PySparkSQL
* Data Analysis
* Data Model Building
* Data Engineering
* BigQuery
* Building a Machine Learning model


## Final report 


This report shows the main indicators of taxi operation. We can also draw basic conclusions about the relationship between some variables. For example, we see the dependence of the average check on the type of payment and by month. We also see that it is the payment by bank card that is most popular, which is quite logical. 

<img align="left" width="1200" height="600" src="https://github.com/densivanov/data_analytics_projects/blob/main/taxi_analysis/final_report.jpg">




## Taxi Explorary Data Analysis


Conducting this analysis, my main goal was to understand the data with which I will work. I also wanted, for greater clarity, to visualize all this and find outliers, understand why they exist, and also build a foundation for a future ML model.

**First of all, I want to draw your attention to the schedule of the number of passengers over the entire time interval that we have.**

![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/1dd879bd-4a8e-4a98-806b-5d8f659e8248)

Conclusions from the graph above:
* We have a small drawdown in terms of quantity
* We have no negative outliers
* We have one value that is not like the others, where the number of passengers is > 35
* Overall, this is an uptrend

**The next important graph is the graph of the dependence of the number of landings and the time of day**
![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/cae6a85d-6375-48e8-8ed2-4931309199ef)

From above graph, we can say that:
* The least number of passengers in the interval from morning at 4-5 o'clock
* The peak of the schedule falls at 18 o'clock, when everyone goes from work
* Then, after the peak, the chart does not hold, but gradually goes down

**Schedule with the place and the biggest tips**
![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/a9804663-b1b7-4705-be15-26e25f815c34)

On this chart, we can see the zones where the biggest tips were


**You can read more about the analysis [here](https://github.com/densivanov/data_analytics_projects/blob/main/taxi_analysis/taxi_EDA.ipynb)**


## Taxi database model

This part of my analysis is aimed at building a separate database for taxis, in this topic there will be concepts such as primary key, foreign key, as well as everything related to databases



I would like to draw attention to a function that facilitates the initial analysis of the data. It is shown in the picture


![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/69011dc6-8dd1-4b4f-858c-e86cde6c9c83)

It greatly facilitates the initial data analysis, helps to identify outliers and missing data, and the documentation is also shown in the picture


Now we will present the splitting of a large table into subtables for the correct design of the database. In the end, we will get such an ERD diagram



![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/c5d132ee-5d2e-4f0d-a3f2-e670c8ba4f95)


## Big query analysis

Since we are working with a large set of data that is presented as a file.parquet we will use PySparkSQL for large data analysis, with the help of which we will draw conclusions and get the information we are interested in


First we will get our data and upload it to the server



![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/129afc2f-46ce-4c6c-97c1-94c99892cf2f)


Having created an image of our table through PySparkSQL, we can now write SQL queries. Let's get down to the analysis

The first thing I would like to know is the basic information on the distance of a taxi ride

![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/4195ac98-f3a0-4069-8fcc-6d4e6f7b3235)


Conclusions:
* The average trip is 3.4 miles
* The maximum trip is 62 thousand miles, which is probably an outlier and not real information



I think it would be quite interesting for us to know the average duration of the trip in minutes during the day. As we can see, the biggest average is to continue at 14-16 o'clock in the afternoon



![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/5909e690-beb3-4233-8425-c112c11e9617)



The graph  shows the average number of passengers and the maximum number of passengers by time

![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/82fbfc2d-1755-47a7-8e7b-2c3e1ee750b2)


The full version of the analysis can be found [here](https://github.com/densivanov/data_analytics_projects/blob/main/taxi_analysis/BigQuery_analysis_PySparkSQL.ipynb)



## Machine Learning model




Conducting the initial analysis, I found logical dependencies with ML, we can build a simple model that will predict the final price



![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/fad9fa2f-598f-47e4-ba0e-36bd00c3ecbe)




As we can see, we have a linear dependence, which allows us to use a linear regression model, let's do it



First I'll import the ML libraries and split our dataset into X and target(y)



![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/ca293cc1-1318-4bd2-9a8d-0eecc9bc67ce)



Then we will train the model on our data



![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/7d9bef8c-20aa-4ca7-9233-f02243655ead)



And in the end, we will evaluate the performance of our model using indicators



![image](https://github.com/densivanov/data_analytics_projects/assets/94192418/d0d57590-586e-4e11-8faa-84eb4add240d)

