---
layout: post
title: Detecting Financial Fraud Using Machine Learning Classifications Models.

---

![Image test]({{ site.url }}/images/credit-cards.png)





•	**The Project Idea:**


For years, fraudsters would simply take numbers from credit or debit cards and print them onto blank plastic cards, Visa and Mastercard 


mandated that banks and merchants introduce  chip card technology , which made it possible for merchants to start requesting a PIN for each transaction


Nevertheless,  experts predict online credit card fraud to soar to a whopping $32 billion in 2020.. 


In addition to the implementation of chip card technology, companies have been investing massive amounts in other technologies for detecting fraudulent transactions.


Would Machine Learning constitute great allies in this battle?



•	**Data Set:**



I used Dataset from Kaggle have 600,000 Rows And 10 Columns 



![Image test]({{ site.url }}/images/sc2.png)


 The attributes for this data set is shown below:


1.	**Step:** This feature represents the day from the start of simulation. It has 180 steps so simulation ran for virtually 6 months.
.

2.  **Customer:** This feature represents the customer id.

3.	**zipCodeOrigin:** The zip code of origin/source.

4.	**Merchant:** The merchant's id.

5.	**zipMerchant:** The merchant's zip code.

6.	**Age:** Categorized age

0: <= 18

1: 19-25

2: 26-35

3: 36-45

4: 46-55

5: 56-65

6: > 65

U: Unknown



7.  **Gender:** Gender for customer

E : Enterprise

F: Female

M: Male

U: Unknown.


8.	**Category:** Category of the purchase.

9.	**Amount:** Amount of the purchase.

10.	**Fraud:** Target variable which shows if the transaction fraudulent(1) or benign(0).





•	**Data Analysis:**

I started with cleaning the data by drop zipMerchant and zipCodeOrigin Columns becouse they have only one value so it is not helpful here 
,I convert the Merchant and Customer Columns into numerical value after that i transform them into categorical value
but after that i think the Customer Column is just an ID so it is did not help my model , so i also drop it.


![Image analysis]({{ site.url }}/images/Screen-shot1.png)


![Image analysis]({{ site.url }}/images/ScreenShot2.png)



**THE CHALLENGE IS !**


 ![Image analysis]({{ site.url }}/images/download-1.png)



my data is imbalance i have only 1.21% for fraud, and 98.79% for Safe Transaction
 
 **And What I did for Imbalance problem is**
 
 I choose Logistic Regression Model to strat with because it's good for who's have two Classes
 then :

 1. I Scaled Amount Column 

2. SMOTE Technique (Over-Sampling)

3. Oversample data during cross-validation, not before!



![Image analysis]({{ site.url }}/images/ScreenShot3.png)

4. I Don't use accuracy score as a metric with imbalanced datasets (because it is usually high and misleading)

5. Use f1-score, precision/recall score and confusion matrix

6. Test on the original Data


![Image analysis]({{ site.url }}/images/Screenshot6.png)



F1 looks low here ,let's trying on other model with diffrent way in SMOTE oversampling 
i think it's better when i change the size of the Sampling strategy 
because in the end we only have 1.2% of my data is fraud , and 50/50 sampling strategy is not fair !



**Random Forest Classifier**



![Image analysis]({{ site.url }}/images/ScreenShot7.png)


![Image analysis]({{ site.url }}/images/ScreenShot5.png)

F1 looks better ! 

let's check by the Confusion Matrix


True Negatives (Top-Left Square): This is the number of correctly classifications of the "No" (No Fraud Detected) class.



False Negatives (Top-Right Square): This is the number of incorrectly classifications of the "No"(No Fraud Detected) class.



False Positives (Bottom-Left Square): This is the number of incorrectly classifications of the "Yes" (Fraud Detected) class.



True Positives (Bottom-Right Square): This is the number of correctly classifications of the "Yes" (Fraud Detected) class.




![Image analysis]({{ site.url }}/images/ScreenShot8.png)



•	**Conclusion:**

Implementing SMOTE on the imbalanced dataset helped the imbalance of our labels ,but in the right way!

Random Forest Classifier Model is doing better  

We have to take care more about False Negatives and False Positives misclassifies those non fraud transactions as fraud cases. 
Imagine that people that were making regular purchases got their card blocked due to the reason that our model classified that transaction as a fraud transaction,
this will be a huge disadvantage for the financial institution.
The number of customer complaints and customer disatisfaction will increase. 





[Resource](https://rstudio-pubs-static.s3.amazonaws.com/448728_e9ddde25fb0242b38e9d05f2b007ec21.html)