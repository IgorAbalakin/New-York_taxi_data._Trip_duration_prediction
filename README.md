# New York taxi data (trip duration prediction) 

### Content
[1. Project Description](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Project-Description) 

[2. Data overview and basic analysis](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Data-overview-and-basic-analysis) 

[3. Exploration Data Analysis (EDA)](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Exploration-Data-Analysis-(EDA)) 

[4. Feature engineering](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Feature-engineering) 

[5. Solving the regression task: linear regression and decision trees](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Solving-the-regression-task-linear-regression-and-decision-trees) 

[6. Solving the regression task: ensemble methods and forecasting](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Solving-the-regression-task-ensemble-methods-and-forecasting) 

[7. Data used in the project that couldn't be placed in the GitHub repository](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Data-used-in-the-project-that-couldn-t-be-placed-in-the-GitHub-repository) 


 
____
### Project Description 

It's known that the cost of a taxi in the USA is calculated on the basis of a fixed rate and tariff cost, the value of which depends on time and distance. Rates vary depending on the city.

In turn, the trip duration depends on many factors, such as the direction of the trip, time of day, weather conditions, and so on.

Thus, if we develop an algorithm capable of determining the trip duration, it'll be possible to predict its cost in the most trivial way, for example, simply multiplying the cost by a given fare.

Taxi services store huge amounts of information about trips, including data such as the end and start points of the route, the date of the trip and its duration. This data can be used to predict the duration of the trip in automatic mode with the involvement of artificial intelligence.

*Business task:* determine the characteristics and use them to predict the duration of a taxi trip.

*Technical task*: to create a machine learning model that based on the proposed characteristics of the client, will predict a numerical feature — the trip duration, so to solve the regression task.
 
:arrow_up: [up to content](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Content)

 ____
### Data overview and basic analysis

Customer and taxi company data:

        id — unique trip ID;
        vendor_id — the unique identifier of the service provider (taxi company) associated with the trip.

Temporary data:

        pickup_datetime — date and time when the trip counter was turned on;
        dropoff_datetime — date and time when the trip counter was turned off.

Geographical data:

        pickup_longitude — the longitude where the counter was turned on;
        pickup_latitude — the latitude where the counter was turned on;
        dropoff_longitude — the longitude where the counter was turned off;
        dropoff_latitude — the latitude where the counter was turned off.

Other features:

        passenger_count — number of passengers in the vehicle (value entered by the driver);
        store_and_fwd_flag — a flag that indicates whether a trip has been saved in the vehicle's memory before being sent to the supplier (Y — store and forward, N — don't store and forward the trip).

Target value:

        trip_duration — duration of the trip in seconds.

:arrow_up: [up to content](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Content)

____
### Exploration Data Analysis (EDA)

In this part of the project, you need to perform:

        1. Research data;
        2. Search for patterns that allow us to formulate preliminary hypotheses about which factors are decisive for the trip duration;
        3. Creating visualizations that illustrate this study.


:arrow_up: [up to content](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Content)

 ____
### Feature engineering

Before making a model, we need to perform the following steps:

        1. Many machine learning algorithms cannot process categorical features in their usual form. Therefore, we need to encode them.
        2. It's necessary to scale and transform some features in order to improve the convergence of models based on numerical methods.
        3. Select the features that will be used for training the model.

:arrow_up: [up to content](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Content)
 
____
### Solving the regression task: linear regression and decision trees

In this part of the project, we need to perform:

        1. Make a linear regression model on a training sample.
        2. Generate polynomial features of the second degree using PolynomialFeatures from the sklearn library. Make a second degree polynomial regression model on a training sample.
        3. Create visualizations that illustrate this study.
        4. Create a second-degree polynomial regression model with L2-regularization (Tikhonov regularization) on a training sample (set the regularization coefficient to 1, and leave the other parameters by default).
        5. Create a Decision Tree model (Decision Tree Regressor) on a training sample.

:arrow_up: [up to content](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Content)
 
____
### Solving the regression task: ensemble methods and forecasting

1. Create a random forest model on a training sample. As hyperparameters , we specify the following:

        n_estimators = 200;
        max_depth = 12;
        riterion = 'squared_error';
        random_state = 42.

2. Create a gradient boosting model over decision trees (Gradient Boosting Regressor) on a training sample. As hyperparameters , we specify the following:

        learning_rate = 0.5;
        n_estimators = 100;
        max_depth = 6;
        min_samples_split = 30;
        random_state = 42.

3. For the best of the designed models, calculate the median absolute error (MeAE, in sklearn — the media_absolute_error function) of predicting the taxi trip  duration on a validation sample.

:arrow_up: [up to content](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Content)
  ____
  
### Data used in the project that couldn't be placed in the GitHub repository

[File with a training sample](https://drive.google.com/file/d/1X_EJEfERiXki0SKtbnCL9JDv49Go14lF/view?usp=sharing)

[Data files from OSRM for trips from the training table](https://drive.google.com/file/d/1ecWjor7Tn3HP7LEAm5a0B_wrIfdcVGwR/view?usp=sharing)

[File with a test sample](https://drive.google.com/file/d/1C2N2mfONpCVrH95xHJjMcueXvvh_-XYN/view?usp=sharing)

[Data files from OSRM for trips from the test table](https://drive.google.com/file/d/1wCoS-yOaKFhd1h7gZ84KL9UwpSvtDoIA/view?usp=sharing)

:arrow_up: [up to content](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Content)
  ____
