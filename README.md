# Police Violence and Racial Equity Analysis

![link](https://images.squarespace-cdn.com/content/v1/55ad38b1e4b0185f0285195f/1593639080742-I0422XS5N9K41NTO3LUL/ke17ZwdGBToddI8pDm48kPTrHXgsMrSIMwe6YW3w1AZ7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z4YTzHvnKhyp6Da-NYroOW3ZGjoBKy3azqku80C789l0k5fwC0WRNFJBIXiBeNI5fKTrY37saURwPBw8fO2esROAxn-RKSrlQamlL27g22X2A/accountable.jpg?format=2500w)

## Introduction 

From Rodney King to Trayvon Martin to Ma'Khia Bryant: the police violence against civilians in the United States is a fact, a significant socio-political challenge and a major human tragedy. In 2020, when one of the four police officers at the scene murdered a black American man George Floyd by kneeling on his neck for 9 minutes and 29 seconds, Floyd's last words 'I can't breath' became a slogan that lead to mass uprising in the US and across the world. Yet, since the arrest of his murderer Derek Chauvin, at least 3 people were [killed by the police](https://www.nytimes.com/2021/04/17/us/police-shootings-killings.html) every day. 

This project intends to analyze police violence (while police violence can be interpeted in various ways, in this instance we are recording only fatal for the civilians encounters with the law enforcement) across the United States in 2013-2020, detect the states where the police is more prone to violence and analyze whether there is racial and/ or other bias in violent police behavior. The project is also looking to compare the budgets of the police departments in the states where police violence is at highest. Among other things the project is looking at: correlation between the age of the victims and whether they attempted to flee the scene; comparisons between US population by race and US police victims by race. For a brief project review, refer to the project presentation [slides](https://spark.adobe.com/page/XI73Ev5wjTeE3/). For a more detailed outline continue reading below. 

## Project Team 

[Amanda Thomson](https://www.linkedin.com/in/acfthomson/)

[Nigel Rowser](https://www.linkedin.com/in/nigelrowser/)

[Shivam Mittal](https://www.linkedin.com/in/shivammittalbi/)

[Tamara Grigoryeva](https://www.linkedin.com/in/tamaragrigoryeva/)


## Questions 

The project research is focused around the following questions: 

#### - [x] MAIN QUESTION: IS THERE RACIAL BIAS IN POLICE VIOLENCE IN THE US? 

##### SUPPORTING QUESTIONS: 
- [x] WHAT ARE THE TOP STATES/ COUNTIES FOR POLICE VIOLENCE IN 2013-2020?
- [x] WHAT IS THE DEATHS BREAKDOWN BY RACE VS. COUNTRY POPULATION BY RACE?
- [x] IS THERE A CORRELATION BETWEEN THR AGE OF TH VICTIM AND WHETHER THEY FLED?
- [x] WHAT ARE THE POLICE DEPARTMENTS' BUDGETS?
- [x] CAN POLICE VIOLENCE IN THE US BE PREDICTED BASED ON FACTORS SUCH AS RACE? 


![link](https://i.guim.co.uk/img/media/fd398259625476ea51106180ab608f1f55d1b7e4/0_306_5344_3207/master/5344.jpg?width=465&quality=45&auto=format&fit=max&dpr=2&s=993b25ee7d5bf9bb4568e8b5a08e55d8)

## Resources 

The project has used the [Police Killings in 2013-2020 dataset](https://github.com/TamaraGR/Police_Violence_Analysis/blob/main/Resources/Datasets/2013-2020_Police_Killings_Revised%20(3).xlsx) as the main resource. Below are some of the supporting datasets that the project has also leaned on:

- [x] [Police Stations/ Departments Budgets](https://github.com/TamaraGR/Police_Violence_Analysis/blob/database/City_Budget.csv)
- [x] [Washington Post Police Shooting Data 2015-2021](https://github.com/washingtonpost/data-police-shootings)
- [x] [Kaggle Datasets on Police Violence and racial Equity](https://www.kaggle.com/jpmiller/police-violence-in-the-us)

The project has used the following documentation tools:

- [x] [Pandas Categorical Data](https://pandas.pydata.org/pandas-docs/stable/user_guide/categorical.html)
- [x] [Seaborn Documentation](https://seaborn.pydata.org/introduction.html)
- [x] [imbalanced-learn documentation](https://imbalanced-learn.org/stable/index.html)
- [x] [scikit-learn documentation](https://scikit-learn.org/stable/supervised_learning.html)

#### Dependencies
- [x] Jupyter Notebook
- [x] Python v3.x
- [x] Pandas
- [x] Numpy
- [x] Seaborn
- [x] Matplotlib
- [x] SciKit-Learn
- [x] Imbalanced-Learn
- [x] SQLAlchemy
- [x] MySQL
- [x] JSON
- [x] Pyscopg2

## Technology at use 

- [x] Database: The project used Postgres SQL and Python Pandas were used to load, clean and analyze the data (for data loading documentation refer [here](https://github.com/TamaraGR/Police_Violence_Analysis/blob/main/Resources/Supporting%20Documents/Police_Violence_Analysis-database%20(2).zip), including the ERD.  
- [x] Host Instance: The project data is stored in AWS RDS. 
- [x] Machine Learning (Python): The project used SciKitLearn to create and test the machine learning (ML) model. THe ML model is testing a predictive statistic (For further details please refer [here](https://github.com/TamaraGR/Police_Violence_Analysis/blob/machine_learning/Police_Violence_Clean.ipynb)).
- [x] Visualization: The project used visuals from the ML analysis as well as Tableau to visualize the analysis. Data is visualized in a simplified manner for all stakeholders to be able to access the validity of it. Data is presented in a story format (To review the dashboard in Tableau please refer [here](https://public.tableau.com/profile/shivam.mittal2652#!/vizhome/PoliceVoliencemockups/PoliceVolience)). 

## Data Exploration and Analysis

To answer the listed above questions the project team reviewed the datasets listed previously, selected the main and the supporting datasets, and worked on cleaning and analyzing them. The main dataset was preprocessed and analyzed in order to test a few ML models and to select the most appropriate one. The supporting datasets helped inform and complete the visual analysis that was performed in Tableau. 

## ML Model Testing and Selection 

#### Data Preprocessing

The police violence data set was imported from AWS into a Pandas DataFrame.  The DataFrame originally contained 20 columns and 9,082 rows of data. Column names include: Victim_Age, Victim_Gender, Victim_Race, Date, City, State, County, Responsible_Agency, Cause_of_Death, Brief_Description, Criminal_Charges, Mental_Illness, Armed_Status, Threat_Level, Fleeing, Body_Camera, Geography, Encounter_Type, Initial_Reason_for_Encounter, and Call_for_Service.

Victim_Gender, City, State, Criminal_Charges, and Brief_Description were dropped since they were not going to be used in the model prediction.  

The DataFrame was inspected for null values and any columns with 2,000 or more null values were filled in with a variable. The decision to fill in null values was made because if all rows with null values were dropped, it would significantly affect the data set.  The variables used to fill in null values were ones that were already found in the column.  The following columns were had null values replaced with a variable: Threat_Level, Fleeing, Body_Camera, Encounter_Type, Initia_Reason_for_Encounter, and Call_for_Service.     

Columns that contained 70 or less null values had their rows dropped.

The data type for the Victim_Age column was converted from an object to an integer because this feature needed to be an integer.

Additional columns from the Date column were created.  New columns created include Day, Month, Year, Day_of_the_Week, and Holiday.  This data may be used to predict when some is more likely to be killed by law enforcement.  The Date column was dropped because it was no longer needed once Day, Month, Year, Day_of_the_Week, and Holiday were extracted from it.

Counts of Victim_Race were also calculated:

![race_counts](https://github.com/TamaraGR/Police_Violence_Analysis/blob/main/Resources/Images/1.png)

Lastly, the Victim_Race values were converted to numbers:

![race_conversion](https://github.com/TamaraGR/Police_Violence_Analysis/blob/main/Resources/Images/2.png)

#### Training and Testing the Datasets

Data was trained and tested on police_killings database that was stored in AWS.  This database was comprised of data from The Washington Post and Kaggle.

The AWS police_killings database was split into a training and testing data set.  The training data set was made up of 8 rows and 5,995 columns.  This will be the data the model learns from.

The test data set consists of the remaining data and will be used to assess the model's performance.

#### Preliminary Feature Engineering and Selection

The following columns were transformed into numerical values using the get_dummies method: Cause_of_Death, Mental_Illness, Armed_Status, Threat_Level, Fleeing, Body_Camera, Geography, County, Responsible_Agency, Encounter_Type, Intitial_Reason_for_Encounter, and Call_for_Service.  These will were the features the model trained on.

The column Victim_Race was dropped because this is the target variable that will be used to predict the outcome.

#### Model Choice
Random Forest, Decision Tree, and Logistic Regression models were tested.  Note that none of the models were optimized at this time.  Overall, all three models performed relatively the same, but future progress on this model will use Random Forest.  Results below are of the initial tests of the models.

##### Random Forest
Random Forest is a supervised machine learning algorithm that creates decision trees on randomly selected data samples, gets predictions from each tree and selects the best solution by means of voting.  The prediction result with the most votes is selected as the final prediction.  

Random Forest gave the following scores:

Receiver Operator Characteristic — Area Under the Curve (ROC AUC) score:
0.565

![rf_class_report](https://github.com/TamaraGR/Police_Violence_Analysis/blob/main/Resources/Images/3.png)

The ROC AUC score for this model means that 56.5% of classes are correct and 43.5% are incorrect.

An average precision score of 0.53 means that this model predicted positive class predictions 53% of the time.

An average recall score of 0.53 means that 53% of class predictions made out of all positive examples in the dataset were correct and 47% were incorrect.

##### Decision Tree
Decision Tree is another supervised machine learning algorithm that can make predictions by learning simple decision rules inferred from test data.

Decision Tree gave the following scores:
ROC AUC: 0.561

![dt_class_report](https://github.com/TamaraGR/Police_Violence_Analysis/blob/main/Resources/Images/4.png)

The ROC AUC score for this model means that 56.1% of classes are correct and 43.9% are incorrect.

An average precision score of 0.53 means that this model predicted positive class predictions 53% of the time.

An average recall score of 0.53 means that 53% of class predictions made out of all positive examples in the dataset were correct and 47% were incorrect.

##### Logistic Regression
Logisitc Regression is a supervised machine learning algorithm that is used to assign observations to a discrete set of classes.

Logistic Regression gave the following scores:
ROC AUC: 0.516

![logreg_class_report](https://github.com/TamaraGR/Police_Violence_Analysis/blob/main/Resources/Images/5.png)

The ROC AUC score for this model means that 51.6% of classes are correct and 48.4% are incorrect.

An average precision score of 0.30 means that this model predicited positive class predictions 30% of the time.

An average recall score of 0.46 means that 46% of class predicitions made out of all positive examples in the dataset were correct and 54% were incorrect.

##### Random Forest Limitations
- Random Forest requires a lot of time and computational power.  The large number of trees can make the algorithm too slow and ineffective for real-time predictions. A more accurate prediction requires more trees, which results in a slower model. 
- Due to the ensemble of decision trees, it can suffer interpretability and fails to determine the significance of each variable.

##### Random Forest Benefits
- Random Forest prevents overfitting by creating trees on random subset.
- Random forest adds additional randomness to the model, while growing the trees. Instead of searching for the most important feature while splitting a node, it searches for the best feature among a random subset of features. This results in a wide diversity that generally results in a better model.
- It automates missing values present in the data.
- Normalising of data is not required as it uses a rule-based approach.

## Project Visualization

To acces the project visualization proceed to Tableau [here](https://public.tableau.com/profile/shivam.mittal2652#!/vizhome/PoliceVoliencemockups/PoliceVolience) or refer to the below screenshot ![screenshot](https://github.com/TamaraGR/Police_Violence_Analysis/blob/main/Resources/Images/screenshot.png). 

The top image is from a 2020 protest to the police killings in California. The top image also states the goal of the project. The image to the right of it is a heat map with interactive features. The map allows the viewer pick top 10,20,30,40 or 50 states with highest police violence rate between 2013-2020. When hovering over the map one can also see the city, county and the number of the police victims. 

The second row of infographics is two doughnut charts representing the compariosn between the US police violence victims by race and the overall US population breakdown by race. When hovering over the chart one can see the percentage of police killings for that group of population. One can also use another filter here to narrow down their search by year and month. To the right from the doughnut charts the viewer can also see a barchart that portrays the correlation between US police victims' age and whether they attempted to flee the scene. Underneath these charts one can see a breakdown of police stations/ departments' budgets in 2013-2017. In this chart the viewer can filter by year to see the changes in the budgets. 

The project plans to add additional visualizations from the ML analysis to this dashboard. 

## Data Limitations and Considerations for Project's Future Steps

The datasets don't differentiate between civilian victims that were killed at a crime scene and during random encounters with the police (such as during a routine traffic stop). The budgets dataset only goes until 2017, therefore the project team cannot perform the correlation analysis for the 2017-2020 years between the killings and the budgets. 

As some of the post-bootcamp steps the project considers to compare the US police stations data in terms of budgets, training and arming/ disarming the police officers with other countries, including those countries where the police don't carry arms.

![image](https://www.worldatlas.com/r/w768/upload/f8/83/89/shutterstock-1078746002.jpg)

## Conclusion 

- [x] Phoenix, AZ is the state with the most number of police killing. Phoenix has a black population of 6.5% but 15% of police killing were black.
- [x] From 2013-2020, 25% the victims of police killings where black. This number isn't consistent with the overall population of blacks in the US.
- [x] Based on the total amount police killings 43% of victims weren’t fleeing, 32% of victims were unknown, 11% fled by car, 9% fled on foot, and 5% used other methods. Age isn’t a factor because ‘not fleeing’ and ‘unknown’ have the highest percentage in almost all age ranges.
- [x] There is no clear correlation between police department budgets and the amount of police killings. Los Angeles, CA and Phoenix, AZ had 125 and 131 police killings respectfully. Los Angeles had a budget that was $271.77 million more.

