# Analyzing the Relationship Between Song Attributes and Streaming Count

## Description
This project explores the characteristics that influence the popularity of songs on major streaming platforms, with a focus on understanding which factors contribute to a song's success. By analyzing a dataset of Spotify songs, this project aims to provide insights that could be valuable for artists, producers, and music enthusiats. the primary goal is to determine if features such as tempo, danceability, energy and instrumentalness are significant predictors of a song's streaming count.

## Data Sources
The dataset used in this project is sourced from Kaggle: 
- [Top Spotify Songs 2023](https://www.kaggle.com/datasets/nelgiriyewithana/top-spotify-songs-2023) 

The dataset includes 953 observations with 24 variables related to the characteristics and streaming numbers of songs.

## Technologies Used
- Programming language: Python 
- Libraries: Pandas, Numpy, Scikit-learn, Matplotlib, Seaborn, Mlxtend

## Analytical Methods
The project involves the following analytical steps:
- Data Wrangling: cleaning and transforming the dataset, including converting the `streams` column to a numeric type and applying a log transformation for better visualization.
- Exploratory Data Analysis (EDA): Generating histograms and a correlation heatmap to understand the distribution of features and their reltaionships.
- Feature Selection: Utilizing Lasso regression and grid search with cross-validation to select the most relevant features for predicting song popularity.
- Model Evaluation: Assessing the model's performance using metrics such Mean Absolute Error (MAE), Mean Squared Error (MSE), and R<sup>2</sup> score.

## Results
The results indicate that the features analyzed (e.g., bpm, danceability, energy, acousticness) do not have a significant or meaningful relationship with the number of streams for the songs in this dataset. The model's poor performance, with a negative R<sup>2</sup> score and high error metrics, suggests that these features are not good predictors of a song's streaming count.

## Limitations
The analysis reveals that factors such as tempo, energy, or instrumental characteristics may not be the primary drivers of a song's popularity. Other factors not captured in this model, such as marketing efforts, artist popularity, or external events, might play a more significant role in determining streaming success. Further research could explore additional features or different modeling approaches to capture complex, non-linear relationships.