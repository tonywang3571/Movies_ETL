# Movies_ETL  

## Overview of Project  

**Purpose:**  
Amazing Prime Video, a movie and tv streaming platform on Amazing Prime, decided to sponsor a hackathon to predict which low budget movies will become popular so they could buy the streaming rights to those movies. Britta, who works for Amazing Prime, was tasked to create a clean database from Wikipedia for movies released since 1990 and ratings data from Movielens. We are to extract the data, transform the data to a clean the dataset, and load the data into SQL tables.  

## Resources:  
- Data Source: movies_metadata.csv, ratings.csv, wikipedia-movies.json  
- Software: Python 3.9.7, Jupyter Notebook 6.4.5, pgAdmin 4  

## Analysis and Results  

**Analysis:**  
For this analysis, we extracted data from 3 different data files. The cleaning process had multiple steps to it from removing duplicates, changing the format of the data so they are similar to each other and easier to read, and merging data if there are missing values from one dataset but available in another dataset. From there, we combined the data into one dataframe and loaded the data into SQL tables. In our analysis, we discovered that there are competing data from the different datasets provided. We created a table to decide which dataset to keep, which dataset to drop, and how we should fill in the missing values from the dataset that we are going to keep. After we cleaned the dataframe, we loaded the data into SQL tables with pgAdmin.  
<img src="Resources/competing_data.PNG">  

Since the data was coming from multiple sources, some of the data was listed as, for example, 'title' and 'original title.' For those similarities, we combined them into under one column and removed the other. For differences in formats such as 'January 15, 2022' and '01-15-2022', we used regular expression (regex) to change the formatting of our data so all of the values are in similar formats. This change would give a clear picture of what the data is supposed to represent without confusion when dealing with the data in each column.  

After cleaning all the data, we combined all the data that we need into a single dataframe. From there, loading the data into SQL tables was the simple and easy part.

**Results:**  
From our analysis, we were able to load 6,052 movies and over 26 million ratings for those movies into SQL tables after cleaning and transforming our data.  
<img src="Resources/movies_query.PNG">  
<img src="Resources/ratings_query.PNG">  

## Challenge Summary  

**Summary**  
The purpose of this project is to extra data, transform or clean the data, and load the data into SQL tables for a hackathon sponsored by Amazing Prime Video to predict which low budget movies will become popular so they could buy the streaming rights to those movies. After performing our ETL (extract, transform, load), we were still able to aquire a large and clean dataset for movies and ratings.  

### Codes Used  
(Please look at specific files for codes used)  
Function for [reading and cleaning datasets](https://github.com/tonywang3571/Movies_ETL/blob/master/ETL_clean_kaggle_data.ipynb)  
Function for [connecting and loading to SQL](https://github.com/tonywang3571/Movies_ETL/blob/master/ETL_create_database.ipynb)  