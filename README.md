# Corporate Default Model: Team Turquoise

Predicting the probability of default

# Preprocessor

1. The function in preprocessor.py inputs a pandas DataFrame, processes it by calculating ratios, handling NaN's and infinities and returns a new dataframe that could be used for prediction.
2. This function can be used to process both training and testing process by the parameter isTraining.

# Prediction
1. The function in prediction.py inputs String value of the paths for test data, model and output file.
2. The function imports the model from pickle and predicts PD on the test set, calibrates the output and saves it in output path.


# Harness
1. This function is the entry point for execution. The CLI command mentioned in the project announcements works with this function.

# ChangeLog
1. Although the preprocessor was loaded with medians of ratios and transformations from the training data to transform the test data, we overlooked the clipping part. We were clipping the outliers of the ratios we created based on quantiles, and we did not hardcode the values of the training data for this. During harness run, it was clipping the test data. However, we identified and changed it now. The changes are in the preprocessor.py on lines 214 and 232. 
