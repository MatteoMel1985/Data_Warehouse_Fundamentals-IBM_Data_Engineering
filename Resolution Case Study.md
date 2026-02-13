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

## Task 5: Create the dimension table MyDimDate  

Start the PostgreSQL server from the SN Toolbox as shown in the image below.  

<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/xTYj5eYM4bLg7oV0HHGxBA/DWF1.png" width="60%">

Open the pgAdmin Graphical User Interface by clicking the pgAdmin launch button in the Cloud IDE interface.  

<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/fUYB2aGP-Xg8FIX8hA8Yrw/DWF2.png" width="60%">

Once the pgAdmin GUI opens, click on the Servers tab on the left side of the page. You will be prompted to enter a password.  

![password_request](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/BIWorkaroundFiles/week2/images/2.png)  

To retrieve your password, click on the PostgreSQL and go to Conection Information tab on the top of the interface.  

<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/V46jb0XRCMzh6nnTGmsJFQ/DWF3.png" width="60%">

Scroll down to the session password and click on the Copy icon to the right of your password to copy onto your clipboard.  

<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/EVui_ox9j9mK7dKeDKjtAQ/DWF4.png" width="60%">

Navigate back to the pgAdmin tab and paste in your password, then click OK.  

<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/BIWorkaroundFiles/week2/images/2.2.png" width="100%">

You will then be able to access the pgAdmin GUI tool.

In the left tree-view, right-click on `Databases > Create > Database`.   

<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/BIWorkaroundFiles/week2/images/3.png" width="100%">

In the Database box, type `Project` as the name for your new database, and then click Save. 

<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/BIWorkaroundFiles/week2/images/3.png" width="100%">

Click on the Query Tool icon on top of the left pane. 

Once in it, write and run the following SQL script.  

```sql
CREATE TABLE "MyDimDate" (
    DateID INTEGER NOT NULL PRIMARY KEY,
    Date DATE NOT NULL,
    Year SMALLINT NOT NULL,
    Quarter SMALLINT NOT NULL CHECK (Quarter BETWEEN 1 AND 4),
    QuarterName VARCHAR(2) NOT NULL,
    Month SMALLINT NOT NULL CHECK (Month BETWEEN 1 AND 12),
    MonthName VARCHAR(9) NOT NULL,
    Day SMALLINT NOT NULL CHECK (Day BETWEEN 1 AND 31),
    Weekday SMALLINT NOT NULL CHECK (Weekday BETWEEN 1 AND 7),
    WeekdayName VARCHAR(9) NOT NULL
);
```

![MyDimDate](https://github.com/MatteoMel1985/Relational-Dataset-Images/blob/main/Data%20Warehouse/02.05-MyDimDate.png?raw=true)  

Take a screenshot of the SQL statement you used to create the table MyDimDate.

Name the screenshot `5-MyDimDate.png`.  

![5-MyDimDate.pn](https://github.com/MatteoMel1985/Data_Warehouse_Fundamentals-IBM_Data_Engineering/blob/main/Tasks/5-MyDimDate.PNG?raw=true)  

## Task 6: Create the dimension table MyDimWaste  

Highlight all the text and delete it, and now run the following SQL string.

```sql
CREATE TABLE "MyDimWaste" (
    WasteID INTEGER NOT NULL PRIMARY KEY,
    WasteType VARCHAR(50) NOT NULL
);
```

![MyDimWaste](https://github.com/MatteoMel1985/Relational-Dataset-Images/blob/main/Data%20Warehouse/02.06-MyDimWaste.png?raw=true)  

Take a screenshot of the SQL statement and save it as `6-MyDimWaste.png`  

![6-MyDimWaste.pn](https://github.com/MatteoMel1985/Data_Warehouse_Fundamentals-IBM_Data_Engineering/blob/main/Tasks/6-MyDimWaste.PNG?raw=true)  

## Task 7: Create the dimension table MyDimZone    

Highlight all the text and delete it, and now run the following SQL string.  

```SQL
CREATE TABLE "MyDimZone" (
    ZoneID INTEGER NOT NULL PRIMARY KEY,
    CollectionZone VARCHAR(50) NOT NULL,
    City VARCHAR(50) NOT NULL
);
```

![MyDimZone](https://github.com/MatteoMel1985/Relational-Dataset-Images/blob/main/Data%20Warehouse/02.07-MyDimZone.png?raw=true)  

Take a screenshot of the SQL statement and save it as `7-MyDimZone.png`  

![7-MyDimZone.png](https://github.com/MatteoMel1985/Data_Warehouse_Fundamentals-IBM_Data_Engineering/blob/main/Tasks/7-MyDimZone.PNG?raw=true)  

## Task 8: Create the fact table MyFactTrips  

Highlight all the text and delete it, and now run the following SQL string.  

```SQL
CREATE TABLE "MyFactTrips" (
    TripID SERIAL PRIMARY KEY,
    DateID INTEGER NOT NULL,
    WasteID INTEGER NOT NULL,
    ZoneID INTEGER NOT NULL,
    WasteCollectedTons DECIMAL(10, 2) NOT NULL,
    FOREIGN KEY (DateID) REFERENCES "MyDimDate" (DateID),
    FOREIGN KEY (WasteID) REFERENCES "MyDimWaste" (WasteID),
    FOREIGN KEY (ZoneID) REFERENCES "MyDimZone" (ZoneID)
);
```

![MyFactTrips](https://github.com/MatteoMel1985/Relational-Dataset-Images/blob/main/Data%20Warehouse/02.08-MyFactTrips.png?raw=true)  

Take a screenshot of the SQL statement and save it as `8-MyFactTrips.png`  

![8-MyFactTrips.png](https://github.com/MatteoMel1985/Data_Warehouse_Fundamentals-IBM_Data_Engineering/blob/main/Tasks/8-MyFactTrips.PNG?raw=true)  

<h1 align="center">Exercise 3: Load data into the data warehouse</h1>  

