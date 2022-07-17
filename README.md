# Movies-ETL
ELT process with Wiki and Kaggle data to PostgreSQL

# Purpose
The purpose of this project is to perform the ETL process by adding the data from Wikipedia, Kaggle, and MovieLens to a PostgreSQL database. I created an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. For that I writed one function that takes in all the three files — Wikipedia data, Kaggle metadata, and the MovieLens rating data, and run the ETL process by adding the data to a PostgreSQL database.

Python 
Pandas
Jupyter Notebook
PostgreSQL

# Results

## 1. Wrote an ETL Function to Read Three Data Files
Using my knowledge of Python, Pandas, the ETL process, and code refactoring, I wrote a function that reads in the three data files and creates three separate DataFrames:

* The wiki_movies_df DataFrame:

![img1.png](/images/img1.png) 

* The kaggle_metadata DataFrame:

![img2.png](/images/img2.png) 

* The ratings DataFrame

![img3.png](/images/img3.png) 

## 2. Extracted and Transformed the Wikipedia Data
I extracted and transformed the Wikipedia data so I can merge it with the Kaggle metadata. While extracting the IMDb IDs I used a regular expression string and dropping duplicates, used a try-except block to catch errors.

* The new wiki_movies_df DataFrame:

![img4.png](/images/img4.png) 

* Columns from wiki_movies_df DataFrame:

![img5.png](/images/img5.png) 

## 3. Extracted and Transformed the Kaggle Data
I extracted and transformed the Kaggle metadata and MovieLens rating data, then convert the transformed data into separate DataFrames. Then, I merged the Kaggle metadata DataFrame with the Wikipedia movies DataFrame to create the movies_df DataFrame. 

* The new movies_df DataFrame:

![img7.png](/images/img7.png) 

Finally, I merged the MovieLens rating data DataFrame with the movies_df DataFrame to create the movies_with_ratings_df.

* The new movies_with_ratings_df DataFrame:

![img6.png](/images/img6.png) 

## 4. The Movie Database was created
Using my knowledge of Python, Pandas, the ETL process, code refactoring, and PostgreSQL I added the movies_df DataFrame and MovieLens rating CSV data to a SQL database:

![img8.png](/images/img8.png) 

* The screenshot of query and the output confirms that the movies table has 6,052 rows:

![img9.png](/images/img9.png) 