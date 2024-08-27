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
- Data Wrangling: cleaning, scaling, and transforming the dataset, including converting the `streams` column to a numeric type and applying a log transformation for better visualization.
> Data Transformation
> To better analyze the data, I created two versions of the dataset with different transformations applied to the `streams` column:
> 1. **Scaled Data:** In this version, the `streams` column is scaled by dividing by 1 million to convert the values into millions. This makes the data easier to interpret and visualize without altering the underlying distribution.
> 2. **Log-Transformed Data:** In the second version, a log transformation is applied to the `streams` column. This transformation is particularly useful for compressing large values, reducing skewness, and making it easier to identify patterns in the data.
>
> Both versions of the dataset are used in different analyses to explore how these transformations impact the results and interpretations.

- Exploratory Data Analysis (EDA): Generating histograms and a correlation heatmap to understand the distribution of features and their reltaionships.
- Feature Selection: Utilizing Lasso regression and grid search with cross-validation to select the most relevant features for predicting song popularity.
- Model Evaluation: Assessing the model's performance using metrics such Mean Absolute Error (MAE), Mean Squared Error (MSE), and R<sup>2</sup> score.

## Results
The results indicate that the features analyzed (e.g., bpm, danceability, energy, acousticness) do not have a significant or meaningful relationship with the number of streams for the songs in this dataset. The model's poor performance, with a negative R<sup>2</sup> score and high error metrics, suggests that these features are not good predictors of a song's streaming count.

## Limitations
The analysis reveals that factors such as tempo, energy, or instrumental characteristics may not be the primary drivers of a song's popularity. Other factors not captured in this model, such as marketing efforts, artist popularity, or external events, might play a more significant role in determining streaming success. Further research could explore additional features or different modeling approaches to capture complex, non-linear relationships.

<br>

-----

<br>

### Model Comparison: Normal vs. Log-Transformed

**Normal Model:**
- **Mean Absolute Error (MAE)**: 398.507
- **Mean Squared Error (MSE)**: 287,855.412
- **R²**: -0.003

**Log-Transformed Model:**
- **Mean Absolute Error (MAE)**: 0.836
- **Mean Squared Error (MSE)**: 1.104
- **R²**: -0.0003

### Performance Comparison

1. **Mean Absolute Error (MAE)**:
   - **Normal Model**: MAE is 398.507, indicating large average errors in predictions.
   - **Log-Transformed Model**: MAE significantly reduced to 0.836, suggesting improved accuracy in predictions.

2. **Mean Squared Error (MSE)**:
   - **Normal Model**: MSE is 287,855.412, showing high variability in the prediction errors.
   - **Log-Transformed Model**: MSE decreased to 1.104, reflecting reduced error variance and improved prediction performance.

3. **R² (Coefficient of Determination)**:
   - **Normal Model**: R<sup>2</sup> is -0.003, indicating that the model performs worse than a simple mean-based model.
   - **Log-Transformed Model**: R<sup>2</sup> is -0.0003, still negative but slightly better than the normal model, suggesting that the log transformation did not significantly improve the model’s ability to capture variance in the data.

### Analysis

- **Improvement in Error Metrics**: The log-transformed model shows a substantial reduction in MAE and MSE compared to the normal model. This indicates that the log transformation has improved the model's accuracy and precision in predictions.

- **R<sup>2</sup> Comparison**: Both models have negative R<sup>2</sup> values, implying that neither model captures meaningful variance in the target variable (`streams_million`). The slight improvement in R<sup>2</sup> with log transformations suggests a marginal benefit from applying the transformations, but the overall performance remains poor.

- **Grid Search CV Results**: For both models, Grid Search CV did not yield significant improvements. In the normal model, a high alpha value (100) led to severe regularization, shrinking all coefficients and preventing meaningful predictions. In the log-transformed model, the alpha value (1) also resulted in zero coefficients for all features, indicating that the chosen alpha values were not effective in capturing useful patterns.

### Conclusion

- **Log Transformation Benefits**: Applying log transformations improved the MAE and MSE significantly, indicating better model performance in terms of prediction errors. However, the overall ability to capture meaningful variance (R<sup>2</sup>) remained poor, suggesting that the log transformations alone did not fully resolve the model's predictive issues.

- **Model Evaluation**: Both models, despite improvements in error metrics with log transformations, struggle to capture significant relationships in the data. Further investigation into feature engineering, model selection, or additional data preprocessing may be necessary to enhance predictive performance.