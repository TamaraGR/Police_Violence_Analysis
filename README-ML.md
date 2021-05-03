# Machine Learning Model

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


## Methodologies
### Data Preprocessing
The police violence data set was imported from AWS into a Pandas DataFrame.  The DataFrame originally contained XX columns and X,XXX rows of data.  
Include column names?

The column names were re-named and shortened so they were easier to work with.

Discuss any dropped columns - why were they dropped

The DataFrame was inspected for null values and any columns with X,000 or more null values were filled in with a variable.  The remaining columns had 70 or less null values.  The decision to fill in null values was made because if all rows with null values were dropped, it would significantly affect the data set.  The variables used to fill in null values were ones that were already found in the column.  The following columns were had null values replaced with a variable: Threat_Level, Fleeing, Body_Camera, Encounter_Type, Initia_Reason_for_Encounter, and Call_for_Service.

Null values for the age column were filled in the with mean average of ages for this column. <-- Still needs to be done... and is it even worth it for 8 null values?

The remaining columns that contained null values were dropped.

The data type for the Victim_Age column was converted from an object to an integer because of XYZ.

Additional columns from the Date column were created as they are vital to the analysis that will be conducted with this machine learning model.  New columns created include Day, Month, Year, Day_of_the_Week, and Holiday.


### Training and Testing Data Sets



### Preliminary Feature Engineering and Selection



### Model Choice
#### Limitations

#### Benefits