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

Additional columns from the Date column were created.  New columns created include Day, Month, Year, Day_of_the_Week, and Holiday.  THis data may be used to predict when some is more likely to be killed by law enforcement.


### Training and Testing Data Sets
Data was trained and tested on police_killings database that was stored in AWS.  This database was comprised of data from the Washington Post and Kaggle.

The following columns were transformed into numerical values using the get_dummies method: Cause_of_Death, Mental_Illness, Armed_Status, Threat_Level, Fleeing, Body_Camera, Geography, County, Responsible_Agency, Encounter_Type, Intitial_Reason_for_Encounter, and Call_for_Service.  These will were the features the model trained on.



### Preliminary Feature Engineering and Selection



### Model Choice
Testing and evaluation of models is continuing.  To date, three different models were tested.  Note that none of the models were optimized at this time.  Results below are of the initial test of the model.

#### Random Forest Model
Random Forest is a supervised machine learning algorithm that creates decision trees on randomly selected data samples, gets predictions from each tree and selects the best solution by means of voting.  The prediction result with the most votes is selected as the final prediction.  

Once the test data set was trained, the Random Forest algorithm gave the following scores:

Balanced Accuracy Score:

#### Limitations

#### Benefits
