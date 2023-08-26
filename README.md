# Kaggle-New-York-City-Taxi-Prediction
Tasked with predicting the fare amount for a taxi ride in New York City given the pickup and drop-off location. 

## Data Processing
There is 55M data, we selected 6M to 15M of them for training due to lack of memories. Data preprocessing plays an essential role in the successful prediction of a model.

#### 1. Remove missing data:  
Remove data with missing features directly since we have a large number of data collections.  
#### 2. Remove outliers:  
Remove locations outside New York City, unreasonable number of passengers, and fare amounts are considered outliers.  
(1) Remove passengers > 7 and < 1  
![passenger](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/number%20of%20passenger.png)  
(2) Remove the position outside the New York City  
![location](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/location.png)  
(3) Remove ‘fare_amount’ < 2.5 and > 500  
![fare](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/fare.png)  
(4) Remove some locations on the water  
![on water](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/on%20water.png)  
#### 3. Process time features:  
The feature includes time and date information. Split ‘pickup_datatime’ into 4 new features: year, month, weekday, and hour. This approach adds useful information as features, they adds complexity to the model to enhance the precision of its predictions.  
#### 4. Calculate Haversine distance:  
The Haversine distance is the angular distance between two points on the surface of a sphere, it can be calculated with given longitude and latitude.  
![haversine](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/haversine.png)  
#### 5. Calculate Chebyshev distance:  
Since New York City is built in a grid plan, Chebyshev distance can be used to represent the distance between 2 locations in NYC.  
![chebyshev](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/chebyshev.png)   
#### 6. Add airports:  
Help the models to capture the proximity of pickup or drop-off locations to predefined landmarks.  
(1) JFK Airport: Longitude -73.7781, Latitude 40.6413  
(2) LGA Airport: Longitude -73.8740, Latitude 40.7769  
(3) EWR Airport: Longitude -74.1745, Latitude 40.6895  
![airport](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/airpoet.png)  
#### 7. Remove useless items:  
‘key’ and 'pickup_datatime’. The feature ‘key’ is seen as the ID of the trips, and ‘pickup_datatime’ has turned into 4 new features: year, month, weekday, and hour.  
#### 8. Observe the correlation between features and target:  
![correlation](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/correlation.png)  
## Model  
#### models comparison  
![model](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/model.png)  
#### Ensemble  
![ensemble](https://github.com/hsieh672/Kaggle-New-York-City-Taxi-Prediction/blob/main/image/ensemble.png)



