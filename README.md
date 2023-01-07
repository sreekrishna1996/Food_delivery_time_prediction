## Food_delivery_time_prediction

### Porter: Neural Networks Regression**

***Problem Statement:***

Porter is India's Largest Marketplace for Intra-City Logistics. Leader in the country's $40 billion intra-city logistics market, Porter strives to improve the lives of 1,50,000+ driver-partners by providing them with consistent earning & independence. Currently, the company has serviced 5+ million customers

Porter works with a wide range of restaurants for delivering their items directly to the people.

Porter has a number of delivery partners available for delivering the food, from various restaurants and wants to get an estimated delivery time that it can provide the customers on the basis of what they are ordering, from where and also the delivery partners.

This dataset has the required data to train a regression model that will do the delivery time estimation, based on all those features

***What does ‘good’ look like?***

1. Import the data and understand the structure of the data:
   * usual exploratory analysis steps like checking the structure & characteristics of the dataset
2. Data preprocessing
   * Cleaning of data
   * Feature engineering: Creating the target column time taken in each delivery from order timestamp (created_at) and delivery timestamp (actual_delivery_time)
   * Getting hour of day from the order time and also the day of the week
   * Understanding pandas datetime data type and what function it provides by default
   * Get delivery time in minutes
3. Handling null values
4. Encoding categorical columns
5. Data visualization and cleaning
   * Visualize various columns for better understanding Countplots, scatterplots
6. Check if the data contains outliers
   * Removing outliers by any method
   * Plotting the data again to see if anything has improved
7. Split the data in train and test
8. Creating a baseline model using random forest
9. Checking its various metrics like MSE, RMSE, MAE
10. Scaling the data for neural networks.
11. Creating a simple neural network
    * Trying different configurations
    * Understanding different activation functions, optimizers and other hyperparameters.
12. Training the neural network for required amount of epochs
13. Plotting the losses and checking the accuracy of the model
14. Comparing the results of neural network and random forest


### EDA | ML model building

Porter is India's Largest Marketplace for Intra-City Logistics. Leader in the country's $40 billion intra-city logistics market, Porter strives to improve the lives of 1,50,000+ driver-partners by providing them with consistent earning & independence. Currently, the company has serviced 5+ million customers. Porter works with a wide range of restaurants for delivering their items directly to the people. 

Porter has a number of delivery partners available for delivering the food, from various restaurants. As per the business problem,  we as data scientists are tasked to get an estimated delivery time(Regression) that can be provided to the customers on the basis of what they are ordering, from where and also the delivery partners.

Data of 200k orders were provided with features like total cost, total items etc per. Target variable which time taken in mins had to be feature engineered using created_at and actual_delivery_time time stamps. 

With the help of given data, I was able to build Random Forest model(baseline) and Neural network model, which can help provide the estimated delivery time to the customers. 

1. I performed EDA on the whole data set before I started building regression models. All the inferences from my EDA have been mentioned in my notebook.
2. Feature engineered the target variable, hour and day of the week the order was delivered from the time stamp features.
3. Started with preprocessing before modelling. I mostly used target encoding to convert nominal categorical features to numerical. Missing values were imputed using KNN imputation. No duplicates were found. Outliers were detected using t-sne (for visualisation). Also, found that the dataset followed a unimodal multivariate distribution. Hence removed outliers using elliptical envelope. Scaling was performed using the standard scaler.
4. Built a Random forest regressor using the best hyperparameters. I tuned my hyperparameters for best oob scores on multiple RF models. Using the tuned hyperparameters, my RF model could get an RMSE score of around 12.47 mins on test data set.
5. I, then built a sequential neural network model . My architecture contained 4 hidden layers and 1 output layers. All the layers were dense. RMSprop optimiser was used, MSE loss and RMSE metrics were tracked. RMSE Score on test sets using the best NN architecture and weights was found to be 14.93.
6. The NN model not an improvement over RF as RF_test_score was around 12.4. This shows that for tabular data with less complexity simple models like RF is sufficient to get the predictions.

To whoever reads this, I hope my insights and recommendations from this case study were meaningful.

Thank you,

Krishna
