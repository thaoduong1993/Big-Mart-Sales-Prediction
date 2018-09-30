# Big-Mart-Sales-Prediction
Predict sales per item at specific outlet (Analytics Vidhya)

This is another Analytics Vidhya competition that I finished. My first submision scored #5xx, and after a few changes, I was able to finish
at #251. There are a couple of things that I've learned from this challenge:

1. Impute missing values based on relationship with other variables:
Instead of taking the mean or mode of the entire data set, I can impute the outlet_size with the mode of outlet_size per outlet_type.

2. Handle mislabled categorical data:
In case of categorical variables, the input values can be mislabled. For example, in this data set, the fat content is labeled as Low Fat,
Regular, LF, reg, low fat. Therefore, we need to fix the values before doing any further analysis.

3. Do the values make sense:
This requires me to look at the data more closely, and realize a subtle pattern that non-consumable products cannot have fat content, or
any product should have some sort of visibility, instead of zero. Hence, I've created new values for fat content "NONE" for non-consumable
products, as well as imputed visibility values based on the mean visibility of an item at an outlet.

4. Use grid-search to tune the models:
Honestly, I still have limited experience in tuning the parameters for a model. Therefore, gridsearch is an option to return the best model
after trying different parameters. While this takes time, it really improves my prediction.

5. Explain black-box random forest:
While random forest is generally known as a black-box algorithm, with little interpretations on how the model can be used to optimize the resul,
which in this case is to increase sales. However, by using visualization (pre-analysis) and important features, I was able to point out 
which variables are most meaningful to predict the sales of a product. Furthermore, when I simplified the model with only top 4 most important
variables, I've achieved the best model with lowest RMSE on the test set.
