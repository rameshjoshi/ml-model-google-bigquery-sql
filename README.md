# ml-model-google-bigquery-sql

**scenario**
  Your organization shuttles hundreds of employees to and from the office every day using private taxi services. They'd like to optimize the resources assigned using Machine Learning. Using BigQuery to Explore and Analyze Data
  
**Resource**
  BigQuery

**flow**
![image](https://github.com/rameshjoshi/ml-model-google-bigquery-sql/assets/7277702/02c1031e-d0ea-4fed-adea-7ecae8f1e097)

  1. Access BigQuery
  2. Add the Chicago Taxi Trips Dataset
  3. Examine the Dataset Schema
  4. Examine the Dataset Details
  5. Query the Data
         SELECT (  fare, trip_miles, trip_seconds
                ) FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips` 
        LIMIT 2000
  6. Count Rows where Fare Is Not Null
        SELECT COUNT(fare) AS count_of_non_null_fares
        FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`
        WHERE fare IS NOT NULL;
  7. Find Correlations between Fare and Other Columns
        SELECT AVG(fare) AS AVG_FARE
        FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips` LIMIT 10000
  8. Find Average Fare
        SELECT 
        EXTRACT(DAYOFWEEK FROM trip_start_timestamp) AS day_of_week,
        AVG(fare) AS average_fare
      FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`
      WHERE fare IS NOT NULL
      GROUP BY day_of_week
      ORDER BY day_of_week;


