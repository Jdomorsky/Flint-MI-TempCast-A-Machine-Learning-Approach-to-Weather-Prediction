---
# **ML Flint Temperature Predictor**
---
## **Table of Contents**
---

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results](#results)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [References](#references)

---
### Project Overview
---

This project explores time series forecasting by leveraging machine learning to predict the next day’s maximum temperature from historical weather data. The project begins by ingesting a multi-decade dataset and performing thorough cleaning, including handling missing values through forward filling and column-specific imputation, and converting date indices into proper datetime objects to enable effective time-based analyses. This foundational work ensures that the dataset is robust and reliable for subsequent modeling.

Once the data is cleaned, the focus shifts to feature engineering and model development. In addition to including standard meteorological variables such as precipitation, snowfall, snow depth, and daily maximum and minimum temperatures, the project creates advanced features like a 30-day rolling average of maximum temperature and derived ratios that encapsulate seasonal trends. These engineered features capture both short-term and longer-term weather patterns, providing the model with a richer context. A Ridge Regression model, known for its ability to mitigate multicollinearity through L2 regularization, is then trained on this enhanced dataset using a thoughtful time-based train-test split.

Model evaluation is conducted using both numerical metrics and visualizations. The model achieves an R² score of approximately 0.845, indicating that over 84% of the variance in maximum temperature is explained by the predictors, alongside an RMSE of around 7.42, which quantifies the typical prediction error. Comprehensive plots, including actual versus predicted temperature graphs and detailed residual analyses, offer insightful diagnostics into model behavior and pinpoint opportunities for further improvement. Overall, the project not only exemplifies a complete end-to-end machine learning workflow—from data cleaning and feature engineering to model training and evaluation—but also lays a solid foundation for future explorations in weather prediction.

---
### Data Sources
---

All the weather data used in the Flint Weather Predictor project was sourced directly from NOAA’s National Centers for Environmental Information (NCEI). NOAA’s NCEI is a premier repository for historical weather records in the United States, and its comprehensive datasets have been instrumental in various research and forecasting applications.

**Dataset Details:**
- ***Source***: NOAA’s National Centers for Environmental Information (NCEI Website)

- ***Data Coverage***: Historical records spanning from 1960 to the present

- ***Location Focus***: Measurements and observations specific to Flint, Michigan

- ***Data Format***: CSV files following standardized formats (similar to those used in the Global Historical Climatology Network or Integrated Surface Data datasets)

- ***Key Variables***: The dataset includes various meteorological variables such as temperature, wind speed, precipitation, and other weather-related metrics that are critical for building predictive models.

**Rationale for Data Selection:**

The decision to utilize NOAA’s NCEI data was driven by its credibility, consistency, and long-term record-keeping. By leveraging over six decades of weather data, the project is able to analyze seasonal patterns and long-term climate trends, providing a robust foundation for accurate weather predictions in Flint, MI.

**Usage Considerations:**
- ***Data Quality***: NOAA’s rigorous data collection and quality control processes ensure that the records are both reliable and precise.

- ***Licensing***: The data is publicly available, making it ideal for academic and research purposes. Users are encouraged to review NOAA’s terms of use on the NCEI website.

- ***Integration***: The standardized format of the dataset allows for seamless integration with Python libraries such as pandas, numpy, and scikit-learn, which were extensively used throughout this project.

The dataset is publicly available under NOAA's NCEI open data policy, promoting widespread use and dissemination for educational and research purposes. Users can access, download, and employ the data freely.

For more detailed information, metadata definitions, and to explore additional resources, please visit the official dataset page: [***NOAA's NCEI***](https://www.ncei.noaa.gov/?form=MG0AV3).

---
### Tools
---

- ***Visual Studio Code*** – The IDE where you ran your Jupyter Notebooks.

- ***Jupyter Notebook*** – Interactive development environment for exploratory analysis.
    
- ***Python*** – The primary programming language.

- ***Pandas*** – For data ingestion, manipulation, and cleaning.

- ***NumPy*** – For numerical computations.

- ***Scikit-learn*** – For building, training, and evaluating the Ridge Regression model.

- ***Matplotlib*** – For data visualization and plotting.

---
### Data Cleaning
---

The data cleaning process begins with importing the raw weather dataset from a CSV file, where the DATE column serves as the index. The initial step involves an exploratory analysis to understand data quality. We use Pandas to compute the fraction of missing values across each feature, which revealed only very small proportions of missing data. Recognizing the significance of ensuring data consistency, especially in a time series context, we immediately address these gaps—specifically filling the missing values in the snow and precip columns with 0, which reflects the assumption that missing entries in those columns likely indicate no measurable snowfall or precipitation.

After addressing the major missing values, additional cleaning is performed by applying forward filling (ffill) across the dataset. This technique propagates the last valid observation forward to fill any remaining gaps, thereby preserving the temporal structure of the data while ensuring that no NaN values remain. In tandem with these steps, the index is converted into a datetime format. This conversion not only assures a consistent time series format but also enables efficient time-based slicing and aggregation for further analysis. A further inspection is made to count occurrences of sentinel values (such as 9999), often used to denote erroneous or missing data, ensuring that such anomalies do not interfere with downstream processing.

By rigorously handling missing values and converting date indices appropriately, the dataset is transformed into a robust foundation for both feature engineering and model training. This meticulous cleaning process ensures that subsequent processes—such as generating rolling averages, engineered ratio features, and model fitting—proceed with a dataset that is both reliable and optimally structured for accurate time series forecasting.

---
### Exploratory Data Analysis
---



---
### Data Analysis
---

- Creates Measures:
   - ```[INT(DATEPART('year', [Year]) / 10) * 10]```
   - ```[[Mass (g)]/1000]```
   - ```[LOG([Mass (g)])]```


---
### References
---

1. [NOAA's NCEI](https://www.ncei.noaa.gov/?form=MG0AV3)
