# Predicting the size of U.S. wildfires based on meteorological factors

## Background
This project was developed for Module 7 of the course *Introduction to Machine Learning: Supervised Learning* (DTSA-5509) at University of Colorado Boulder. It was inspired by the paper [A data mining approach to predict forest fires using meteorological data](https://core.ac.uk/works/9801673/), which uses machine-learning models, with very limited success, to predict the size of wildfires in a region of Portugal, based on meteorological factors.

## Description
The project employs machine-learning models to predict the size of wildfires in the United States based on meteorological factors. (The factors in the dataset are different from those in the Portuguese study mentioned above.)

## Key Features:
* **Feature Engineering**: Uses **backwards stepwise elimination** to select relevant features from meteorological variables, such as temperature, humidity, wind speed, and precipitation.
* **Model Development**: Explores and compares four different kinds of models: **Linear Regression, Support-Vector Regression (SVR), Random Forest**, and a **Feed-Forward Neural Network**.
* **Model Evaluation**: Assesses model accuracy using **Mean Absolute Error (MAE), Root Mean Squared error (RMSE)**, and **Mean Absolute Percentage Error (MAPE)**, and compares them to naive basemarks based on both the mean and median fire sizes, as well as "semi-naive" benchmarks which take the month of the year, but no meteorological factors, into consideration.
* **Visualization**: Visualizes the model performance with **Receiver Error Characteristic (REC)** curves (an analog to ROC curves adopted to regression tasks).

## Results
The best model, based on the Mean Absolute Percentage Error (MAPE) was the Support Vector Regression (SVR), which performed much better than the mean-based naive and semi-naive benchmarks on all metrics. This is better than the model in the Portuguese study mentioned above, which performed worse than a mean-based naive benchmark when evaluated on RMSE. However, the current model does not perform better than median-based naive and semi-naive benchmarks, and has thus limited value. Further work would be needed to find a model with better predictive power.

![SVR compared with benchmarks](https://github.com/user-attachments/assets/1b52a806-b98f-4140-ad8e-1fb5a534f094)

## Conclusion
The results were somewhat disappointing. While the model performs better than the one presented in the Portuguese study, it still does not have much value, since it does not outperform a naive median-based benchmark. The difficulty in beating the naive median-based benchmark has to do with the extreme skew of the data. A majority of the fires are very small. (Almost 70% are smaller than 5 hectares.) This means that if we had a model that for any fire, regardless of the predictors, just guessed "I'm sure it will be very small!", then that model would usually be right. And that 
is basically what the median-based benchmarks do.
