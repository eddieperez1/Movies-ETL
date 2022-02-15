# Movies-ETL

This project was written in Python 3.9 using Jupyter Notebooks.
Postgress 11.4 and pgadmin 4 v5.7 are needed to run the code in this project.
config.py is needed for this project. This file contains a variable dbpassword to store the database password for Postgres as a string.
The [wikipedia-movies.json](/Resources/wikipedia-movies.json) and [movies_metadata.csv](/Resources/movies_metadata.csv) are found in the resources folder in the repository.
The ratings.csv can be download at kaggle dataset [the movies dataset](https://www.kaggle.com/rounakbanik/the-movies-dataset).

## Overview of Project

A fake company Amazing Prime is creating a dataset for a data science competetion. This project creates an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. The code was refactored to create one function that takes in the three files—Wikipedia data, Kaggle metadata, and the MovieLens rating data—and performs the ETL process by adding the data to a PostgreSQL database.

## Delivarble 1:
### Write an ETL Function to Read Three Data Files

Using Python, Pandas, the ETL process, and code refactoring, a function was written that reads in the three data files and creates three separate DataFrames. The function is stored in [ETL_function_test.ipynb](/ETL_function_test.ipynb).

## Deliverable 2
### Extract and Transform the Wikipedia Data

Using Python, Pandas, the ETL process, and code refactoring, extract and transform the Wikipedia data so it can merge with the Kaggle metadata. While extracting the IMDb IDs using a regular expression string and dropping duplicates, try-except block was used to catch errors. The function is stored in [ETL_clean_wiki_movies.ipynb](/ETL_clean_wiki_movies.ipynb).

## Deliverable 3
### Extract and Transform the Kaggle data

Using Python, Pandas, the ETL process, and code refactoring, extract and transform the Kaggle metadata and MovieLens rating data, then convert the transformed data into separate DataFrames. Then, the Kaggle metadata DataFrame merged with the Wikipedia movies DataFrame to create the movies_df DataFrame. Finally, the MovieLens rating data DataFrame merge with the movies_df DataFrame to create the movies_with_ratings_df.  The function is stored in [ETL_clean_kaggle_data.ipynb](/ETL_clean_kaggle_data.ipynb).

## Deliverable 4
### Create the Movie Database

Use Python, Pandas, the ETL process, code refactoring, and PostgreSQL to add the movies_df DataFrame and MovieLens rating CSV data to a SQL database. The function is stored in [ETL_create_database.ipynb](/ETL_create_database.ipynb).

## Summary

The function created in deliverable 4 now automates the ETL process for Wikipedia and Kaggle datasets. To test if the function worked correctly, the following queries where run in pgadmin 4:
```
SELECT COUNT(*) FROM movies;
```
and 
```
SELECT COUNT(*) FROM ratings;
```
The result query will look like the following: 

![movies_query.PNG](/Resources/movies_query.PNG)

![ratings_query.PNG](/Resources/ratings_query.PNG)
