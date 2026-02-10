![Skills_Network](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-PY0221EN-Coursera/images/image.png)  

<h1 align="center">Final Assignment: Data Warehouse Fundamentals</h1>

# ***Project Scenario***  

You are a data engineer hired by a solid waste management company. It collects and recycles solid waste across major cities in the country of Brazil. They operate hundreds of trucks of different types to collect and transport solid waste. The company would like to create a data warehouse so that it can create reports like:

* Total waste collected per year per city  
* Total waste collected per month per city  
* Total waste collected per quarter per city  
* Total waste collected per year per trucktype  
* Total waste collected per trucktype per city  
* Total waste collected per trucktype per station per city

You will use your data warehousing skills to design and implement a data warehouse for the company.  

<h1 align="center">Exercise 1: Design a data warehouse</h1>  

The solid waste management company has provided you the sample data they want to collect.  

![Table](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/hMJNLH6NFkVdh8Rqf-MDNg/imagePostGreSQL.png)  

You will start your project by designing a Star Schema warehouse by identifying the columns for the various dimensions and fact tables in the schema.  

## Task 1: Design the dimension table MyDimDate  

Write down the fields in the MyDimDate table in any text editor, one field per line. The company is looking at a granularity of day, which means they would like to have the ability to generate the report on a yearly, monthly, daily, and weekday basis.

Here is a partial list of fields to serve as an example:

* dateid

* month

* monthname

* …

* …

Take a screenshot of the fieldnames for the table MyDimDate.

Name the screenshot `1-MyDimDate.png` (Images can be saved with either the .jpg or .png extension).  

## Task 2: Design the dimension table MyDimWaste  

Write down the fields in the MyDimWaste table in any text editor, one field per line.

Take a screenshot of the fieldnames for the table MyDimWaste.

Name the screenshot `2-MyDimWaste.png`.  

## Task 3: Design the dimension table MyDimZone  

Write down the fields in the MyDimZone table in any text editor, one field per line.

Take a screenshot of the fieldnames for the table MyDimZone.

Name the screenshot `3-MyDimZone.png`.  

<h1 align="center">Exercise 2 - Create schema for data warehouse on PostgreSQL</h1>  

In this exercise, you will create the tables you have designed in the previous exercise. Open pgAdmin and create a database named **Project**, then create the following tables.  

## Task 5: Create the dimension table MyDimDate  

Create the MyDimDate table.

Take a screenshot of the SQL statement you used to create the table MyDimDate.

Name the screenshot `5-MyDimDate.png`.  

## Task 6: Create the dimension table MyDimWaste  

Create the MyDimWaste table.

Take a screenshot of the SQL statement you used to create the table MyDimWaste.

Name the screenshot `6-MyDimWaste.png`. 

## Task 7: Create the dimension table MyDimZone  

Create the MyDimZone table.

Take a screenshot of the SQL statement you used to create the table MyDimZone.

Name the screenshot `7-MyDimZone.png`.  

## Task 8: Create the fact table MyFactTrips  

Create the MyFactTrips table.

Take a screenshot of the SQL statement you used to create the table MyFactTrips.

Name the screenshot `8-MyFactTrips.png`. 

<h1 align="center">Exercise 3: Load data into the data warehouse</h1>  

In this exercise, you will load the data into the tables.

**After the initial schema design, you were told that due to operational issues, data could not be collected in the format initially planned. This implies that the previous tables (MyDimDate, MyDimWaste, MyDimZone, MyFactTrips) in the Project database and their associated attributes are no longer applicable to the current design. The company has now provided data in CSV files with new tables DimTruck and DimStation as per the new design.**  

You will need to load the data provided by the company in CSV format. First, create a new database named FinalProject. Then, create the tables DimDate, DimTruck, DimStation, and FactTrips by defining the structure of the columns as per the CSV files. Next, load the data from the CSV files into the appropriate tables.  

>*Note: Ensure that you upload the files to this path: /var/lib/pgadmin/*

## Task 9: Load data into the dimension table DimDate  

Download the data from [https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/Final%20Assignment/DimDate.csv](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/Final%20Assignment/DimDate.csv)  

Load this data into DimDate table.

Take a screenshot of the first 5 rows in the table DimDate.

Name the screenshot `9-DimDate.png`.  

## Task 10: Load data into the dimension table DimTruck  

Download the data from [https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/Final%20Assignment/DimTruck.csv]([)](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/Final%20Assignment/DimTruck.csv)  

Load this data into DimTruck table.

Take a screenshot of the first 5 rows in the table DimTruck.

Name the screenshot `10-DimTruck.png`.  

## Task 11: Load data into the dimension table DimStation  

Download the data from [https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/Final%20Assignment/DimStation.csv](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/Final%20Assignment/DimStation.csv)  

Load this data into DimStation table.

Take a screenshot of the first 5 rows in the table DimStation.

Name the screenshot `11-DimStation.pmg`.  

## Task 12: Load data into the fact table FactTrips  

Download the data from [https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/Final%20Assignment/FactTrips.csv](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/Final%20Assignment/FactTrips.csv)  

Load this data into FactTrips table.

Take a screenshot of the first 5 rows in the table FactTrips.

Name the screenshot `12-FactTrips.png`.  

<h1 align="center">Exercise 4 - Write aggregation queries and create materialized views</h1>  

In this exercise, you will query the data you have loaded in the previous exercise.  

## Task 13: Create a grouping sets query  

Create a grouping sets query using the columns stationid, trucktype, total waste collected.

Take a screenshot of the SQL and the output rows.

Name the screenshot `13-groupingsets.png`.  

## Task 14: Create a rollup query  

Create a rollup query using the columns year, city, stationid, and total waste collected.

Take a screenshot of the SQL and the output rows.

Name the screenshot `14-rollup.png`.  

## Task 15: Create a cube query  

Create a cube query using the columns year, city, stationid, and average waste collected.

Take a screenshot of the SQL and the output rows.

Name the screenshot `15-cube.png`.  

## Task 16: Create a materialized view  

Create a materialized view named max_waste_stats using the columns city, stationid, trucktype, and max waste collected.

Take a screenshot of the SQL.

Name the screenshot `16-mv.png`.  

# Author
# ***[Matteo Meloni](https://www.linkedin.com/in/matteo-meloni-40a357154/)***
