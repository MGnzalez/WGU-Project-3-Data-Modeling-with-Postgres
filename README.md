#WGU-Project-3-Data-Modeling-with-Postgres

The purpose of the database was to enable Sparkify to run queries on song play analysis in order to understand what songs users are listening to. In order to do this we will need to define a fact table, songplays that will aggregate data based on our dimension tables: songs, users, artists, and time. As this is a relatively simple query with specific data we are looking for a star schema will be best. From there we will use an ETL pipeline that will take data from two JSON files and transfer it into our fact and dimension tables for Sparkify to run analyses. 

In the repository we have the following files:
sql_queries.py
    This file is the script that creates the file and dimension tables and inserts data into those tables based on on the insert queries.  

create_tables.py
    This file defines functions that creates the sparkify database and runs scripts and queries that reside in the file sql_queries.py.

etl.ipynb
    This file runs a script that extracts/processes the data from the JSON files, cleans and transfers the data to the appropriate dimension tables where it can then be loaded into our fact able.  

etl.py
    This file defines functions that run the scripts created in etl.ipynb in order to input all data into the appropriate tables for queries and data analysis. 

test.ipynb
    This file tests that all scripts in the previous files run correctly with no errors. 

json_files.ipynb
    This file loads the json files used for the analysis as data frames so it is easy to see column names.
    

To run the scripts you need to open the terminal and run the first file: create_tables.py. This will load sql_queries.py and will create the tables and how data is to be inserted into them. From there you will run the 2nd file: etl.py. This will load the etl.ipynb and will insert the data from the JSON files into the tables for queries to be run. For any changes that need to be made to the table attributes and data types, you will use sql_queries.py and then rerun create_tables.py. If you need to make changes to the ETL process you will rerun the first file, create_tables.py and then make changes in the etl.ipynb file before running etl.py to load the new data into the tables. To check data anytime changes have been made please use test.ipynb to validate changes or to check for errors. 
