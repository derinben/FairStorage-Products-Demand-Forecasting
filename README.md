# Demand Forecasting For FairStorage 

## Summary

In this project, we help Fairstorage build a efficient Machine Learning model to forecast the sales for every product in every store across regions for the next 21 days by leveraging historical data with the volume of sales done over the past 1920 days. Of course, our model has to be better than the conventional statistical models used for these use cases by the company so far. 


### Dataset 

The dataset consists of the different products represented by the product ID that consists of the Item ID, Sub-Category ID, Category ID, Store ID and Region ID. The data also includes the past sales history (in units) over the past 1920 days. 


### Methodology 

We start with some data analysis to understand the layout of the data which helps us uncover some insights about the data collected so far. 


<img src = https://user-images.githubusercontent.com/42509638/204120919-f774fdaa-5ffd-447c-ae1a-379341084cd0.png width = 500>
<img src = https://user-images.githubusercontent.com/42509638/204120931-d3da8fdb-07b1-487a-a98a-a87958d0a667.png width = 500>

The plot shows how erratic the sales trends are and days where the product was never sold at all. This could be due the product going out of stock but since we have no inventory data available, this hypothesis couldn't be rationalized.


In fact, we learn that using a metric like Meaning Absolute Percentage Error (MAPE) during our modelling would not yield the best results given the magnitude of sparse values found in the dataset. 

