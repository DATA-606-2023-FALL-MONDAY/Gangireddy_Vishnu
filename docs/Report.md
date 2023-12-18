 ## 1. Title and Author
- Title - Vishnu Fall 2023 Final project report
- Project Title - Analysis of Uber & Lyft ride details
- Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang
- Link to the author's GitHub profile - https://github.com/vishnu-50213
- Link to the author's LinkedIn progile - https://www.linkedin.com/in/vishnu-vardhan-reddy-gangireddy-60226b235/
- Link to your PowerPoint presentation file - https://github.com/DATA-606-2023-FALL-MONDAY/Gangireddy_Vishnu/blob/main/docs/FINAL%20PRESENTATION.pptx
- Link to your YouTube video -
    
## 2. Background

Provide the background information about the chosen topic. 

- What is it about? 
-   This analysis centers on the comprehensive examination of trip details sourced from two major ride-hailing platforms, Uber and Lyft. The primary focus is to elucidate the determinants governing ride pricing dynamics and the quality of service experienced by passengers. It entails a meticulous investigation into the intricate interplay between ride-hailing operations and meteorological factors, with a view to uncovering how weather conditions influence ride costs, durations, and overall customer satisfaction.
- Why does it matter? 

-   The significance of this analysis is underscored by its potential to impart valuable insights to diverse stakeholders, encompassing ride-hailing enterprises, riders, and regulatory bodies. Several compelling reasons underscore the importance of this research:

-    Pricing Transparency: The elucidation of weather's influence on ride pricing equips passengers with knowledge to make judicious choices, enhancing transparency and predictability in their travel expenditures.

-    Operational Efficacy: For ride-hailing companies such as Uber and Lyft, a deeper comprehension of weather-induced demand patterns augments the efficiency of resource allocation and pricing strategies.

-    Weather Resilience: Insights into the repercussions of different meteorological conditions on ride durations and routes inform strategies for developing more resilient and adaptive transportation systems.
- What are your research questions?
-   In the context of this analysis that delves into Uber and Lyft trip details alongside meteorological data, a series of pertinent research inquiries emerge:

-    How does meteorological variation exert an influence on ride pricing for Uber and Lyft? - This central question seeks to establish the correlation between distinct weather conditions (e.g., precipitation, temperature extremes) and the resultant fluctuations in ride costs.

-    Which specific meteorological variables wield the most pronounced influence on ride pricing dynamics? - This question endeavors to pinpoint the key meteorological determinants (e.g., precipitation intensity, temperature variations) that wield a substantial impact on ride pricing.

-    Is it feasible to develop predictive models capable of forecasting ride prices contingent upon forthcoming weather forecasts? - This inquiry examines the feasibility of constructing predictive models that anticipate ride costs based on forecasted meteorological conditions.

-    How do meteorological conditions engender alterations in ride durations and route selection? - This research query scrutinizes the ramifications of weather conditions on the temporal and spatial dimensions of rides, inclusive of potential route diversions attributed to meteorological exigencies.

## 3. Data 

Describe the datasets you are using to answer your research questions.

