---
layout: post
title: Using Clustering - unsupervised machine learning for Customer Segmentation
---


![Image test]({{ site.url }}/images/monitor-different-metrics.jpg)





•	**The Project Idea:**


The most successful companies are the ones that know their customers so well and understand there needs 


Because you can’t treat your customers by the same way ,They will find another option which treat them better.


Here is my job as a data analyst to segmenting the customers to better serve them



•	**Data Set:**



The dataset  contains transactions occurring between 01/12/2010 and 09/12/2011 In UK-based and registered non-store online retail.


Many customers of the company are wholesalers.


The dataset have near to 500,000 rows and 7 columns.




![Image test]({{ site.url }}/images/Screen-a.png)



 The attributes for this data set is shown below:



1.	**InvoiceNo:** Unique number assigned to each transaction.

2.  **StockCode:** Product code.

3.	**Quantity:** The quantities of each product per transaction.

4.	**InvoiceDate:** The day and time when each transaction was generated.

5.	**UnitPrice:** Product price per unit.

6.	**CustomerID:** Unique number for each customer.

7.  **Country:** the name of the country where each transaction done.




•	**Data Cleaning:**
I start with cleaning the dataset by Drop null values ,Convert InvoiceDate  to datetime type , CustomerID and InvoiceID into string, 
Drop canceled orders and Remove duplicated data.





•	**RFM Analysis:**

RFM analysis is the most pupular analysis way for customer Segmentation
and let me explain it shortly to you 

 **Recency:** days since last customer transaction.

 **Frequency:** Number of Purchase is done in last 12 months.

 **Monetary:** Total Customer spend in last 12 months.


and look at this new dataframe 



![Image analysis]({{ site.url }}/images/screen-b.png)


 
 i got Recency here after do some operations on InvoiceDate Column.

 i count InvoiceNo Column to get th Frequency for each customer.

  and for Monetary i Multiply UnitPrice and Quantity columns.




![Image analysis]({{ site.url }}/images/screen-c.png)



after that i creat new 4 columns as you see above [R,F,M,RFM Score]

R,F,M labels range is from 1 to 4 

for R the lower Recency the Higher label value 

but F,M range is different, higher label to higher value , because we need the customer spend more and visit more.

and sum all of them in RFM Score



based on RFM score i creat new column called 'General_Segment'
for each customer if RFM score >= 9 the class of this customer will be 'Gold’
and if RFM score >= 5 and < 9 the class will be 'Silver’
    else it's 'Bronze' as you see below



 ![Image analysis]({{ site.url }}/images/screen-d.png)






• **Clustering Key steps**



1. Data Pre-processing.

2. Choosing a number of clusters.

3. Running k-means clustering on pre-processed data.



 • **Pre-processing**
 
 

 ![Image analysis]({{ site.url }}/images/screen-e.png) 



look at the mean and standard deviation it's different and Kmeans work better with equal mean and standard deviation

 so we have to scale the data !




![Image analysis]({{ site.url }}/images/screen-f.png)




![Image analysis]({{ site.url }}/images/screen-g.png)

now it's scaled ..



• **K-means**



let's go to the second step and Running the Kmeans , and look at the elbow after that 

![Image analysis]({{ site.url }}/images/screen-h.png)

i see here 3 clusters 

now take a look atb this bar plot


![Image analysis]({{ site.url }}/images/screen-i.png)


it's shows that Recency in gold cluster is low and the Frequency & Monetary is high.


for Silver cluster all of them near to the middle.


but for bronze class the Recency is high and the Frequency & Monetary values is low.



•	**Conclusion:**

in this project I learned more about business side that's what I'm interested in ,how I segmenting the customers based on RFM analysis and make the segments more powerful with k-means clustering


hope you enjoyed readying that 

thank you.



