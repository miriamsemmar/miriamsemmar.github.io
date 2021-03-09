---
layout: post
title:      "Recommendation Systems"
date:       2021-03-09 02:50:40 +0000
permalink:  recommendation_systems
---

Streaming services have exploded in popularity and availability as years have gone on. Netflix, Hulu, Paramount+, all promising some sort of entertainment. Sometimes, you log in to watch the newest episodes of your favorite show. Sometimes, you're bored and hoping something in your suggested watch list will catch your eye. But how exactly do these lists come to be? Recommendation systems! 

We can categorize recommendation systems as either unpersonalized and personalized.

Unpersonalized recommendation systems recommend the most popular items overall. Think of Netflix's Top 10 list.

Personalized recommendation are a bit more involved. They leverage machine learning and large amounts of data to make unique predictions for each individual user. Many recommendation systems use of something called collaborative filtering. Collaborative filtering makes predictions (filtering) about the interests of a user by collecting preferences or taste information from many users (collaborating). There are two types of collaborative filtering: memory/neighborhood based, and model based.

Memory based filtering is based on the premise that similar users will enjoy similar items or that similar items will be enjoyed by similar users. Memory based filtering deems items or users similar to each other by using similarity metrics

Model-based algorithms use the data to learn/train a model which can later be used to make predictions. Model based filtering view the dataset as a matrix, and by decomposing that matrix into individual matrices. This reduction of dimensionality can be completed using Singular-Value Decomposition or SVD. With SVD, the recommendation problem is turned into an optimization problem that deals with how good it is in predicting the rating for items given a user. The optimization is completed by minimizing the squared error using gradient descent, and then scored using MAE or RMSE.


 Surpise is a popular python library which efficiently builds and analyzes recommendation systems using explicit rating data, and automatically cross validates to create optimal predictions.