- Data sources - https://www.kaggle.com/datasets/brllrb/uber-and-lyft-dataset-boston-ma
- Data size (MB, GB, etc.) - Around 300 MB
- Data shape (# of rows and # columns) - 693070 of rows and 57 columns
- Time period (for example, 2010 to 2020) if your data are time-bound - 11-26-2018 to 12-18-2018 and Location - Uber and Lyft Dataset Boston, MA
- **What does each row represent?(a patient, a school, a crime, etc.)**
- Data dictionary
  - Columns name
  - Data type
  - Defition
  - Potential values (for categorical valuables, what are the categories?)

| **Column Name**              | **Data Type** | **Definition**                                          | **Potential Values**                                                                                                     |
|-----------------------------|---------------|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| `id`                        | `object`      | Unique identifier for each ride.                       | -                                                                                                                         |
| `timestamp`                 | `float64`     | Timestamp for the ride.                                | -                                                                                                                         |
| `hour`                      | `int64`       | The hour component of the timestamp.                  | 0 to 23                                                                                                                   |
| `day`                       | `int64`       | The day component of the timestamp.                   | 1 to 31                                                                                                                   |
| `month`                     | `int64`       | The month component of the timestamp.                 | 1 to 12                                                                                                                   |
| `datetime`                  | `object`      | Date and time of the ride.                            | -                                                                                                                         |
| `timezone`                  | `object`      | Timezone information.                                  | -                                                                                                                         |
| `source`                    | `object`      | Pickup location.                                       | Categorical values                                                                                                        |
| `destination`               | `object`      | Drop-off location.                                     | Categorical values                                                                                                        |
| `cab_type`                  | `object`      | Type of ride-hailing service (Uber or Lyft).          | Categorical values (Uber, Lyft)                                                                                           |
| `product_id`                | `object`      | Identifier for the specific ride product.             | -                                                                                                                         |
| `name`                      | `object`      | Name of the ride product.                             | -                                                                                                                         |
| `price`                     | `float64`     | Ride price.                                            | Numeric values (may be missing)                                                                                          |
| `distance`                  | `float64`     | Distance of the ride.                                 | Numeric values                                                                                                           |
| `surge_multiplier`          | `float64`     | Surge pricing multiplier.                              | Numeric values                                                                                                           |
| `latitude`                  | `float64`     | Latitude coordinate.                                   | Numeric values                                                                                                           |
| `longitude`                 | `float64`     | Longitude coordinate.                                  | Numeric values                                                                                                           |
| `temperature`               | `float64`     | Temperature.                                          | Numeric values                                                                                                           |
| `apparentTemperature`       | `float64`     | Apparent temperature.                                 | Numeric values                                                                                                           |
| `short_summary`             | `object`      | Short summary of weather conditions.                  | Categorical values                                                                                                        |
| `long_summary`              | `object`      | Detailed summary of weather conditions.               | Categorical values                                                                                                        |
| `precipIntensity`           | `float64`     | Precipitation intensity.                              | Numeric values                                                                                                           |
| `precipProbability`         | `float64`     | Probability of precipitation.                         | Numeric values                                                                                                           |
| `humidity`                  | `float64`     | Humidity level.                                       | Numeric values                                                                                                           |
| `windSpeed`                 | `float64`     | Wind speed.                                           | Numeric values                                                                                                           |
| `windGust`                  | `float64`     | Wind gust.                                            | Numeric values                                                                                                           |
| `windGustTime`              | `int64`       | Time of the wind gust.                                | Integer values                                                                                                           |
| `visibility`                | `float64`     | Visibility.                                           | Numeric values                                                                                                           |
| `temperatureHigh`           | `float64`     | Highest temperature.                                  | Numeric values                                                                                                           |
| `temperatureHighTime`       | `int64`       | Time of the highest temperature.                      | Integer values                                                                                                           |
| `temperatureLow`            | `float64`     | Lowest temperature.                                   | Numeric values                                                                                                           |
| `temperatureLowTime`        | `int64`       | Time of the lowest temperature.                       | Integer values                                                                                                           |
| `apparentTemperatureHigh`   | `float64`     | Apparent highest temperature.                         | Numeric values                                                                                                           |
| `apparentTemperatureHighTime`| `int64`       | Time of the apparent highest temperature.             | Integer values                                                                                                           |
| `apparentTemperatureLow`    | `float64`     | Apparent lowest temperature.                          | Numeric values                                                                                                           |
| `apparentTemperatureLowTime`| `int64`       | Time of the apparent lowest temperature.              | Integer values                                                                                                           |
| `icon`                      | `object`      | Icon representing weather conditions.                  | Categorical values                                                                                                        |
| `dewPoint`                  | `float64`     | Dew point.                                            | Numeric values                                                                                                           |
| `pressure`                  | `float64`     | Air pressure.                                         | Numeric values                                                                                                           |
| `windBearing`               | `int64`       | Wind bearing.                                         | Integer values                                                                                                           |
| `cloudCover`                | `float64`     | Cloud cover.                                          | Numeric values                                                                                                           |
| `uvIndex`                   | `int64`       | UV index.                                             | Integer values                                                                                                           |
| `visibility.1`              | `float
- Which variable/column will be your target/label in your ML model? - price
- Which variables/columns may be selected as features/predictors for your ML models? - Not yet decided

## 4. Exploratory Data Analysis (EDA)

- Find out if the data require cleansing:
  - Duplicate rows? - None

### 1. Data Exploration

- In this phase of the project, I conducted an extensive Exploratory Data Analysis (EDA) using Jupyter Notebook, focusing on the target variable and selected features while excluding irrelevant columns. The primary goal was to gain a comprehensive understanding of the dataset and extract meaningful insights for further analysis.

#### 1.1 Target Variable and Selected Features

- The target variable for my analysis is the "price," representing the cost of the trip. The selected features include various categorical and continuous variables such as cab type, weather conditions, distance, and starting locations.

#### 1.2 Summary Statistics

- I computed summary statistics for key variables using the `describe` function, providing insights into the central tendency, dispersion, and shape of the distribution. Additionally, I generated histograms to visualize the distribution of numeric variables, offering a more intuitive understanding.

#### 1.3 Visualizations with Plotly Express

- To enhance data exploration, I employed Plotly Express for creating interactive visualizations. Bar plots, pie charts, and bar graphs were utilized to illustrate distributions, relationships, and patterns within the data. The visualizations provide a clear representation of the data, aiding in the identification of trends and outliers.

### 2. Data Cleansing

####  Missing Values

- I assessed the dataset for missing values to ensure data integrity. In case of any missing values, appropriate strategies were employed, such as imputation or removal, to maintain the quality of the dataset.


### 3. Data Transformation

#### Feature Engineering

- I introduced a new variable, "Price per Mile (PPM)," calculated as the ratio of price to distance. This variable serves as a standardized measurement for observations, providing valuable insights into pricing dynamics.
![Visualization](https://github.com/DATA-606-2023-FALL-MONDAY/Gangireddy_Vishnu/blob/main/docs/Images/newplot.png)
![Visualization](https://github.com/DATA-606-2023-FALL-MONDAY/Gangireddy_Vishnu/blob/main/docs/Images/newplot-2.png)


### 4. Tidiness of the Dataset

- Ensuring the dataset is tidy is imperative for effective analysis. Each row represents a unique observation, and each column corresponds to a distinct property of that observation. This tidy format facilitates seamless integration into predictive analysis and machine learning models.

### Conclusion

The EDA phase has provided valuable insights into the dataset, laying the foundation for further analysis and modeling. The clean and enriched dataset, along with meaningful visualizations, sets the stage for predictive analysis and machine learning tasks in the next phases of the project.



## 8. References 

- https://www.kaggle.com/datasets/brllrb/uber-and-lyft-dataset-boston-ma
