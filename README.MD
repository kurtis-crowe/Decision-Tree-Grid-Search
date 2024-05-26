# Decision Tree Classifier and Hyperparameter Tuning

## Project Overview

The main purpose of this assignment is to gain experience creating and visualizing a Decision Tree along with sweeping a problem's parameter space by performing a grid search. This process allows the identification of the optimal hyperparameter values to be used for training your model.

## Key Objectives

### Create a Single Decision Tree

1. Import the `DecisionTreeClassifier` class from the `sklearn.tree` library.
2. Create a `DecisionTreeClassifier` object called `tree_clf` with a `random_state` of `42`.
3. Fit the `DecisionTreeClassifier` object on the training data.
4. Make a prediction on the test data, and name the predicted values output by the model `preds`.
5. Compute the performance of the model by measuring the accuracy score on the test set. You must import the [accuracy_score()](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.accuracy_score.html) function from the `sklearn.metrics` library. Name the accuracy score value you compute `acc_score`.
6. Print the accuracy score to the screen.

### Perform Grid Search

1. Import the `GridSearchCV` class from the `sklearn.model_selection` library.
2. Create a dictionary called `param_grid` with three key-value pairs. The keys are `max_depth`, `max_leaf_nodes`, and `min_samples_split`, and their respective values are `[2, 3, 4, 5, 8, 16, 32]`, `list(range(2, 20, 1))`, and `[2, 3, 4, 5, 8, 12, 16, 20]`.
3. Instantiate an object of the `GridSearchCV` class called `grid_search_cv`. Pass the following as input to the constructor:
   - The model to be used: a `DecisionTreeClassifier` with a `random_state` parameter of `42`.
   - The parameter grid.
   - The hyperparameter `verbose=1`.
   - The number of cross-folds: `cv=3`.
4. Call the `fit()` method to perform the grid search using 3-fold cross-validation.
5. Print the best parameters identified by the grid search using the `best_params_` attribute of the GridSearchCV object.
6. Compute the predicted values `y_pred` using the test set `X_test`.
7. Calculate the accuracy, precision, and recall scores using the `accuracy_score()`, `precision_score()`, and `recall_score()` functions. Call these `acc_score`, `prec_score`, and `recall_score`, respectively. Set the average parameter to `micro` when calculating precision and recall to account for multiple classes.
8. Print all three scores to the screen.

### Visualize Optimal Decision Tree

1. Instantiate a new `DecisionTreeClassifier` object, and use the `best_params_` attribute of the `grid_search_cv` object to specify the best `max_depth`, `max_leaf_nodes`, and `min_samples_split` values calculated from the grid search along with a `random_state` of `42`.
2. Retrain the "optimal" decision tree.
3. Use the [tree.export_text()](https://scikit-learn.org/stable/modules/generated/sklearn.tree.export_text.html) method to visualize the "optimal" decision tree. This function takes a trained classifier as its first parameter, and a set of feature names as its second parameter (the feature names are included in the `iris` dictionary returned from the `load_iris()` function). The result is a text-based visualization of the decision tree. Note that this method returns a string, so you'll want to `print()` the result to get it to look right.
4. Use the `tree.plot_tree()` method to visualize the "optimal" decision tree, which takes a trained classifier as its only parameter and returns a graphical visualization of the decision tree. Use `filled=True` as an argument to the method to add color to the image.

### Critical Analysis

1. In your own words (a sentence or two), explain what setting the GridSearchCV hyperparameter `verbose` to `1` does. Please provide a citation. (A link to the website or the name of the book where you found this answer will suffice.)
2. In your own words, describe or interpret the role of the Gini score criterion in the decision tree algorithm. How does this compare to the entropy impurity measure? Finally, sklearn uses the CART (Classification and Regression Tree) algorithm to train Decision Trees. How does this algorithm determine the feature and threshold value to use for splitting at each step of the Decision Tree algorithm? It may be helpful to look at outside resources to help you answer these questions (The YouTube channel ["StatQuest"](https://youtu.be/7VeUPuFGJHk) has some excellent videos on Decision Trees for those of you that like visual explanations.)

Make sure that you answer all the questions above. I am looking for **meaningful content** here that **goes into detail**. Don't just copy from the textbook or rush through answering this question.

## Learning Outcomes

- Gain practical experience with Decision Tree classifiers.
- Develop an understanding of hyperparameter tuning and grid search techniques.
- Learn to visualize and interpret Decision Trees both textually and graphically.
- Enhance critical thinking about model performance and decision tree algorithms.
