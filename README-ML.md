# Machine Learning Model

## Overview
Supervised machine learning models were created with a sample of police violence data in order to better understand which model will fit into the overall project.  The goal of the model is to predict what activities will most likely lead to the victim getting killed.


## Resources
- [scikit-learn documentation](https://scikit-learn.org/stable/supervised_learning.html)


## Dependencies
- Jupyter Notebook
- Python v3.x
    - Pandas
    - Numpy
    - SciKit-Learn
    - SQLAlchemy
    - MySQL
    - JSON
    - Pyscopg2


## Methodologies
### Data Preprocessing
The police violence data set was imported from AWS into a Pandas DataFrame.  The DataFrame originally contained 20 columns and 9,082 rows of data. Column names include: Victim_Age, Victim_Gender, Victim_Race, Date, City, State, County, Responsible_Agency, Cause_of_Death, Brief_Description, Criminal_Charges, Mental_Illness, Armed_Status, Threat_Level, Fleeing, Body_Camera, Geography, Encounter_Type, Initial_Reason_for_Encounter, and Call_for_Service.

Victim_Gender, City, State, Criminal_Charges, and Brief_Description were dropped since they were not going to be used in the model prediction.  

The DataFrame was inspected for null values and any columns with 2,000 or more null values were filled in with a variable. The decision to fill in null values was made because if all rows with null values were dropped, it would significantly affect the data set.  The variables used to fill in null values were ones that were already found in the column.  The following columns were had null values replaced with a variable: Threat_Level, Fleeing, Body_Camera, Encounter_Type, Initia_Reason_for_Encounter, and Call_for_Service.     

Columns that contained 70 or less null values had their rows dropped.

The data type for the Victim_Age column was converted from an object to an integer because this feature needed to be an integer.

Additional columns from the Date column were created.  New columns created include Day, Month, Year, Day_of_the_Week, and Holiday.  This data may be used to predict when some is more likely to be killed by law enforcement.  The Date column was dropped because it was no longer needed once Day, Month, Year, Day_of_the_Week, and Holiday were extracted from it.

Counts of Victim_Race were also calculated:

![race_counts](https://user-images.githubusercontent.com/73897240/117447022-f3380280-af0a-11eb-8987-1000ce3abab3.PNG)

Lastly, the Victim_Race values were converted to numbers:

![race_conversion](https://user-images.githubusercontent.com/73897240/117447188-2b3f4580-af0b-11eb-970c-a33db8369b45.PNG)


### Training and Testing Data Sets
Data was trained and tested on police_killings database that was stored in AWS.  This database was comprised of data from The Washington Post and Kaggle.

The AWS police_killings database was split into a training and testing data set.  The training data set was made up of 8 rows and 5,995 columns.  This will be the data the model learns from.

The test data set consists of the remaining data and will be used to assess the model's performance.


### Preliminary Feature Engineering and Selection
The following columns were transformed into numerical values using the get_dummies method: Cause_of_Death, Mental_Illness, Armed_Status, Threat_Level, Fleeing, Body_Camera, Geography, County, Responsible_Agency, Encounter_Type, Intitial_Reason_for_Encounter, and Call_for_Service.  These will were the features the model trained on.

The column Victim_Race was dropped because this is the target variable that will be used to predict the outcome.


### Model Choice
Random Forest, Decision Tree, and Logistic Regression models were tested.  Note that none of the models were optimized at this time.  Results below are of the initial test of the model.


#### Random Forest
Random Forest is a supervised machine learning algorithm that creates decision trees on randomly selected data samples, gets predictions from each tree and selects the best solution by means of voting.  The prediction result with the most votes is selected as the final prediction.  

Random Forest gave the following scores:

Receiver Operator Characteristic — Area Under the Curve (ROC AUC) score:
0.561

![rf_class_report](https://user-images.githubusercontent.com/73897240/117449016-75c1c180-af0d-11eb-92cd-88cf1de22766.PNG)

The ROC AUC score for this model means that 56.1% of classes are correct and 43.9% are incorrect.

An average precision score of 0.53 means that this model predicted positive class predictions 53% of the time.

An average recall score of 0.53 means that 53% of class predictions made out of all positive examples in the dataset were correct and 47% were incorrect.


#### Decision Tree


#### Limitations
- Random Forest requires a lot of time and computational power.  The large number of trees can make the algorithm too slow and ineffective for real-time predictions. A more accurate prediction requires more trees, which results in a slower model. 
- Due to the ensemble of decision trees, it can suffer interpretability and fails to determine the significance of each variable.

#### Benefits
- Random Forest prevents overfitting by creating trees on random subset.
- Random forest adds additional randomness to the model, while growing the trees. Instead of searching for the most important feature while splitting a node, it searches for the best feature among a random subset of features. This results in a wide diversity that generally results in a better model.
- It automates missing values present in the data.
- Normalising of data is not required as it uses a rule-based approach.
