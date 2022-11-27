# Demand Forecasting For FairStorage 

## Summary

In this project, we help Fairstorage build a efficient Machine Learning model to forecast the sales for every product in every store across regions for the next 21 days by leveraging historical data with the volume of sales done over the past 1920 days. Of course, our model has to be better than the conventional statistical models used for these use cases by the company so far. 


### Dataset 

The dataset consists of the different products represented by the product ID that consists of the Item ID, Sub-Category ID, Category ID, Store ID and Region ID. The data also includes the past sales history (in units) over the past 1920 days. 


### Methodology 

We start with some data analysis to understand the layout of the data which helps us uncover some insights about the data collected so far. 


![image](https://user-images.githubusercontent.com/42509638/204120866-008eb607-fec5-43dc-a4ab-f44a4b31c8e6.png)

![image](https://user-images.githubusercontent.com/42509638/204120861-75397bbd-7a2d-4f4c-9c94-27c3ce3b738d.png)
The plot shows how erratic the sales trends are and days where the product was never sold at all. This could be due the product going out of stock but since we have no inventory data available, this hypothesis couldn't be rationalized.


In fact, we learn that using a metric like Meaning Absolute Percentage Error (MAPE) during our modelling would not yield the best results given the magnitude of sparse values found in the dataset. 

