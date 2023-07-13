"# Movie-Recommender" 
# Movie Recommendation System

This code implements a movie recommendation system using content-based filtering. It recommends similar movies based on the content features such as genres, overview, keywords, cast, and crew.

## Prerequisites
- Pandas (imported as `pd`)
- NumPy (imported as `np`)

## Data Loading
The code loads two CSV files: `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv`, which contain information about movies. The data is stored in the `movie` and `credits` dataframes, respectively.

## Data Cleaning and Preparation
The code performs several data cleaning steps to prepare the data for analysis. Unnecessary columns are removed, and important columns such as genres, title, id, cast, and crew are selected. Null values are dropped, and duplicates are removed from the dataframe.

The `genres`, `keywords`, `cast`, and `crew` columns contain lists of dictionaries. The code converts them into a more readable format by extracting relevant information.

## Movie Recommendation
The code creates a new dataframe `nw` with columns `movie_id`, `title`, and `tags`. The `tags` column is created by combining the `overview`, `genres`, `keywords`, `cast`, and `crew` columns. Text preprocessing techniques such as converting to lowercase and stemming are applied to the `tags` column.

Text vectorization is performed using the bag-of-words approach. The `CountVectorizer` class from scikit-learn is used to convert the text data into vectors. The resulting vectors are used to compute cosine similarity between movies.

The `recommend` function takes a movie title as input and recommends similar movies based on cosine similarity. It prints the titles of the top 5 recommended movies.

## Usage
To use the movie recommendation system, follow these steps:
1. Load the `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv` files.
2. Execute the provided code.
## Note
Make sure to adjust the file paths when loading the CSV files according to your specific directory structure.
