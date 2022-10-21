# NYPD 911 Call Forecasting

In this project, we collect data on NYPD 911 calls from 2018-01-01 to 2022-09-30 from https://catalog.data.gov/dataset/nypd-calls-for-service-historic and https://catalog.data.gov/dataset/nypd-calls-for-service respectively.
This combined dataset contain information on over $30$ million calls throughout this time period. We group this data by individual dates and obtain a record of the number of calls received by the NYPD department each day.

![call_data](https://user-images.githubusercontent.com/79466280/197096684-a3a7781d-daad-4a30-b191-971efd8eddca.png)

## **Data Dictionary for NYPD_Calls_by_Date.csv**

| Column | Description |
|---|---|
| Dates| The date that the incidents occurred |
| #calls | The number of calls received by NYPD dispatchers |
| weekday | The day of the week, represented by integers from $0$ - $6$ |
| day | The day of the month of the incidents |
| month | The month of the incidents |

## **Results**

| Model | MAPE (Daily) | MAPE (Weekly) |
|---|---|---|
| Baseline Model | 0.0349 | 0.0474 |
| Linear Regression | 0.0261 | 0.0630 (recursive), 0.0372 (direct) |
| Random Forest | 0.0368 | - |
| XGBoost | 0.0383 | - |
| Neural Network | 0.0287 | 0.0372 |

The **direct weekly Linear Regression model** and **weekly Neural Network** are the best candidates for week-to-week forecasting models

### **Daily and Weekly Predictions with our most promising Forecasting Models**
![daily_linear_regression](https://user-images.githubusercontent.com/79466280/197096704-88b0c71f-007a-445c-9332-7baa07208d3b.png)
![direct_weekly_linear_regression](https://user-images.githubusercontent.com/79466280/197097080-98a46d52-a543-4afc-b08e-27096f687388.png)

![daily_neural_network](https://user-images.githubusercontent.com/79466280/197096727-75f3bde6-b31b-412e-947e-e02c3f43fd25.png)
![weekly_neural_network](https://user-images.githubusercontent.com/79466280/197096811-bcfd6e9d-e673-4f47-b1e2-b46e9ab3cd57.png)
