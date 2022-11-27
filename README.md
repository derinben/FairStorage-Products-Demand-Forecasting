# Demand Forecasting For FairStorage 

## Summary

In this project, we help Fairstorage build a efficient Machine Learning model to forecast the sales for every product in every store across regions for the next 21 days by leveraging historical data with the volume of sales done over the past 1920 days. Of course, our model has to be better than the conventional statistical models used for these use cases by the company so far. 


### Dataset 

The dataset consists of the different products represented by the product ID that consists of the Item ID, Sub-Category ID, Category ID, Store ID and Region ID. The data also includes the past sales history (in units) over the past 1920 days. 


### Methodology 

Firstly, in order to keep the dataset processing light on my machine, I downcast the datatypes used in the dataset that helps in about 75% reduced memory usage while handling this dataset.

We start with some data analysis to understand the layout of the data which helps us uncover some insights about the data collected so far. 

<p align="center">
<img src = https://user-images.githubusercontent.com/42509638/204120919-f774fdaa-5ffd-447c-ae1a-379341084cd0.png width = 500  height= 170 >
<img src = https://user-images.githubusercontent.com/42509638/204120931-d3da8fdb-07b1-487a-a98a-a87958d0a667.png width = 500  height= 170>
<img src = https://user-images.githubusercontent.com/42509638/204121253-a14cb7fb-603e-4ad3-adea-8385d228eeb0.png>

</p>

For example, the above plot shows how erratic the sales trends are and some days where the product was never sold at all. This could be due the product going out of stock but since we have no inventory data available, this hypothesis couldn't be rationalized.

From this, we learn that using a metric like Meaning Absolute Percentage Error (MAPE) during our modelling would not yield the best results given the magnitude of sparse values found in the dataset. 

For exploratory analysis that could make the procurement manager's job easier is shown in the solution notebook.

For the next part, 
