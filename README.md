# Summary

In this project, we help Fairstorage build a efficient Machine Learning model to forecast the sales for every product in every store across regions for the next 21 days by leveraging historical data with the volume of sales done over the past 1920 days. Of course, our model has to be better than the conventional statistical models used for these use cases by the company so far. 


## Dataset 

The dataset consists of the different products represented by the product ID that consists of the Item ID, Sub-Category ID, Category ID, Store ID and Region ID. The data also includes the past sales history (in units) over the past 1920 days. 


## Methodology 

Firstly, in order to keep the dataset processing light on my machine, I downcast the datatypes used in the dataset that helps in about 75% reduced memory usage while handling this dataset.

We start with some data analysis to understand the layout of the data which helps us uncover some insights about the data collected so far. 

<p align="center">
<img src = https://user-images.githubusercontent.com/42509638/204121294-a8d34571-b842-49b7-bf8f-7f52d60dd93e.png width = 500  height= 170 >
<img src = https://user-images.githubusercontent.com/42509638/204121283-062d3e19-8796-485a-88b0-a9bf5b3ef7e3.png width = 500  height= 170>
</p>

For example, the above plot shows how erratic the sales trends are and some days where the product was never sold at all. This could be due the product going out of stock but since we have no inventory data available, this hypothesis couldn't be rationalized.

From this, we learn that using a metric like Meaning Absolute Percentage Error (MAPE) during our modelling would not yield the best results given the magnitude of sparse values found in the dataset. Therefore, we could go with Root Mean Square Error (RMSE) as a metric. 

For exploratory analysis that could make the procurement manager's job easier is shown in the solution notebook.

For the next part, we proceed with feature engineering. 
- Encode categorical features - Product Category
- Include Lags (Shifts) - To capture auto correlation between values that are certain time period apart
- Mean encoding - We are again converting categorical features into numerical. This creates a feature that is more representative of the target variable by considering the avergage with respect to different product categories.
- Moving Average (Rolling Mean) - for statistical estimates at different points in time. 
- Expanding Mean - While the rolling window uses the same amount of observations each time, and the expanding window uses more and more observations each time.
- Trends - The selling trend feature will be positive if the daily items sold are greater than the entire duration average else negative.


## Modelling

We use LGBM which is known to handle large datasets with low memory usage without compromising on accuracy. We use the "tweedie" objective as it is the distribution of the sales data we see here (Similar to lot of other sales data distributions which is almost always skewed due to various factors). 

We achieve a RMSE of 0.82 in the final model. 

### Feature Importance Plot 
This plot shows that most of our engineered features contributed to the model's predictions. 
![image](https://user-images.githubusercontent.com/42509638/204121848-0542d450-acf5-4752-9276-b3afa596a983.png)


## For further improvements

- In the future, we could sit together and work with the domain experts from supply chain management (Ex. Procurement Manager) for improved feature engineering and selection. 
- Collecting relevant data such as weather, inventory data, discount, marketing, pricing, shelf life will increase the accuracy and reliability of the model.
- We could consider using a better metric such as <b> Weighted Mean Absolute Error </b> (weighted by price or shelf life). This penalises the errors made on expensive products more as compared to cheaper products. This helps our use case in saving costs by making more accurate forecasts for set of products that are more sensitive (high in price or perishable in nature). 
- We can also consider experimenting with developing separate models for each region to better forecast demand of the products.
