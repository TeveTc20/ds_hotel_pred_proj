# Data Science hotels price prediction 
# Project overview

* Created tool that estimates hotels price in New York from Booking.com and Expedia.com.
* Scraped for over 40,000 hotels from each of the websites.
* Engineered features from the data to see how hotels values their property.
* Optimized regression models such as Linear , Decision Tree , Gaussian Process , ElasticNet , Random Forest , XGBoost to reach the best model for each website seperatly.
* Performed an experiment to see if we can predict the price of the hotel from each website depending on the TTT (Time To Travel) using the best perform model.
* Combined the Hotels data from both website and searching matching hotels , exploring the price difference between the websites and then predict the price difference using regression models.

# Code and Resource Used
**Python Version:** 3.11.1
**Packages:** Selenium , Pandas , Numpy , Matplotlib , Seaborn , Sklearn , xgboost , skopt

## Web scraping
Scraped over 40,000 hotels from each Booking.com and Expedia.com. With each hotel, we got the following:
*Hotel Name
*Number of night
*Room and Bed type
*Reviews
*Score,Ratings and Stars
*Center from distance
*Dates for : Snapshot , Checkin and Checkout
*TTT (Time To Travel)
*LOS (Length Of Stay)
*Price per night
*Total price

# Data Cleaning
After scraping the data , needed to clean and organize so that is be usable for our model. Made the following changes and created new variables : 
* Converted date data to represent only Day and Month in sperated columns
* Sorted Room and Bed type in numerical order.
* Used dummies for the locations.
* Removed $ sign.
* Removed any string value and converted to numerical.

# EDA for Booking.com

![alt text](https://github.com/TeveTc20/ds_hotel_pred_proj/blob/master/Images/booking_review_hist.png "Reviews histogram")
![alt text](https://github.com/TeveTc20/ds_hotel_pred_proj/blob/master/Images/booking_price_score.png "Price depending on score")
![alt text](https://github.com/TeveTc20/ds_hotel_pred_proj/blob/master/Images/booking_price_rating.png "Price depending on rating and stars")

# Model building for Booking.com
Tried six different models and evaluated them using R2 score.

# Booking.com Model performance
The XGBoost model far outperformed the other approaches on the test and valid sets.
* **Linear Regression-** R2 Score = 0.83
* **Decision Tree Regression-** R2 Score = 0.89
* **Gaussian Process Regressor-** R2 Score = 0.88
* **ElasticNet Regression-** R2 Score = 0.82
* **RandomForest Regression-** R2 Score = 0.91
* **XGBoost-** R2 Score = 0.93

# EDA for Expedia.com
![alt text](https://github.com/TeveTc20/ds_hotel_pred_proj/blob/master/Images/expedia_review_hist.png "Reviews histogram")
![alt text](https://github.com/TeveTc20/ds_hotel_pred_proj/blob/master/Images/expedia_price_score.png "Price depending on score")

# Model building for Expedia.com
Tried six different models and evaluated them using R2 score.

# Expedia.com Model performance
The XGBoost model far outperformed the other approaches on the test and valid sets.
* **Linear Regression-** R2 Score = 0.76
* **Decision Tree Regression-** R2 Score = 0.88
* **Gaussian Process Regressor-** R2 Score = 0.75
* **ElasticNet Regression-** R2 Score = 0.75
* **RandomForest Regression-** R2 Score = 0.9
* **XGBoost-** R2 Score = 0.97

# Exploring the difference between the websites

Searched hotels that appear in both websites and than comaperd and models to see which website is more expensive

![alt text](https://github.com/TeveTc20/ds_hotel_pred_proj/blob/master/Images/booking_expedia_price_dist.png "Price distribution")
![alt text](https://github.com/TeveTc20/ds_hotel_pred_proj/blob/master/Images/booking_expedia_price_diff_dist.png "Price difference distribution")

* **We can see that Expedia.com is often more expensive than Booking.com**

# Predicting differnce models performance
* **Linear Regression-** R2 Score = 0.56
* **Decision Tree Regression-** R2 Score = 0.8
* **Gaussian Process Regressor-** R2 Score = 0.78
* **ElasticNet Regression-** R2 Score = 0.75
* **RandomForest Regression-** R2 Score = 0.86
* **XGBoost-** R2 Score = 0.55
