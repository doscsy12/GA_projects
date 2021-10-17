# Project 4: West Nile Virus Prediction

# Problem Statement
We analyze the severity of the West Nile Virus to find the best metric to best tackle the client's request. We find that the West Nile Virus is fatal for a small proportion of the population, especially those who are older and have a weaker immune system. For the general population, about 20% of those infected will develop a fever. While this may not be fatal, those contracting the fever will have a productivity loss, and tax the city's public health services. With Covid still being prevalent, we believe that we should aim to decrease the number of WNV cases, whether it results in a fatality or a fever. As such, we believe that while our focus should be developing accurate predictions, it is just as important to maximize the number of true findings (sensitivity). 


## Background
West Nile virus (WNV) (Flaviviridae: Flavivirus) is an arbovirus circulating among mosquitoes, which serve as the vectors, and wild birds, which serve as the main reservoir hosts. WNV raises public health concerns for its ability to infect humans, which are considered dead-end hosts due to our inability to develop a sufficient viremia to infect mosquitoes. So, environmental surveillance, particularly surveillance based on mosquito sampling, can provide early detection of the virus circulation before the onset of the disease in humans.  
<br> WNV typically spreads via the bite of infected mosquitoes. Most mosquitoes do not carry the virus. While most people infected with WNV do not feel sick, about 1 in 5 people develop a fever and flu-like symptoms. Severe illness can occur in about 1 in 150 people and is most likely in people over age 60. Because there are no specific medications to treat WNV in people, the most effective method to prevent infection is to prevent mosquito bites. 
<br>
<br> So, every year, from late-May to early-October, public health workers in Chicago setup mosquito traps scattered across the city. Every week from Monday through Wednesday, these traps collect mosquitoes, and the mosquitoes are tested for the presence of West Nile virus before the end of the week. The test results include the number of mosquitoes, the mosquitoes species, and whether or not West Nile virus is present in the cohort. 

## Data and Model
The data is in a format where each row represents the results for the results of a week / trap location collection, and the interval between the dates is a week apart from May to October. The model relies on the presence of past West Nile Virus, weather data, and trap locations with a (Model) develop predictions of whether a trap will have WNV present during a particular collection week. 

The overall performance of the model depends on the AUC score and recall/sensitivity scores. Sensitivity was chosen because predicting mosquitoes to have WNV when they do not (false positives) is less of a concern than predicting mosquitoes to not have WNV when they actually do (false negatives). 

We created models to after splitting into two primary ways: feature reduction and feature extraction. Due to the highly imbalanced nature of our target group, we used Smote on the minority class to improve the balance in the target class. Below are the list of models that we created:

**A. Feature Reduction**
Feature reduction models undergo standardization using StandardScaler and Smote on the minority class.
    1. Logistic Classifier - Ridge Regularized
    2. Logistic Classifier - Lasso Regularized
    3. Decision Tree Classifier
    4. Bootstrap Aggregating Classifier
    5. XGBoost Classifier
    
**B. Feature Extraction**
Feature extraction models undergo standardization using StandardScaler, Smote on the minority class, and PCA for dimensionality reduction.
    1. Logistic Regression
    2. Decision Tree Classifier
    3. Random Forest Classifier
    4. Extra Trees Classifier
    5. Support Vector Classifier

## Primary findings

The top 5 features predicting the presence of WNV in our logistic-lasso model are: sunrise, temperature difference, average temperature, station pressure and thunderstorm. These features are not entirely surprising, since previous studies have demonstrated that features related to temperature will make a positive impact on WNV. Our dummy feature created through outside research, thunderstorm, is also in our top 5 features, suggesting that it may have been a good idea to dummify this weather condition.

Meanwhile, the top 5 features predicting the lack of WNV in our logistic-lasso model are: preciptotal, longitude, sealevel, dewpoint and depart. As we see in our EDA, preciptotal has a negative effect on mosquito activity and its resulting effect on the presence of WNV. Longitudinal difference may not be directly related to the presence of WNV, but it may be indicative of other indirect causes such as population density, cleanliness of an area, or presence of a location where there is still water: an ideal breeding ground for mosquitos. Dewpoint is a measure of both temperature and takes into account precipitation. As such, it provides a benefit of combining both our top feature predicting the absence and presence of WNV.

The top 5 features in our xgboost model are: sunset, sunrise, species_nr, addressaccuracy and year. Similar to our  previous finding during data cleaning, mosquito life cycles and activities are affected by sunrise/sunset times. Our third most important feature is the species; This makes sense given the rates at which our higher ordinal value species shows a higher rate of testing for WNV as compared to the species with lower ordinal value.

## Conclusion
Our client requested for us to provide suggestions of when and where to spray for mosquitoes which have the West Nile Virus in order to decrease their city's rate of infection and death rate. We recommend that pesticides be deployed in inner suburbs, and that older housing (built in the 40s-60s) be given priority due to their older sewer systems which are favourable breeding grounds for mosquito breeding. Furthermore, we recommend that spraying should be done 14 days earlier given that there is a max 14-day WNV incubation period. 

We had provided a map which predicts spray locations beginning from Week 29 to Week 39 of each year. This allows the city to plan the routes they should be taking to reach all the spray locations within the week. It should be noted that while we also provide a map of all locations to be sprayed, users should take more care to conduct the spraying week by week to reduce the number of sprays required and not waste on spraying locations which are not suggested by the model.

From the models developed, Logistic-Lasso is selected due to several reasons:
* The model was built based on feature reduction. This allowed us to filter irrelevant or redundant features based on domain knowledge; It is a relatively safe technique to ensure that the features that have been 'proven' to possess high predictive power to be included in the model. 
* Highest roc_auc accuracy.  The model provide good predictions and could provide an accurate distinguish between the classes. 
* The model has high sensitivity, ie., the model has low false negatives. Since predicting mosquitoes to have WNV when they do not (False Positives) is less of a concern than predicting mosquitoes not to have WNV when they actually have it (false negatives). 

However, given a higher computing power and time to continually train the models, we also suggest another model based on feature reduction: the XGBoost model. The reasons are as such:
* Model does not exhibit overfitting due to its nature of training stumps (short trees).
* Model continually builds upon its previous iteration and determines the best estimators based on previous misclassification.
* Model has the highest ROC score as shown in the plot. This suggests that the xgboost model was able to obtain the highest true positives when compared to false positives.


## Recommendation
We recommend the collection of other data to supplement our datasets and improve our model. Some of the data we suggest collecting are:
    1. Population density
    2. Housing density
    3. Housing year built
    4. Sewage flow
    5. Increased number of traps 
    6. Humidity
    7. Sunlight duration
    8. Migratory patterns of aviation animals (as potential carriers)
    9. Data on WNV cases in other states

We believe that including data on the above list would provide greater predictive power to our models.

In the long term, we recommend that our client explore other ways to combat the WNV in their city. These include the usage of genetically modified mosquitos which disables female mosquitos from reproducing.