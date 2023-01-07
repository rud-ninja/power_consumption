# Title: Forecasting total power consumption of a city based on historical data and environmental factors (Multivariate time series forecasting).

### Objectives:
1. Perform Exploratory data analysis to derive insight about the place and power usage tendencies.
2. Forecast power consumption

#### Language used:
Python

#### Libraries used:
Pandas, Numpy, Scipy, Matplotlib, XGBoost, statsmodel, sklearn

#### The dataset:
Power consumption by the city of Tetouan in Morocco. The dataset is available on Kaggle. All observations were made at an interval of 10 minutes for a whole year. Power is distributed to the city from 3 zones. In this task, the consumption from all the zones have been added and all analyses have been performed on the *Total* consumption for any time duration considered. 


### Figures and discussions:
This task concentrated on understanding the power consumption tendencies of the city of Tetouan, Morocco from 3 distribution units over the year. Understanding the tendencies and trends will help energy providers plan better to gather necessary resources or maintain the systems. Along with record of daily power consumption, the dataset also has a number of environmental factors; all recorded with the same frequency as that of power consumption. These factors are namely, temperature, humidity, diffuse flows and general diffuse flows. Some of these factors affect the power consumption more evidently than the others.

![](https://github.com/rud-ninja/power_consumption/blob/main/images/full_yr_weekly_power.png)

**Fig 1: Power consumption over the whole year with a 7 day moving average**

The above plot tells us that the power usage starts rising steadily from May and continues till August after which it begins to drop. The country of Morocco lies near the Tropic of Cancer and therefore experiences summer during these months. The sudden rise in power consumption could be due to higher requirement of refrigeration and cooling units during this time. As the data is only of 1 year, it is not possible to study monthly trends. But it is surely possible to visualise daily and weekly trends.

#### Stats from the dataset

![](https://github.com/rud-ninja/power_consumption/blob/main/images/power_trend_per_hr.png)

**Fig 2: Hourly power consumption trend**

![](https://github.com/rud-ninja/power_consumption/blob/main/images/temp_hym_per_hr.png)

**Fig 3: Hourly trend of temperature and humidity**

![](https://github.com/rud-ninja/power_consumption/blob/main/images/power_per_wkn_mnth.png)

**Fig 4: Weekly and monthly power consumption trend**

![](https://github.com/rud-ninja/power_consumption/blob/main/images/temp_hum_per_mnth.png)

**Fig 5: Monthly temperature and humidity trend**

![](https://github.com/rud-ninja/power_consumption/blob/main/images/mul_decom_daily.png)

**Fig 6: Seasonal decomposition of power composition with a daily periodicity**

![](https://github.com/rud-ninja/power_consumption/blob/main/images/corr_heatmap.png)

**Fig 7: Correlation heatmap and matrix**

![](https://github.com/rud-ninja/power_consumption/blob/main/images/tables_club.png)

**Fig 8: Sorted tables of monthly average of features**

![](https://github.com/rud-ninja/power_consumption/blob/main/images/forecast.png)

**Fig 9: Actual values vs Forecasted values**
