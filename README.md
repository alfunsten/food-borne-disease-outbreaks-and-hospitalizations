# Food-borne Disease Outbreaks and Hospitalizations


## Contents
 - [Problem Statement](#Problem-Statement)
 - [Executive Summary](#Executive-Summary)
 - [Data](#Data)
 - [Data Dictionary](#Data-Dictionary)
 - [Conclusions and Recommendations](#Conclusions-and-Recommendations)
 - [Limitations and Areas for Further Research](#Limitations_and_Areas-for-Further-Research)
 - [Sources](#Sources)



## Problem Statement
[back to top](#Food-borne-Disease-Outbreaks-and-Hospitalizations)

Based on food-borne disease outbreak data from the CDC, what features of the outbreak are likely to cause hospitalizations?

## Executive Summary
[back to top](#Food-borne-Disease-Outbreaks-and-Hospitalizations)

After evaluating food-borne illness 1998-2015 data from the CDC, it is apparent that there are specific factors that can increase your likelihood of being hospitalized after contracting a food-borne illness. This analysis takes a deeper look into what factors might increase the likelihood of an individual being hospitalized for a food-borne illness and also looks at multiple classification models to predict hospitalization risk. Logistic Regression, Naive Bayes, KNN Classifier, and Decision Tree Classifier models were all used to evaluate likelihood of hospitalization after a food-borne illness outbreak. 

## Data
[back to top](#Food-borne-Disease-Outbreaks-and-Hospitalizations)

Data downloaded from kaggle with reference to CDC food-borne disease outbreak data from 1998-2015

## Data Dictionary
[back to top](#Food-borne-Disease-Outbreaks-and-Hospitalizations)

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**Year**|*int64*|clean_df|year of outbreak|
|**Month**|*object*|clean_df|month of outbreak|
|**State**|*object*|clean_df|state outbreak occurred|
|**Location**|*object*|clean_df|location of outbreak|
|**Food**|*object*|clean_df|food that caused outbreak|
|**Species**|*object*|clean_df|species of pathogen that caused outbreak|
|**Illlnesses**|*int64*|clean_df|number of people sick from outbreak|
|**Hospitalizations**|*float64*|clean_df|number of hospitalizations from outbreak|
|**Fatalities**|*float64*|clean_df|number of fatalities from outbreak|


## Conclusions and Recommendations
[back to top](#Food-borne-Disease-Outbreaks-and-Hospitalizations)

After evaluating Logistic Regression, Naive Bayes, KNN Classifier, and Decision Tree Classifier models, both a simple logistic regression model and a slightly more complex Decision Tree Classifier presented the best scores when looking at f1 and false negative rates. 

The simple logistic regression model performed the best and used species and number of illnesses in the outbreak as features and produced the highest f1 score of 0.71 and lowest false negtive rate at 0.33. Highest coef with simple logistic regression model are illnesses, Species_Salmonella enterica and Species_Escherichia coli, Shiga toxin-producing showing that these features would increase likelihood of hospitalizations. Lowest coef Species_Heavy metals, Species_Norovirus genogroup II,  Species_Bacterium would decrease probability of hospitalizations.

The second best model was Decision Tree Classifier which used State, Location, Food, Species, Illnesses as features and produced a false negative score of 0.395 and f1 score of 0.68. Features ranked with the greatest importance in this model are Species_Salmonella enterica, Species_Escherichia coli, Shiga toxin-producing, Illnesses, location being restaurant, state of Utah also ranked high on feature importance and Food_Pork, Roasted ranked high on feature importance to predict likelihood of hospitalization.

Based on this analysis, I would pay attention to the number of illnesses an outbreak has, the species of Species_Salmonella enterica and Species_Escherichia coli, Shiga toxin-producing, and the location of the outbreak being a restaurant setting since these factors appear to increase the likelihood of hospitalization. 

## Limitations and Areas for Further Research
[back to top](#Food-borne-Disease-Outbreaks-and-Hospitalizations)

The data was slightly imbalanced with 0.640498 of the data having cases that were not hospitalized and 0.359502 with cases that were hospitalized. In the future, it would be useful to create models addressing imbalanced data and also looking at some other classification models such as random forest and extra trees.

## Sources
[back to top](#Food-borne-Disease-Outbreaks-and-Hospitalizations)

https://www.kaggle.com/cdc/foodborne-diseases

