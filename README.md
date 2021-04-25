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


## Results - Race
### Balanced Random Forest Classifier
The Balanced Random Forest Classifier is an ensemble method where each tree in the ensemble is built from a sample drawn with replacement (bootstrap sample) from the training set. Instead of using all the features, a random subset of features is selected, which further randomizes the tree. As a result, the bias of the forest increases slightly, but since the less correlated trees are averaged, its variance decreases, which results in an overall better model.

Once the data were balanced and trained, the balanced random forest algorithm gave the following scores:

![random_forest_scores](https://user-images.githubusercontent.com/73897240/115964224-65631d00-a4f1-11eb-8220-66d26f830100.PNG)

Balanced Accuracy Score: 0.292

This algorithm's balanced accuracy score is 0.292, which means only 29% of class predictions were correct and 71% were incorrect.

Balanced Random Forest's average precision score of 0.47 means that this algorithm predicted positive class predictions 47% of the time on this dataset.

An average recall score of 0.26 means that 26% of class predictions made out of all positive examples in this dataset were correct, whereas 74% were incorrect.

#### Prediction:
The Balanced Random Forest Classifier predicted the following races as having the highest incidences of police-related violence:

![rf_pred](https://user-images.githubusercontent.com/73897240/116002684-e3debe00-a5c8-11eb-8ac4-b7a66bc94558.PNG)



### Easy Ensemble AdaBoost Classifier
The Easy Ensemble AdaBoost Classifier combine multiple weak or low accuracy models to create a strong, accurate models. This algorithm uses one-level decision trees as weak learners that are added to the ensemble sequentially. This is an iterative process, so each subsequent model attempts to correct predictions made by the previous model in the sequence.

Once the data were balanced and trained, the Easy Ensemble AdaBoost Classifier algorithm gave the following scores:

![easy_ensemble_scores](https://user-images.githubusercontent.com/73897240/115965431-410a3f00-a4f7-11eb-8898-3b980d20e2a7.PNG)

Balanced Accuracy Score: 0.271

Easy Ensemble AdaBoost Classifier's accuracy score of 0.271 means that its predictions were correct only 27% of the time and 73% were incorrect.

This algorithm's precision score of 0.49 means that it predicted positive class predictions 49% of the time on this dataset.

The average recall score of 0.33 means that 33% of class predictions made out of all positive examples in this dataset were correct.

#### Prediction:
The Easy Ensemble AdaBoost Classifier predicted the following races as having the highest incidences of police-related violence:

![ee_pred](https://user-images.githubusercontent.com/73897240/116002626-aa0db780-a5c8-11eb-9711-8125bc0355d8.PNG)


### Why this model was chosen
The team will continue to conduct additional testing and evaluation on machine learning models before deciding on a model.  Models that will be tested include Decision Tree, Random Forest, and Support Vector Classifier (SVC).
