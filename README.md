# NYPD 911 Call Forecasting

In this project, we collect data on NYPD 911 calls from 2018-01-01 to 2022-09-30 from https://catalog.data.gov/dataset/nypd-calls-for-service-historic and https://catalog.data.gov/dataset/nypd-calls-for-service respectively.
This combined dataset contain information on over $30$ million calls throughout this time period. We group this data by individual dates and obtain a record of the number of calls received by the NYPD department each day.

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
