# Objective

Getting familiar with regression problems, basic data processing and modeling techniques such as feature scaling, dimensionality reduction, Random Forest, K-fold cross-validation, data balancing, evaluating model performance, and MLFlow logging.

# Steps
1. **Start a Jupyter notebook container and link it to your MLFlow container.**
2. **Load the diabetes dataset from sklearn.**
3. **Data Pre-processing: Dimensionality Reduction to avoid multicollinearity.** Try both:
   - Taking PCA components of the features (minimum variance 0.7/0.8).
   - Dropping the highly correlated features (if three features have high correlation, then two are dropped and one is kept).
4. **Set up K-fold cross-validation training with proper stratification** (use the binned target variable to ensure the ratio of all bins is the same in the training and test set). Decide bins based on min, max values, and problem statement.
5. **For every fold’s train and test sets, perform additional processing:**
   - Fit feature scaler to training features and use it to transform the testing features.
   - Fit target values scaler to training target values and use it to transform the testing target values.
   - Balance the dataset according to binned target values. Try both:
     - Oversampling: resample the minority bins.
     - Undersampling: undersample the majority bins.
6. **Initialize a Random Forest regressor for each fold, fit on the training set, and predict on the test set.**
7. **Calculate regression performance metrics on the test set results:**
   - MSE
   - RMSE
   - MAE
   - MAPE
   - R²
   - Adjusted R²
   - Pearson R
   - Spearman R
   - Accuracy within a certain range (±5/10/15/20)
   - Plot real vs predicted values (show density of points as well)
8. **Store all the test set predictions and their real values.**
9. **Combine test sets from all folds to have test set predictions for the entire dataset** and calculate the final regression metrics on this combined set.
