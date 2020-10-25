---
layout: post
title:      "Mod 2 Project"
date:       2020-10-25 13:35:29 -0400
permalink:  mod_2_project
---


Creating linear regression models can be tricky for numerous reasons. Have you scrubbed your data clean? Do you have outliers? What should we do with the outliers? Are your residuals normal? Do we need to transform any of our features? What type of transformation should we perform? What about multicollinearity? These are some of the questions we might consider. What I’d like to focus on today is the impact one of the earliest decisions you make in modeling can have on the output of your model. How does simplifying existing data impact our models?
 
 Recently, I was working with a dataset for [House Sales in King County, USA](https://www.kaggle.com/harlfoxem/housesalesprediction). This dataset includes some expected features: price, number of bedrooms and bathrooms, square footage, etc. As I prepared this dataset for modeling, my initial approach to the ZIP code column was to consolidate this information by grouping these ZIP codes by neighborhood. I dropped the ZIP code column and transformed the neighborhoods into dummy variables. Moving onto modeling, my baseline model output an R2 of 0.753. However, the RMSEs were very high, residuals were skewed and many of the features yielded p-values greater than 0.05. Despite working to further improve my model by removing features, using log transformations and removing features due to multicollinearity, the RMSE difference between my train and test sets were still very large. 

After seeing little improvement in my model, I decided to take a different approach and leave the zipcodes as they were. When I transformed the ZIP codes into dummy variables, my baseline model had an R2 of 0.841. This was already much higher than that of the baseline model from my original approach. However, the RMSE difference was still high and my residuals were even more skewed. Performing a log transformation on price (our target variable), drastically improved my model. My final model had an R2 of 0.856 and a RMSE difference close to 0. Furthermore, the residuals were fairly normally distributed.  

Why did using ZIP codes instead of neighborhoods drastically improve the model? 

