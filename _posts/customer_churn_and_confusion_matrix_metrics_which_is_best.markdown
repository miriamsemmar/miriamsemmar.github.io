<h1> Customer Churn & Confusion Matrix Metrics. Which is best? </h1>

Customer churn is one of the most important metrics for a business providing ongoing services to evaluate. Think of subscription based services: Netflix, Hulu, Verizon, Spotify, etc. The subscription based business model has become increasingly popular. While customers are provided more flexibility, businesses must keep a close eye on how many of those users are churning. "What is churn?" you ask. Churn is the percentage of customers that stopped using your product. Some percentage of churn is expected. Users may try the service and decide another offering is a better fit. However, if this number is on the rise, the business risks losing large amounts of revenue. To keep churn as low as possible, businesses implement various strategies to make the product/service more enticing to users. This might be in the form of loyalty incentives, excellent customer service or discounts. However, before a business can work to counteract churn, they need to be able to determine who is at risk of churning before it is too late. Using machine learning algorithms, we can actually help to determine which customers are most likely to churn before we lose their business. 

We won't go into depth on the various modeling approaches here. Machine learning leverages algorithms on "training" data to "learn" from. This allows the model to learn what behavior makes a customer more likely to churn. We then test what the algorithm has learned on a set of test data to evaluate its performance. Typically, there are 4 key metrics one can consider: Accuracy, Precision, Recall or F1. Brief descriptions of each can be found below:

* Accuracy: a measure of how "right" a model is. This is calculated as the sum of true positives and true negatives divided by the total number of samples

![](https://miro.medium.com/max/1836/1*sVuthxNoz09nzzJTDN1rww.png)

* Precision: Precision looks at proportion of true positives of all samples the algorithm scored as positive. As a result, false positives drive down our precision score. 

![](https://miro.medium.com/max/888/1*C3ctNdO0mde9fa1PFsCVqA.png)

* Recall: Precision looks at proportion of samples the algorithm correctly scored as positive out of all the actual positives. In this case, false negatives decreases our recall score. 

![](https://miro.medium.com/max/836/1*dXkDleGhA-jjZmZ1BlYKXg.png)


* F1: F1 tells us the balance between precision and recall. F1-score is calculated as:
   
	 ![](https://miro.medium.com/max/564/1*T6kVUKxG_Z4V5Fm1UXhEIw.png)
	 
	 

When evaluating customer churn, precision and recall will be important to us. With recall, incorrectly predicting that someone who is going to churn as someone who won't churn will cost the business money. These are the exact people businesses need to be engaging with more and exerting resources on in order to maintain their business.  Precision is also important because we don't want to waste business resources on individuals who plan to maintain their customer status. 






