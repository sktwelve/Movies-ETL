# Extract, Transform, Load: Movies Database

## Overview:
We have created a program to take the databases of movies, ratings and information then cleaning them to combine them into one leglible table. Now the company is asking for a way to automate the process using 3 input files which will be cleaned and then merged to then be passed to a sql database.

## Function Test
The first step was to create a function to open all the files passed to the program by the use of pandas and json.load. The files are then passed to dataframes to ensure they are visible on python.

## Cleaning the Movies Wiki
Building off of the function that we created, we begin cleaning the data of the first file. We start by filtering out the tv shows to have a dataframe that only has movies. The ids are extracted from the links in order to create a new column so duplicates can be dropped based on new movie id column. Regular expressions are used to format the budget, revenue, date, and running times of each movie. We then create a function that will combine all the language columns and agregate the information from similar columns into a singular columns to reduce the number of columns.

## Cleaning Kaggle and Ratings
We begin by dropping all adult movies from the kaggle dataframe then move on to make sure the data types of each columns match the data that it holds. The wiki and kaggle dataframes are merged then unnecessary columns are dropped. A function is created to fill all nan values with zeros to ensure all fiels are filled. The columned are filtered and renamed for legibility then the rating dataframe is merged to the main dataframe.

## Creating the Database
The program is edited to take 3 files at the programs location that will be passed as the wiki file, kaggle file, and the ratings file. A connection is created to the sql server is created which will open the path for data. All the previous steps are performed then the finished dataframe will be passed to the sql database as a table.
