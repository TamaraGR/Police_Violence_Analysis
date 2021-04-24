# Final

## Overview
Supervised machine learning models were created with a sample of police violence data in order to better understand which model will fit into the overall project.


## Resources
- [Washington Post Police Shooting Data 2015-2021](https://github.com/washingtonpost/data-police-shootings)
- [fatal-police-shootings-data.csv](https://github.com/TamaraGR/Police_Violence_Analysis/tree/amanda/Resources)
- [Pandas Categorical Data](https://pandas.pydata.org/pandas-docs/stable/user_guide/categorical.html)
- [Seaborn Documentation](https://seaborn.pydata.org/introduction.html)
- [imbalanced-learn documentation](https://imbalanced-learn.org/stable/index.html)
- [scikit-learn documentation](https://scikit-learn.org/stable/supervised_learning.html)



## Dependencies
- Jupyter Notebook
- Python v3.x
    - Pandas
    - Numpy
    - Seaborn
    - Matplotlib
    - SciKit-Learn
    - Imbalanced-Learn


## Results
### Balanced Random Forest Classifier
The Balanced Random Forest Classifier is an ensemble method where each tree in the ensemble is built from a sample drawn with replacement (bootstrap sample) from the training set. Instead of using all the features, a random subset of features is selected, which further randomizes the tree. As a result, the bias of the forest increases slightly, but since the less correlated trees are averaged, its variance decreases, which results in an overall better model.

Once the data were balanced and trained, the balanced random forest algorithm gave the following scores:

![random_forest_scores](https://user-images.githubusercontent.com/73897240/115960650-ac94e200-a4e0-11eb-917e-25430f347e42.PNG)

Balanced Accuracy Score: 0.646

This algorithm's balanced accuracy score is 0.646, which means nearly 65% of class predictions were correct and 35% were incorrect.

Balanced Random Forest's average precision score of 0.74 means that this algorithm predicted positive class predictions 74% of the time on this dataset.

An average recall score of 0.62 means that 62% of class predictions made out of all positive examples in this dataset were correct, where as 38% were incorrect.


### Easy Ensemble AdaBoost Classifier
The Easy Ensemble AdaBoost Classifier combine multiple weak or low accuracy models to create a strong, accurate models. This algorithm uses one-level decision trees as weak learners that are added to the ensemble sequentially. This is an iterative process, so each subsequent model attempts to correct predictions made by the previous model in the sequence.

Once the data were balanced and trained, the Easy Ensemble AdaBoost Classifier algorithm gave the following scores:

![easy_ensemble](https://user-images.githubusercontent.com/73897240/115962132-e3bac180-a4e7-11eb-8fa2-3798bd7da80e.PNG)

Balanced Accuracy Score: 0.619

Easy Ensemble AdaBoost Classifier's accuracy score of 0.619 means that its predictions were correct nearly 62% of the time and 38% were incorrect.

This algorithm's precision score of 0.73 means that it predicted positive class predictions 73% of the time on this dataset.

The average recall score of 0.60 means that 60% of class predictions made out of all positive examples in this dataset were correct.

### Why this model was chosen
