# ETL-Telecom-SSIS
ETL pipeline for telecom company to process csv files and load data into database with validation and rejected records handling with SQL Server Integration Services 'SSIS' .


## About of Project 
The csv file has customer activity data such as  IMSI IMEI CELL and other columns. 
The ETL process was designed to clean and validate the data before loading into the target database.  
Invalid or rejected records are stored in a separate table with the original csv file name.

The required processing exceeds this previous data to store it in the database and Rejected records will be stored in a separate table, with the original CSV file name recorded :

<img src="Task Image/Tabel.png" alt="ETL Flow" width="500">

<img src="Task Image/Case.png" alt="ETL Flow" width="500">

## Processing Rules

- IMSI is validated and records with null are rejected.
- IMSI is joined with reference table to get subscriber id and if missing it is replaced with -99999.
- IMEI is split into TAC first 8 characters and SNR last 6 characters if invalid replaced with -99999.
- CELL and LAC must not be null. I had a problem because I wasn't making NULL,Then alter on table to change constraint NULL.
- Event timestamp must be a valid datetime format.

## Rejected Records
Any record that does not pass validation is stored in a rejected table.  

## File Management
After the data is processed and loaded into the database.


## Tools i used 
- SQL server.
- SQL Server Integration Services "SSIS" apply on VS.



## Project Structure

<img src="Task Image/Tabels.png" alt="ETL Flow" width="900">


<img src="Task Image/Control_Flow.png" alt="ETL Flow" width="900">


<img src="Task Image/Data_Flow.png" alt="ETL Flow" width="900">


<img src="Task Image/SUCC_Mappings.png" alt="ETL Flow" width="900">


<img src="Task Image/Failed_Mappings.png" alt="ETL Flow" width="900">



<img src="Task Image/Diagram.png" alt="ETL Flow" width="900">


<img src="Task Image/Data.png" alt="ETL Flow" width="900">

## Conclusion
This project shows how to design and implement ETL pipeline for telecom company using csv files as source and applying business rules before loading data into database

## Conclusion
This project shows how to design and implement ETL pipeline for telecom company using csv files as source and applying business rules before loading data into database
