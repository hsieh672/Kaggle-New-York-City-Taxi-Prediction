# Kaggle-New-York-City-Taxi-Prediction
Tasked with predicting the fare amount for a taxi ride in New York City, given the pickup and drop-off location.

## Data Processing
We have a dataset of 55 million records, but due to memory constraints, we have selected a subset ranging from 6 million to 15 million for training purposes. Data preprocessing is a critical step in ensuring the successful performance of our predictive model.  

#### 1. Removing missing data:  
Given the large size of our dataset, we will directly remove records with missing features.  
#### 2. Removing outliers:  
To improve the quality of our dataset, we will eliminate data points that fall outside the geographic boundaries of New York City, as well as those with unreasonable passenger counts or fare amounts, which are considered outliers.  
(1) Remove records with passengers > 7 or < 1 to address passenger count outliers.  
![passenger](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/number%20of%20passenger.png)  
(2) Remove the position outside the New York City  
![location](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/location.png)  
(3) Remove ‘fare_amount’ < 2.5 and > 500  
![fare](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/fare.png)  
(4) Remove some locations on the water  
![on water](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/on%20water.png)  
#### 3. Process time features:  
The feature includes time and date information. Split' pickup_datatime' into four new features: year, month, weekday, and hour. This approach adds useful information as features; they add complexity to the model to enhance the precision of its predictions.  
#### 4. Calculate Haversine distance:  
The Haversine distance is the angular distance between two points on the surface of a sphere; it can be calculated with a given longitude and latitude.  
![haversine](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/haversine.png)  
#### 5. Calculate Chebyshev distance:  
Since New York City is built in a grid plan, Chebyshev distance can represent the distance between 2 locations in NYC.  
![chebyshev](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/chebyshev.png)   
#### 6. Add airports:  
Help the models to capture the proximity of pickup or drop-off locations to predefined landmarks.  
(1) JFK Airport: Longitude -73.7781, Latitude 40.6413  
(2) LGA Airport: Longitude -73.8740, Latitude 40.7769  
(3) EWR Airport: Longitude -74.1745, Latitude 40.6895  
![airport](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/airpoet.png)  
#### 7. Remove useless items:  
'key' and 'pickup_datatime.' The feature 'key' is seen as the ID of the trips, and 'pickup_datatime' has turned into four new features: year, month, weekday, and hour.  
#### 8. Observe the correlation between features and target:  
![correlation](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/correlation.png)  
## Model  
#### models comparison  
![model](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/model.png)  
#### Ensemble  
![ensemble](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/ensemble.png)



