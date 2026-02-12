<h1 align="center">Exercise 1: Design a data warehouse</h1>  

<p align="center">
  <img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/hMJNLH6NFkVdh8Rqf-MDNg/imagePostGreSQL.png" alt="Table">
</p>

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

<h1 align="center">Exercise 2 - Create schema for data warehouse on PostgreSQL</h1>  

Start the PostgreSQL server from the SN Toolbox as shown in the image below.  

![PostgreSQL](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/xTYj5eYM4bLg7oV0HHGxBA/DWF1.png)  

Open the pgAdmin Graphical User Interface by clicking the pgAdmin launch button in the Cloud IDE interface.  

![pgAdmin_launch](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/fUYB2aGP-Xg8FIX8hA8Yrw/DWF2.png)  

Once the pgAdmin GUI opens, click on the Servers tab on the left side of the page. You will be prompted to enter a password.  

![password_request](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/BIWorkaroundFiles/week2/images/2.png)  

To retrieve your password, click on the PostgreSQL and go to Conection Information tab on the top of the interface.  

![connection_information](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/V46jb0XRCMzh6nnTGmsJFQ/DWF3.png)  

Scroll down to the session password and click on the Copy icon to the right of your password to copy onto your clipboard.  

![copy_password](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/EVui_ox9j9mK7dKeDKjtAQ/DWF4.png)  

Navigate back to the pgAdmin tab and paste in your password, then click OK.  

![password_paste](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/BIWorkaroundFiles/week2/images/2.2.png)  

You will then be able to access the pgAdmin GUI tool.

In the left tree-view, right-click on `Databases > Create > Database`.   

![create_database](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/BIWorkaroundFiles/week2/images/3.png)  

In the Database box, type `Project` as the name for your new database, and then click Save. 

![database_creation](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/BIWorkaroundFiles/week2/images/4.png)  

