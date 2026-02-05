![Skills_Network](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-PY0221EN-Coursera/images/image.png)  

<h1 align="center">Final Assignment: Data Warehouse Fundamentals</h1>

# ***Project Scenario***  

You are a data engineer hired by a solid waste management company. It collects and recycles solid waste across major cities in the country of Brazil. They operate hundreds of trucks of different types to collect and transport solid waste. The company would like to create a data warehouse so that it can create reports like:

* Total waste collected per year per city  
* Total waste collected per month per city  
* Total waste collected per quarter per city  
*Total waste collected per year per trucktype  
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

Name the screenshot `1-MyDimDate.jpg` (Images can be saved with either the .jpg or .png extension).
