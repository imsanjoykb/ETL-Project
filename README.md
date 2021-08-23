# Covid-19 Infection ETL Project
By Sanjoy Biswas

## Project Proposal
Based upon the data compiled by John Hopkins University, I want to explore ''' Insert reasons here'''
This will be done by extracting the CSV data and migrating it to a PostgreSQL Database.  

## Project Description
I found data from `data.data.org` that had been compiled from John Hopkins University.  I filtered the data for March 2020 and evaluated the number of cases with respect to the deaths, recovery, and the confirmed cases.  

## Finding Data
All of the data that we used were from `https://data.humdata.org/dataset/novel-coronavirus-2019-ncov-cases` where they compiled by the John Hopkins University Center for Systems Science and Engineering (JHU CSSE) from various sources that include the World Health Organisations, Hong Kong Department of Health, European Centre for Disease Prevention and Control, etc.  This data is always being updated so we are narrowing the scope to the month of March.

## Data Cleanup and Analysis

* TRANSFORMATION STEPS
My transformation steps I needed to clean the data to be readable, presentable, and easy for me to query in the later stages.  This was done by:
  * Developing a cleaning function in python that would select the data in the month of March 2020.  This was applied to all datasets that I have.
  * All of the dates that have in the data sets we treated as values through the `pd.melt` function in Pandas.
  * Found a way of finding the daily increase with respect to each table.  This value was converted from a float to an integer

* LOADING STEPS
  * I established a connection to a local PostgreSQL server in our desktop to store the data
  * I have a schema that just makes the tables and we can confirm it throught `engine.table_names()`
  * I pushed the Pandas DataFrame to the local PostgreSQL server so I can retrieve and query the data in our Jupyter Notebook

* Analysis / SQL Queries
In this part, I want to find:
  * Top 5 countries with the most/least confirmed cases
  * Top 5 countries with the most/least deaths
  * Top 5 countries with the most/least recovered
  * Date in March with the most confirmed/deaths/recovered