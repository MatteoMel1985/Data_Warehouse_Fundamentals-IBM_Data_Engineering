<h1 align="center">Exercise 1: Design a data warehouse</h1>  

![Table](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/hMJNLH6NFkVdh8Rqf-MDNg/imagePostGreSQL.png)  

## Task 1: Design the dimension table MyDimDate  

To design the `MyDimDate` table, it is sufficient to inspect the attributes of [DimDate.csv](https://github.com/MatteoMel1985/Data_Warehouse_Fundamentals-IBM_Data_Engineering/blob/main/CSV/DimDate.csv).

Hence, it will appear as follows.

| Field Name | Details |
|---|---|
| DateID | Primary Key - Unique identifier for each date |
| Date | Full date from the date field of the original data |
| Year | Year derived from the date field of the original data. Example: 2020 |
| Quarter | Quarter number derived from the date field of the original data. Example: 1, 2, 3, 4 |
| QuarterName | Quarter name derived from the date field of the original data. Example: Q1, Q2, Q3, Q4 |
| Month | Month number derived from the date field of the original data. Example: 1, 2, 3 |
| MonthName | Month name derived from the date field of the original data. Example: January |
| Day | Day derived from the date field of the original data. Example: 23, 24 |
| Weekday | Weekday derived from the date field of the original data. Example: 1, 2, 3, 4, 5, 6, 7. 1 for Sunday, 7 for Saturday |
| WeekdayName | Weekday name derived from the date field of the original data. Example: Sunday, Monday |  

## Task 2: Design the dimension table MyDimWaste  

For MyDimWaste, we can simply add `WasteID` as a primary key, next to the attribute `WasteType`, which is shown in the original table of the exercise. 

| Field Name | Details |
|---|---|
| WasteID | Primary Key - Unique identifier for each waste type |
| WasteType | Type of waste. Example: Dry, Electronic, Plastic, Wet |

## Task 3: Design the dimension table MyDimZone  

For MyDimZone, we can do the same, or creating the primary key `ZoneID`, to match with the given attributes `CollectionZone ` and `City`.  

| Field Name | Details |
|---|---|
| ZoneID | Primary Key - Unique identifier for each collection zone |
| CollectionZone | Zone where waste is collected. Example: South, Central, West |
| City | City where the zone is located. Example: Sao Paulo, Rio de Janeiro |
