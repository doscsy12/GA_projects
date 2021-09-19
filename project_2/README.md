# Project 2: Ames Housing Data and Kaggle Challenge

# Problem Statement

The aim of this project is to identify the prominent factors that affect property prices in Ames, Iowa.

## Background
The Ames Housing dataset described the sale of individual residential property in Ames, Iowa from 2006 to 2010. It was found by Dr Dean De Cock, Professor of Statistics at Truman State University for his students to utilise the skills he taught in class ([source](http://jse.amstat.org/v19n3/decock.pdf)). The data set contains almost 2050 observations and a large number of explanatory variables (23 nominal, 23 ordinal, 14 discrete, and 20 continuous) involved in assessing property values. These 79-80 or so variables describe (almost) every physical attributes (quality and quantity) of the properties. Most of the variables described are features that a potential buyer would want to know before an offer was made.  


## Primary Work/Findings
Data from the well known Ames housing data was used to create regression models that will predict the sale price of houses in the area. 

The various property size features, namely living area, basement area, lot area and garage area, were all found to be positively correlated to the sale price. Overall quality and condition were also found to be among the most important factors in determining property prices. 

Linear regression modelling using the selected features was utilised to predict the sale price. The ordinary least squares (OLS) model achieved rather similar rsme scores, effectively matching those derived from the Ridge and Lasso regressions.


## Conclusion and Recommendations
**Main factors:** 
The overall quality of the property is a huge factor in determining its value. Overall quality is the rating of the overall finish, material, etc of the house. This is also evident in other factors, since condition of the material on the exterior, kitchen, fireplace, basement, heating are also related to the general overall quality of the house.

As expected, size matters! Larger living areas, area of first floor, lot area, masonry veneer area, number of baths are also huge factors in the sale price. An extra bathroom (up to 4 in total) can increase value to the property.

On the other hand, the age of the property has a negative impact on sale price. However, this can be curtailed by having remodeling or renovations done.

**Renovations:**
- **What renovations then will add the most value to a house?**
- An extension to the property (increase in square footage), especially when one adds to the living areas, rather than add an extra bedroom, will increase the value. Number of bedrooms seemed to have little impact. It could be that expanding a bedroom might reduce living areas. 

- Renovations to just one part of the house like upgrading the kitchen or bathroom, will fetch a higher sale price. One can also make it more efficient - by installing smart-home technology can help increase its value.
<br> 

- **What improvements will NOT add value to a house?**
- The size of a porch has little effect. Either not everyone likes to sit on the porch, or it cannot be used all year. While a porch can be used in good weather, one can stay indoors all day.
- Having a swimming pool or pool area haa no effect. This is not surprising since it is expensive and a hassle to maintain.








