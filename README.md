# Ski Resort Lift Ticket Price Prediction
## Introduction
As ski lift ticket prices continue to rise faster than inflation, both consumers and resort operators face challenges in determining fair value. This project addresses this business problem by developing a predictive model to estimate the price of a day pass based on a ski resort's features.

The goal is to provide a data-driven tool for:

- Skiers: To evaluate whether a ticket price is fair for the amenities offered, helping them maximize the value of their purchase.

- Ski Resorts: To benchmark their pricing against competitors and understand which features are the most significant drivers of ticket price, informing strategic investments and pricing adjustments.

The analysis involved a comprehensive workflow, including data cleaning, feature engineering, and an evaluation of multiple regression models to identify the most accurate predictor of ticket price.

## Methodology
**1. Data Source** </br>
The analysis utilized a dataset from Ski-resort-stats.com, containing data for 376 European ski resorts across 16 distinct features. Key variables included:

Mountain Characteristics: Highest point, lowest point, total slope length, and number of beginner, intermediate, and difficult slopes.

Resort Amenities: Number and type of lifts (surface, chair, gondola), lift capacity, and availability of snow cannons, snow parks, and night skiing.

**2. Data Preprocessing & Feature Engineering**</br>
To prepare the dataset for modeling, several steps were performed:

Data Cleaning: Handled missing values and dropped irrelevant columns.

Dummy Variables: Converted categorical features like NightSki and SnowPark availability into numerical (0/1) format.

Feature Engineering: Created a Total Length feature by calculating the vertical drop (Highest Point - Lowest Point) to better capture the scale of the resort.

**3. Modeling Approach**</br>
To find the most accurate prediction model, a suite of regression techniques was evaluated. The performance of each model was measured by its Root Mean Squared Error (RMSE) on a held-out test set. The models tested include:

- Linear Regression

- Lasso and Ridge Regression (with cross-validation to find the optimal alpha)

- Decision Tree (both full and pruned)

- Random Forest

- Gradient Boosting

## Results & Model Comparison
After evaluating all models, **Lasso and Ridge Regression** proved to be the most effective, achieving the lowest RMSE and thus the highest predictive accuracy.
| Method    | Best RMSE |
| -------- | ------- |
| Naïve Baseline|12.46|
|Linear Regression|8.82|
|Decision Tree|9.56|
|Random Forest|9.27|
|Boosting|8.58|
|Lasso/Ridge|7.67  |

The final Lasso model also performed feature selection by shrinking the coefficients of less important variables to zero, providing insight into the key drivers of ticket price.

## Business Implications & Takeaways
This analysis successfully created a model that can predict ski resort ticket prices with a high degree of accuracy. The key takeaways provide value to both consumers and businesses:

- For Consumers: The model can be used as a tool to input a resort's features and receive an estimated fair price, helping skiers make informed purchasing decisions and identify overpriced tickets.

- For Resort Operators: The model provides a powerful framework for competitive analysis and strategic pricing. By understanding which features (e.g., number of slopes, lift types) most influence price, resorts can better justify their pricing or identify areas for capital improvement to support price increases.
