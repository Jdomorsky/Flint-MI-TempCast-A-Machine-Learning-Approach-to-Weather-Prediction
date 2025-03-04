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
- [References](#references)

---
### Project Overview
---

The Flint Weather Predictor is an innovative machine learning project focused on accurately forecasting weather conditions in Flint, Michigan. This project was designed to tackle the challenges of weather prediction by utilizing historical weather data and applying advanced machine learning algorithms. Recorded weather data for this project spans from 1960 to the present, providing a rich and extensive dataset for analysis. By examining over six decades of past weather patterns, the Flint Weather Predictor aims to deliver precise and reliable forecasts, helping residents and businesses make informed decisions based on anticipated weather conditions. This project exemplifies the power of data-driven approaches in solving real-world problems and highlights the potential of machine learning in the field of meteorology.

---
### Data Sources
---

All the weather data used in the Flint Weather Predictor project was sourced directly from NOAA’s National Centers for Environmental Information (NCEI). NOAA’s NCEI is a premier repository for historical weather records in the United States, and its comprehensive datasets have been instrumental in various research and forecasting applications.

**Dataset Details:**
- Source: NOAA’s National Centers for Environmental Information (NCEI Website)

- Data Coverage: Historical records spanning from 1960 to the present

- Location Focus: Measurements and observations specific to Flint, Michigan

- Data Format: CSV files following standardized formats (similar to those used in the Global Historical Climatology Network or Integrated Surface Data datasets)

- Key Variables: The dataset includes various meteorological variables such as temperature, wind speed, precipitation, and other weather-related metrics that are critical for building predictive models.

**Rationale for Data Selection:**

The decision to utilize NOAA’s NCEI data was driven by its credibility, consistency, and long-term record-keeping. By leveraging over six decades of weather data, the project is able to analyze seasonal patterns and long-term climate trends, providing a robust foundation for accurate weather predictions in Flint, MI.

**Usage Considerations:**
- Data Quality: NOAA’s rigorous data collection and quality control processes ensure that the records are both reliable and precise.

- Licensing: The data is publicly available, making it ideal for academic and research purposes. Users are encouraged to review NOAA’s terms of use on the NCEI website.

- Integration: The standardized format of the dataset allows for seamless integration with Python libraries such as pandas, numpy, and scikit-learn, which were extensively used throughout this project.

The dataset is publicly available under NOAA's NCEI open data policy, promoting widespread use and dissemination for educational and research purposes. Users can access, download, and employ the data freely.

For more detailed information, metadata definitions, and to explore additional resources, please visit the official dataset page: [NOAA's NCEI](https://www.ncei.noaa.gov/?form=MG0AV3).

---
### Tools
---

- ***VS Code*** - IDE
- ***Jupyter Notebook*** – Data Cleaning & Visualizations
    - [NOAA's NCEI](https://www.ncei.noaa.gov/?form=MG0AV3)
    - **Libraries Used:**
      - **Pandas**
      - **Numpy**
      - **SkLearn**
      - **MatPlotLib**

---
### Data Cleaning
---

In the initial data preparation phase, I performed the following tasks:
1. Data Loading and Inspection.
2. Handling Missing Values.
3. Data Cleaning and Formatting.

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
