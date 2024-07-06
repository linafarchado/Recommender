# Movie Recommendation System

## Overview
This project implements a sophisticated movie recommendation system using collaborative filtering and content-based approaches. It utilizes the Surprise library for matrix factorization and incorporates custom content similarity metrics to enhance recommendation quality.

## Methodology

### Datasets
1. Movies ratings
2. Movies details
3. Movies links
3. IMDb basics
4. IMDb ratings 

### Data Preparation
1. Multiple datasets are merged to create a rich feature set including:
   - User ratings
   - Movie metadata (title, genres, year)
   - Aggregated ratings (average rating, number of votes)

2. The final dataset structure:
   `userId, movieId, rating, title, genres, year, averageRating, numVotes`

### Model Architecture
1. **Collaborative Filtering**: Singular Value Decomposition (SVD) from Surprise library
2. **Content-Based Filtering**: Jaccard similarity on movie genres
3. **Hybrid Approach**: Combining collaborative and content-based methods

### Key Features
1. Dual-user recommendations
2. Genre similarity integration
3. Rating normalization based on user history

## Experiments

### Base Model
- SVD model with parameters:
  ```python
  SVD(n_factors=100, n_epochs=20, lr_all=0.005, reg_all=0.02)
  ```

### Evaluation Metrics
1. Root Mean Square Error (RMSE)
2. Mean Absolute Error (MAE)
3. Precision@10
4. Recall@10

## Results

### Base Model Performance
```
RMSE: 0.7776093162550577
MAE: 0.5867644104050305
Precision@10: 0.8381125386648483
Recall@10: 0.5850689540573039
```

### Sample Recommendations
```
      predicted_score  
7            4.135233  
134          4.082209  
137          4.050195  
666          3.977311  
1096         3.893091
```

## Conclusions

1. **Hybrid Approach Effectiveness**: The combination of collaborative filtering (SVD) and content-based filtering (genre similarity) provides robust recommendations, addressing cold-start problems and improving recommendation diversity.

2. **Dual-User Recommendations**: The system's ability to generate recommendations for two users simultaneously is a unique feature, useful for group recommendations.

3. **Performance Metrics**: The base model shows strong performance, particularly in precision@10, indicating high relevance of top recommendations.

4. **Scalability**: The use of SVD allows the system to handle large datasets efficiently, crucial for real-world applications.

5. **Customization Potential**: The integration of movie metadata (genres, year) allows for fine-tuned recommendations based on content preferences.

6. **Future Improvements**:
   - Incorporate more advanced hybrid techniques
   - Explore deep learning models for better feature extraction
   - Implement real-time updating capabilities for production environments

In conclusion, this recommendation system demonstrates a robust approach to movie recommendations, effectively combining collaborative and content-based methods. The high precision and recall scores indicate its potential for practical applications, while the dual-user recommendation feature sets it apart from traditional systems.