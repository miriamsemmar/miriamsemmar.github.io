# Dog Breed Image Classification via Convolutional Neural Networks


53% of Americans households include a dog, creating a huge market and need for canine care products. A strong dog image classification model can have many applications including creating more custom/personalized product recommendations to pet parents. Dog classification would also allow for more personalized marketing of these products.

Additionally, a dog image classification model could be a tool to help identify lost dogs and help reunite them with their owners through facial recognition.

Barking Data Inc. would like to develop this model in order to sell the various applications that will come out of it to pet product companies, veterinary offices, animal rescues and other companies who may benefit from these tools.

To begin the development of the model we will eventually sell, we will start by building a model using the 50 most popular dog breeds. Additionally, we will generate our own dataset using Selenium to scrape Google Images.


We began our modelling process using a densely connected network as our baseline model. This model performed poorly, with an accuracy around 3% across both the testing and training sets as well as demonstrating significant overfitting. Image below.


<img align="center" src="https://github.com/miriamsemmar/Capstone/blob/main/Results-Images/Baseline%20Model.png" width="400" height="600">


Following poor performance from a densely connected network, we moved on to CNN networks. We didn't see much improvement in these models until trying a gridsearch. The gridsearch model resulted in a roughly 29% accuracy on train data and a roughly 19% accuracy on test data. However, overfitting still remained a problem. 

Transfer learning via VGG19 and Inceptionv3 also did not yield much improvemnt.

Following out lack of success with our existing dataset, we combined our dataset with the Stanford dog dataset to increase our sample size. From here, we built a CNN model using a step-by-step process. We specifically tried to address overfitting via dropout regularization and weight decay. While our weight decay model yielded the highest accuracy (86%), overfitting only improved slightly. Our dropout regularization model is our final model, with an accuracy of 55% for our training data and 53% for our test data. Loss was roughly 1.8 for both groups. Image below.

<img align="center" src="https://github.com/miriamsemmar/Capstone/blob/main/Results-Images/Dropout.png" width="400" height="600">

Potential next steps include increasing the size of our dataset,test leveraging K-fold cross validation to improve our model and expanding our model to provide predictions for mixed-breed dogs.
