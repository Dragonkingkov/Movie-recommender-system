
# Movie Recommender System
## Project Overview
A content-based movie recommendation system implemented in Jupyter Notebook that suggests similar movies based on cast, crew, genres and other movie features. The system uses cosine similarity to find movies with similar characteristics.

### Note
File recc_sys_preprocessing.ipynb and recc_sys_dataset2020_2023.ipynb are the preprocessing notebooks.
reccomendersystemproject.ipynb is main implementing code.
## Dataset
The system uses multiple datasets merged together:
- Movie metadata from IMDB
- Cast and crew information from TMDB
- Movie listings from Wikipedia (2018-2023)
- Additional movie features from Kaggle datasets

## Requirements
- pandas
- numpy
- scikit-learn
- tmdbv3api
- requests

## Setup 
1. Install required packages

2. Get TMDB API key:
- Register at TMDB website
- Generate API key from your account settings


## Data Processing Pipeline

### Data Loading and Cleaning:

- Load movies data from multiple sources
- Handle missing values using SimpleImputer
- Convert genres from pipe-separated strings to space-separated format
- Process release dates and extract years


### Feature Engineering:

- Extract actor names from cast information
- Get director names from crew data
- Combine features into a single string for similarity calculation


### Similarity Calculation:

- Convert text data to numerical format using CountVectorizer
- Calculate cosine similarity between movies

## Usage
In your Jupyter notebook:

        # Input a movie title to get recommendations
        movie_input = input("Enter a movie name: ")
        recommendations = rcmd(movie_input)

        if isinstance(recommendations, str):  # If it's an error message
          print(recommendations)
        else:
          print("Recommended Movies:")
          for movie in recommendations:
                  print(movie)
## Functions

#### create_similarity(data)
Creates cosine similarity matrix from movie features
#### rcmd(movie_title)
Returns top 10 similar movies for given movie title
## Data Sources

- IMDB Dataset (movies, ratings)
- TMDB API (genres, additional metadata)
- Wikipedia (American films 2018-2023)
- Kaggle movie datasets (supplementary information)

## Future improvements
Create Web App with search suggestions
