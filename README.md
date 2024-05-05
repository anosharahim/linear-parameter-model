# Predicting Yosemite Village Weather

This project aims to model the yearly temperature variations in Yosemite Village, California, using Radial Basis Functions (RBFs) and Linear Parameter Modeling.

## Techniques Used

- Linear Parameter Modeling: Assumes a linear relationship between input features and the target variable.
- Radial Basis Functions (RBFs): Capture non-linear relationships and introduce complexity to the model.

## Approach

1. Preprocess the data from time and date formats to numerical values.
2. Split the data into training and test sets.
3. Map input dimensions to a higher-dimensional space using RBFs.
   - Randomly select centroids and tune the number of centroids as a hyperparameter.
   - Set the width of the centroids relative to the surrounding data points using a heuristic (median of pairwise distances).
4. Conduct linear regression using the expanded representation of the input data.
5. Evaluate the model performance using R-squared metric.

<img width="560" alt="image" src="https://github.com/anosharahim/linear-parameter-model/assets/55622095/4af49084-e24a-44a5-9549-1f6795b4e6f5">


## Hyperparameter Tuning

- Number of Centroids:
  - Tested different values and found that 50 centroids provide a good balance between capturing complexity and avoiding overfitting.
  - Fewer than 50 centroids reduced performance, while more than 50 had minimal impact on R-squared.

- Width of RBFs (Sigma Squared):
  - Set using a heuristic that takes the median of pairwise distances between input points.
  - This approach systematically determines the similarity and width of the RBFs based on the data distribution.

## Results

- Using day-of-year data as input provides better predictions (R2 = 53.59%) compared to using only time-of-day data (R2 = 3.67%).
- Combining both inputs slightly improves the model performance (R2 = ~60%).
- Setting the width of the RBFs using the median of pairwise distances between data points improves the model performance.

Note: Due to RAM limitations, the model was run on a subset of the dataset. Increasing the data size might further improve the model metrics.
