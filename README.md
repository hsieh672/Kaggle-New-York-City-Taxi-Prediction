# Kaggle-New-York-City-Taxi-Prediction
Tasked with predicting the fare amount for a taxi ride in New York City given the pickup and drop-off location. 

## Data Processing
There is 55M data, we selected 6M to 15M of them for training due to lack of memories. Data preprocessing plays an essential role in the successful prediction of a model.

#### 1. Remove missing data:  
Remove data with missing features directly since we have a large number of data collections.
#### 2. Remove outliers:  
Remove locations outside New York City, unreasonable number of passengers, and fare amounts are considered outliers.
(1) Remove passengers > 7 and < 1  
(2) Remove the position outside the New York City  
