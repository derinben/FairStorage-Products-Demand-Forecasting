# Demand Forecasting For FairStorage 

## Summary

In this project, we help Fairstorage build a efficient Machine Learning model to forecast the sales for every product in every store across regions for the next 21 days by leveraging historical data with the volume of sales done over the past 1920 days. Of course, our model has to be better than the conventional statistical models used for these use cases by the company so far. 


### Dataset 

The dataset consists of the different products represented by the product ID that consists of the Item ID, Sub-Category ID, Category ID, Store ID and Region ID. The data also includes the past sales history (in units) over the past 1920 days. 


### Methodology 

Firstly, in order to keep the dataset processing light on my machine, I downcast the datatypes used in the dataset that helps in about 75% reduced memory usage while handling this dataset.

We start with some data analysis to understand the layout of the data which helps us uncover some insights about the data collected so far. 

<p align="center">
<img src = https://user-images.githubusercontent.com/42509638/204121294-a8d34571-b842-49b7-bf8f-7f52d60dd93e.png width = 500  height= 170 >
<img src = https://user-images.githubusercontent.com/42509638/204121283-062d3e19-8796-485a-88b0-a9bf5b3ef7e3.png width = 500  height= 170>
<!-- <img src = https://user-images.githubusercontent.com/42509638/204121253-a14cb7fb-603e-4ad3-adea-8385d228eeb0.png> -->
<!-- ![image](https://user-images.githubusercontent.com/42509638/204121283-062d3e19-8796-485a-88b0-a9bf5b3ef7e3.png)
![image](https://user-images.githubusercontent.com/42509638/204121294-a8d34571-b842-49b7-bf8f-7f52d60dd93e.png) -->

</p>

For example, the above plot shows how erratic the sales trends are and some days where the product was never sold at all. This could be due the product going out of stock but since we have no inventory data available, this hypothesis couldn't be rationalized.

From this, we learn that using a metric like Meaning Absolute Percentage Error (MAPE) during our modelling would not yield the best results given the magnitude of sparse values found in the dataset. 

For exploratory analysis that could make the procurement manager's job easier is shown in the solution notebook.

For the next part, 
