# ETL-Driven-Cinema-analysis

# ETL - Extraction, Transformation, and Loading
*Analyzing Movies Data with Python, Regular Expressions, and SQL Databases*

## Project Overview

### Objective
The Amazing Prime, a video streaming company, has sponsored a hackathon where participants aim to predict the success of low-budget movie releases. To assist participants in their analysis, we need to provide a clean and organized dataset. This project centers around the ETL (Extract, Transform, Load) process and encompasses the following steps:

- **Extraction**: Gathering data from two distinct sources.
    - Web scraping movie information from Wikipedia for films released since 1990.
    - Acquiring rating data from Kaggle.
- **Transformation**: Processing and refining the data using Jupyter Notebook, Python, Pandas, and Python's Regular Expression module.
- **Loading**: Storing the cleaned dataset using PostgreSQL and pgAdmin.

## Overview of the Code

The objective of this analysis is to establish an automated pipeline that can extract, transform, and load data. This analysis is divided into four parts, each step progressively building from data extraction and function testing to data transformation and cleaning, and finally, connecting and loading the data into a database. The entire ETL process can be executed with a single call to the function ***extract_transform_load*** in the final step [ETL_create_database.ipynb](ETL_create_database.ipynb). The ETL process is divided into four Jupyter Notebook files:

1. [ETL_function_test.ipynb](ETL_function_test.ipynb):
    - Data is extracted from the website in JSON and CSV formats.
    - Data is transformed into Pandas data frames.
    - The JSON file requires an additional step - loading the file first and then transforming it into a data frame.

2. [ETL_clean_wiki_movies.ipynb](ETL_clean_wiki_movies.ipynb):
    - The *clean_movie* function consolidates scattered data from alternative languages into one column called *alt_titles*.
    - Its subfunction *change_column_name* standardizes column names.
    - In the *extract_transform_load* function, the transformation process for Wikipedia movies data begins and includes:
        - Utilization of Python **list comprehensions**.
        - Usage of *apply()* and *map()* methods in conjunction with **lambda functions**.
        - Application of regular expressions or **RegEx**.

3. [ETL_clean_kaggle_data.ipynb](ETL_clean_kaggle_data.ipynb):
    - The *extract_transform_load* function handles new tasks for cleaning Kaggle data and includes:
        - Changing data types using methods like *pd.to_numeric*, *astype()*, and Python comparison operators for Boolean types.
        - Handling missing values and filtering unwanted columns.
        - Merging data frames using the *pd_merge* method.

4. [ETL_create_database.ipynb](ETL_create_database.ipynb):
    - Finally, the function in its last step connects to the database using the **sqlalchemy** library and the **to_sql** method.
    - The entire ETL process can be initiated with a single call to the *extract_transform_load* function.

## Resources

Data Sources:

- Wikipedia web scrape [JSON file](Resources/wikipedia-movies.json).
- Kaggle data from [Kaggle.com](https://www.kaggle.com/rounakbanik/the-movies-dataset) - consisting of two files: movies_metadata.csv and ratings.csv.

Environment:
- Python 3.7

Dependencies:
- Please refer to Jupyter Notebook [ETL_create_database.ipynb](ETL_create_database.ipynb) for a complete list of dependencies.

Software:
- Jupyter Notebook
- PostgreSQL and PgAdmin
