# Project 3: Web APIs and NLP classification

# Problem Statement

**To determine if the beverage company I worked for should focus on the coffee or the tea market in their business expansion, we need to determine if people in the area posts more on social media about coffee or tea.**


## Background
For hot beverage consumption, there are two primary contenders, and both have fiercely loyal fans. There is coffee lovers and espresso enthusiasts on one side, and green tea and chai lovers on the other. So coffee and tea lovers are the main target customers.

The beverage company I worked for is seeking to expand. They want to find out if people in the area post more on social media about coffee or tea. They will, then use this information to decide if they are going into the coffee market or the tea market. 

While I wish this project is a systematic literature review, the aim here is to find the buzz words associated with each beverage. This will help to determine if the person who made the posts online is a coffee drinker or tea drinker. To achieve this, a classification model is needed to classify posts into either coffee or tea. 

## Models 
Models explored were the Naive Bayes algorithm, Decision Tree Classifier, Random Forests Classifier and Extra Trees Classifier. Decision trees tend to overfit without fine-tuning of hyperparameters. Random Forests and Extra Trees performed well, but better with the stemmed dataset. Thus, if there were a lot of irrelevant features (or spam), stemming might be better in consolidating the features, and raising their importance, which will result in a more accurate prediction.


## Primary findings
From the model, it was evident that searches done for coffee leaned towards the different type of machines and methods of brewing beans. Tea-related searches are associated with searching for a specific type of tea, usually named after the place the leaves came from. 


## Conclusion
The selected model of choice is the **Naive Bayes** model. This is due to several reasons:
<br> * It provided good accuracy and f1-scores, compared to other models. 
<br> * It reported good scores, regardless of whether the text was with/without lemmatization/stemming. 
<br> * Negative impact from spam posts seemed to be at a minimum. In other words, the model performed well *despite* the presence of spam.
<br>
<br> It is uncertain how the model will fare in the **longer term**. Considering that there is a strong coffee or tea drinking culture in some societies, the current dataset (with spam) might still prove useful. However, getting a larger set of data is still encouraged. 

