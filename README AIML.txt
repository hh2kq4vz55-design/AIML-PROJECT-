Name : Sidharth Yadav
Reg.No. : 25BCE11296
## Movie Recommendation System


## Overview


This project is a simple movie recommendation system built using Python. The goal of the project is to recommend movies that are similar to a movie selected by the user.


Instead of using ratings or user behavior, this system works using a content-based recommendation approach. It analyzes important information about each movie such as the movie description, genres, keywords, cast members, and director. By comparing these features across movies, the system identifies movies that are similar and suggests them to the user.


For example, if a user searches for a movie like Avatar, the system will recommend other movies that share similar themes, genres, or actors.


How the System Works


The recommendation system follows a few main steps:


1. Dataset Loading


The project uses the TMDB 5000 Movies Dataset, which contains information about thousands of movies. Two datasets are used:


tmdb_5000_movies.csv
tmdb_5000_credits.csv


These files contain movie details such as titles, descriptions, genres, cast members, and crew information.


Both datasets are merged together to create a single dataset that contains all the necessary movie information.


2. Data Cleaning and Processing


After merging the datasets, only the most useful columns are kept:


Movie ID
Title
Overview (movie description)
Genres
Keywords
Cast
Crew


Missing values are removed to ensure the data can be processed correctly.


The dataset contains structured information in text format. This information is converted into lists so that it can be processed easily.


From the cast, only the top three actors are used.
From the crew, only the director is extracted.


3. Feature Creation


To compare movies, different features such as genres, keywords, cast members, director names, and the movie description are combined into a single column called tags.


This combined feature represents the overall characteristics of each movie.


4. Text Vectorization


The tags are converted into numerical form using Count Vectorization.


This process transforms text data into numerical vectors based on the frequency of words. It allows the computer to compare movies mathematically.


5. Similarity Calculation


Once the movies are represented as vectors, the similarity between movies is calculated using Cosine Similarity.


Cosine similarity measures how closely two movies are related based on their feature vectors.


Movies with similar tags will have higher similarity scores.


6. Generating Recommendations


When a user enters the name of a movie, the system:


Finds that movie in the dataset
Calculates similarity scores with all other movies
Sorts the movies based on similarity
Displays the top 5 most similar movies


This allows the system to quickly recommend movies related to the selected movie.


## Technologies Used


Python – main programming language
Pandas – data processing and dataset handling
AST – used to convert structured text into lists
Scikit-learn – used for vectorization and similarity calculation
CountVectorizer – converts text into numerical vectors
Cosine Similarity – measures similarity between movies
Project Structure
movie-recommendation-system
│
├── movie_recommender.py
├── tmdb_5000_movies.csv
├── tmdb_5000_credits.csv
├── README.md
Installation


First, install the required libraries.


pip install pandas scikit-learn
How to Run the Project
Download the TMDB dataset files.
Place the CSV files in the same folder as the Python script.
Run the Python script.


# Example command:


python movie_recommender.py


The program will analyze the dataset and generate recommendations.


# Example


If the system is asked to recommend movies for Avatar, it will return a list of movies that share similar genres, themes, or cast members.


# Example output:


Guardians of the Galaxy
Star Trek
John Carter
The Avengers
Alien


These movies are recommended because they share similar characteristics with the selected movie.


## Learning Outcomes


Through this project, the following concepts were explored:


Data cleaning and preprocessing
Working with real-world datasets
Text processing and feature extraction
Vectorization of text data
Cosine similarity for recommendation systems
Building a simple content-based recommender system
Possible Improvements


Although the system works well, several improvements could be added in the future:


Build a web interface using Streamlit or Flask
Add movie posters and ratings
Implement collaborative filtering
Improve recommendations using TF-IDF vectorization
Deploy the project as a web application
Conclusion


This project demonstrates how machine learning techniques can be used to build a simple movie recommendation system. By analyzing movie descriptions and metadata, the system can identify similarities between movies and recommend relevant movies to users.


Even though the project uses a basic content-based approach, it shows how recommendation systems can help users discover new content more efficiently.