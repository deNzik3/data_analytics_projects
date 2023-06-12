# Taxi Data Analytics | Data Analyst Project

## Table content
- [Introduction](#introduction)
- [Project organization](#project-organization)
- [Skills and technologies](#skills-and-technologies)


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

