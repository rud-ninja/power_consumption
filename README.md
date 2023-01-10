# Title: Forecasting total power consumption of a city based on historical data and environmental factors (Multivariate time series forecasting).

### Objectives:
1. Performed Exploratory data analysis to derive insight about the place and power usage tendencies.
2. Forecasted power consumption using extreme gradient boosting

#### Language used:
Python

#### Libraries used:
Pandas, Numpy, Scipy, Matplotlib, XGBoost, statsmodel, sklearn

#### Forecasting algorithm used:
Extreme gradient boosting or XGBoost regression.

#### The dataset:
Power consumption by the city of Tetouan in Morocco. The dataset is available on Kaggle. All observations were made at an interval of 10 minutes for a whole year. Power is distributed to the city from 3 zones. In this task, the consumption from all the zones have been added and all analyses have been performed on the *Total* consumption for any time duration considered. 


### Figures and discussions:
This task concentrated on understanding the power consumption tendencies of the city of Tetouan, Morocco from 3 distribution units over the year. Understanding the tendencies and trends will help energy providers plan better to gather necessary resources or maintain the systems. Along with record of daily power consumption, the dataset also has a number of environmental factors; all recorded with the same frequency as that of power consumption. These factors are namely, temperature, humidity, diffuse flows and general diffuse flows. Some of these factors affect the power consumption more than the others.

![](https://github.com/rud-ninja/power_consumption/blob/main/images/full_yr_weekly_power.png)

**Fig 1: Power consumption over the whole year with a 7 day moving average**

The above plot tells us that the power usage starts rising steadily from May and continues till August after which it begins to drop. The country of Morocco lies near the Tropic of Cancer and therefore experiences summer during these months. The sudden rise in power consumption could be due to higher requirement of refrigeration and cooling units during this time. As the data is only of 1 year, it is not possible to study monthly trends. But it is surely possible to visualise daily and weekly trends.

#### Stats from the dataset

![](https://github.com/rud-ninja/power_consumption/blob/main/images/power_trend_per_hr.png)

**Fig 2: Hourly power consumption trend**

![](https://github.com/rud-ninja/power_consumption/blob/main/images/temp_hym_per_hr.png)

**Fig 3: Hourly trend of temperature and humidity**

Comparing the trends in figures 2 and 3, we can see that there is a mild correlation between temperature and power consumption in a daily window. This unfortunately does not mean that the temperature rise causes the increase in power usage. Both are in fact the result of the sun rising. The temperature increases when the sun is up and people begin their work for the day. This claim can be corroborated by the drop in temperature in the final third of the graph whereas there is a peak in power usage as it indicates the evening when there's no sun and all the lights are switched on. The mild correlation is a situation of confounding variables caused by the sun rising. Therefore, in the time period of a day, it cannot be said that temperature affects the power consumption.

![](https://github.com/rud-ninja/power_consumption/blob/main/images/power_per_wkn_mnth.png)

**Fig 4: Weekly and monthly power consumption trend**

![](https://github.com/rud-ninja/power_consumption/blob/main/images/temp_hum_per_mnth.png)

**Fig 5: Monthly temperature and humidity trend**

Similar to the previous scenario, there is visible correlation between temperature and humidity as well and power consumption in a monthly frequency. But contrary to the previous scenario, the rise in power consumption is now caused by the rise in temperature during the summer months. We can also see a drop in humidity for that time period. Therefore it can be said that monthly climate does affect the power usage and we have to consider it to forecast monthly results.

![](https://github.com/rud-ninja/power_consumption/blob/main/images/mul_decom_daily.png)

**Fig 6: Seasonal decomposition of power composition with a daily periodicity. It allows us to see the trend and seasonality components of a time series in the same window**

![](https://github.com/rud-ninja/power_consumption/blob/main/images/corr_heatmap.png)

**Fig 7: Correlation heatmap and matrix**

![](https://github.com/rud-ninja/power_consumption/blob/main/images/tables_club.png)

**Fig 8: Sorted tables of monthly average of features**

Above are various ways of visualising the interrelationships between the features in the dataset.

For the forecast, the first 11 months have been chosen as the training set for the XGBoost model and the performance has been tested on the observations from the last month.

![](https://github.com/rud-ninja/power_consumption/blob/main/images/forecast.png)

**Fig 9: Actual values vs Forecasted values**

The above model prediction registered a mean squared error of 6.96 MW. It looks like a very good prediction except for the initial sharp changes in pwer consumption. A 90 percent confidence interval can be caluclated for this algorithm by training several models and obtaining a distribution for the predictions at each timestamp. This will be added in future versions of this project. The complete code can be found [here](https://github.com/rud-ninja/power_consumption/blob/main/tetouan_revisited.ipynb).
