# CA5-
By Christopher Strouse &amp; Jasmine Cheng 

CA05 – kNN Movie Recommender Engine
What This Project Does
This notebook builds a movie recommendation engine using the k-Nearest Neighbors (kNN) algorithm. Given a movie called "The Post", it finds the 5 most similar movies in the dataset. This is the same idea as the "More Like This" section you see on Netflix or IMDb.
The Data
The dataset has 30 movies loaded from GitHub. Each movie has an IMDB rating and binary genre flags (1 = Yes, 0 = No) for Biography, Drama, Thriller, Comedy, Crime, Mystery, and History. The Label column is all zeros and is ignored.
Steps
Step 1 – Import Libraries
We bring in pandas for data handling, numpy for math, and sklearn for the kNN model.
Step 2 – Load the Dataset
We load the CSV file directly from GitHub. It has 30 rows and 11 columns.
Step 3 – Explore the Data
We check column names, data types, and missing values. All 30 movies have complete data with no nulls.
Step 4 – Prepare the Feature Matrix
We select the columns the model uses to measure similarity: IMDB Rating, Biography, Drama, Thriller, Comedy, Crime, Mystery, and History. We drop Movie ID, Movie Name, and Label since they aren't useful for distance calculations.
Step 5 – Fit the kNN Model
We build a NearestNeighbors model asking for 6 neighbors using Euclidean distance. We ask for 6 instead of 5 as a buffer, but since The Post isn't in the dataset all 6 results are real recommendations anyway.
Step 6 – Define the Query Movie
We create a feature vector for "The Post" using the values given in the assignment: IMDB Rating 7.2, Biography yes, Drama yes, Thriller no, Comedy no, Crime no, Mystery no, History yes.
Step 7 – Find the 5 Most Similar Movies
We run the kNN query with The Post's feature vector. The model returns the closest movies by Euclidean distance.
Step 8 – Display the Recommendations
We map the results back to movie names and display the top 5 with their distances.
Step 9 – Interpretation
Lower distance means more similar. The top results all share Biography and Drama with The Post, which makes sense. The model only knows about the numbers in the dataset — it doesn't account for actors, directors, or themes.
Results
RankMovieIMDB RatingDistance1Queen of Katwe7.40.22The Wind Rises7.80.6312 Years a Slave8.10.94Hacksaw Ridge8.21.05A Beautiful Mind8.21.0
All five are Biographical Dramas, which matches The Post perfectly.
