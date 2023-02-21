## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Summary](#summary)
* [Files content](#files-content)


## General info
This is the second part of Forage virtual program created by British Airways.

In this task, using provided customer booking data (from Forage website), high-quality predictive model should be created.

## Technologies

In EDA phase, Pandas library was used to prepare data for the analysis.
Using inbuilt class feature_importances of tree based classifiers initial feature selection was made.
Next, features were analysed using the chi-squared (chi²) statistical test for non-negative features and correlation matrix with Heatmap was created.

To create models RandomForestClassifier and Autogluon TabularPredictor were used.

## Summary

To create random forest models 3 sets of features were created, to check best possible outcomes:

features_set_1 = ["purchase_lead", "length_of_stay", "flight_hour", "flight_duration", "flight_day", "num_passengers"]

features_set_2 = ["purchase_lead", "length_of_stay", "flight_hour", "flight_duration", "flight_day", "num_passengers", "wants_in_flight_meals", "wants_extra_baggage", "wants_preferred_seat"]

features_set_3 = ["length_of_stay", "purchase_lead", "flight_duration", "wants_preferred_seat", "wants_extra_baggage", "mobile_sale"]

Using Sklearn RandomForestClassifier for all 3 models score was the same:
0.85015


To compare the score with different models, Autogluon TabularPredictor model was created. The highest scores were

WeightedEnsemble_L2 - 0.85284
NeuralNetFastAI_BAG_L1 - 0.85050
CatBoost_BAG_L1 - 0.85044

# Files content

'Customer_booking_analysis_model.ipynb' - file includes EDA and created models

'Predicting customer buying behaviour BA - Task 2.pptx' - file includes short presentation which is short summary of what was done
