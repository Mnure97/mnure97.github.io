---
layout: post
title: Predicting the ratings of supplements
---

![Image test]({{ site.url }}/images/Protein1.jpg)


Using linear regression model to predict the ratings of protein powder products.


•	**The Project Challenge:**

Given the range of properties, we will be able to predict the success of the new protein powder product.


•	**Data Set:**


Data was scraped from the [bodybuilding](https://www.bodybuilding.com) website using Beautifulsoup, which is a Python library for pulling data out of HTML and XML files.
I chose bodybuilding because It is one of the Internet's most-trafficked health and fitness websites, with over One million daily visitors and nearly Three million active members.

 The attributes for this data set is shown below:


1.	**Brand_name:** Brand name of each product.

2.  **Product_name:** the product name of each brand.

3.	**Ratings:** rating of each product.

4.	**Container_size:** How much scoops in this product.

5.	**Calories:** numbers of Calories in one scoop.

6.	**Total_fat:** numbers of Total fat in one scoop.

7.  **Sugars:** numbers of Sugars in one scoop.

8.	**price:** price of each product.

9.	**price/serving:** price of one scoop.

10.	**PPD:** protein per dollar in one scoop.



•	**Data Analysis:**

After cleaning the data and creating the “PPD” column we were able to start analyzing the data. 


![Image analysis]({{ site.url }}/images/Screen1.jpg)


Below are some graphs.

 ![Image analysis]({{ site.url }}/images/screen2.jpg)


The heatmap above shows that there is a low correlation between the features and the target.


Below is a histogram of the ratings. Notice that the graph is left skewed.

![Image analysis]({{ site.url }}/images/screen4.jpg)

A simple but effective way to transform a left skewed graph to become closer to a normal distribution is taking the power transformation.

![Image analysis]({{ site.url }}/images/screen5.jpg)

I split the data to train 80%  and test 20% in Linear Regression Model , then i have R-Squared with 0.07 in the training part ,and 0.08 to the testing part.



•	**Conclusion:**
 the numbers said there is no relationship between the features and the target, but logically there is a strong relationship between them.

 


•	**Further Steps:**

so after this result i think i need to scrape more data to increase accuracy ,add more data sets with more features to compare.