# Exploring the Human-Centered Impact of Air Quality on Boise's Economic Performance

## Overview
This project investigates the relationship between air quality and economic performance in Boise, Idaho, focusing on how wildfires, air quality index (AQI), and key economic factors such as GDP, unemployment rates, and Micron Technology’s stock prices interact. The analysis includes correlation analysis, predictive modeling, and forecasting of Boise’s economic future based on these relationships.

## Goal
The main research question is: **How does the relationship between air quality and economic performance manifest in Boise?** This question is significant because it explores the intersection of environmental science and economics. Poor air quality not only decreases workforce productivity and increases healthcare burdens but also disrupts corporate operations and weakens investor confidence, threatening economic stability.

## License
This project utilizes wildfire and air quality data subject to data-sharing policies from relevant sources. It adheres to data-sharing agreements and licensing terms from data providers. Historical stock price data for Micron Technology will be sourced from Yahoo Finance. This dataset is available for educational and research purposes, but users must comply with Yahoo Finance’s terms regarding commercial use. The GDP dataset from FRED is available for research and educational use, provided appropriate citations are made. Any visualizations or datasets created from this analysis are available under the [Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/deed.en).

## Data Sources

1. **Boise GDP Data**
: Sourced from FRED (Federal Reserve Economic Data). [Boise GDP Data FRED](https://fred.stlouisfed.org/series/RGMP14260)

2. **Wildland Fire Dataset**: Based on the Combined Wildland Fire Datasets for the United States and Certain Territories (1800s-Present), collected by the US Geological Survey. [Access the dataset here](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81)

3. **Unemployment Rates**: Obtained from local workforce statistics. [Unemployment Rates - Bureau of Labor Statistics](https://www.bls.gov/eag/eag.id_boisecity_msa.htm)

4. **Micron Stock Prices**: Historical stock price data from Yahoo Finance. [Micron Stock Prices - Yahoo Finance](https://finance.yahoo.com/quote/MU/)


## Project Structure

### Step 0: Data Acquisition
The common analysis is based on the **Combined Wildland Fire Datasets for the United States and Certain Territories (1800s-Present)** collected by the US Geological Survey. You can access the dataset [here](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81).

### Step 1: Create Fire Smoke Estimates
To create annual estimates of wildfire smoke for Boise, Idaho:
- Consider only the last 60 years of wildland fire data (1961-2021).
- Include fires within 650 miles of the city.
- Define the annual fire season as running from May 1st through October 31st.

#### Smoke Estimation Model
A smoke estimation model is developed using the following formula:

$$
smoke\_estimate = \frac{GIS Hectares}{average\_distance\_miles} \times normalized\_weight_{fire\_type}
$$

- **GIS_Hectares**: The area affected by wildfires measured in hectares.
- **average_distance_miles**: The average distance from the wildfire to Boise in miles.
- **normalized_weight_{fire\_type}**: A weight assigned to different fire types, based on the weight found using GIS_Hectares.

This formula incorporates the normalized weight for fire type, calculated based on the assumption that fire size is highly correlated with smoke levels produced by different types of wildfires. By utilizing this weight, we can estimate smoke levels more accurately. The resulting smoke estimates are then merged with AQI data for further analysis and comparison to assess the model's accuracy.

### Step 2: Visualizations
I produced the following visualizations within this analysis:
- A histogram showing the number of fires occurring at intervals of 50 miles up to 1800 miles from Boise.
- A time series graph of total acres burned per year from fires within the specified distance.
- A time series graph comparing fire smoke estimates and AQI estimates for Boise.

### Step 3: Human-Centered Data Science (HCDS) Analysis
The next phase of the analysis focuses on how the data can be used to address the impacts of air quality on Boise’s economy and public health. Human-centered data science (HCDS) principles guide the interpretation of the results, ensuring that the findings are relevant to the community’s well-being.

### Step 4: Correlation and Predictive Modeling
After conducting exploratory data analysis and visualizations, the next step is to perform a correlation analysis to identify relationships between air quality and economic performance. A polynomial regression model is then used to predict Boise’s GDP, considering factors like AQI, unemployment rates, and Micron’s stock performance. These predictions are used to forecast the city’s economic future under varying air quality conditions.

### Step 5: Forecasting and Long-Term Implications
Using the polynomial regression model and exponential smoothing, projections are made for Boise’s GDP over the next 25 years, incorporating anticipated trends in AQI, unemployment rates, and Micron’s stock prices. The results help predict long-term economic impacts and inform policymakers about potential future economic stability under different environmental scenarios.

### Step 6: Final Recommendations
Based on the analysis and model predictions, final recommendations are made for policymakers, businesses, and residents:
- Policymakers: Strategies to mitigate wildfire impacts and improve air quality management.
- Residents: Encouraging individual actions to reduce emissions and support sustainability initiatives.
- Businesses: Recommendations for implementing remote work policies and air filtration systems.

## API Documentation
The following APIs were used to gather data for this analysis:
- **EPA Air Quality API**: Provides historical air quality index (AQI) measurements.
[Documentation](https://www.google.com/url?q=https%3A%2F%2Faqs.epa.gov%2Faqsweb%2Fdocuments%2Fdata_api.html)

## Jupyter Notebooks
The project includes the following Jupyter notebooks for data collection, processing, and analysis:
1. `epa_air_quality_history.ipynb` - Collects and processes historical air quality data from the EPA with this example code: [Example Code](https://drive.google.com/file/d/1fwS60QStiMDqwINvW2LEDFBX5xg6Wnmg/view?usp=drive_link).
2. `wildfire_geo_proximity.ipynb` - Calculates the proximity of fire occurrences using this example code: [Example Code](https://drive.google.com/file/d/1B7AGlaW7d-27bHKLVXGBwLt8T-Elx-HB/view?usp=drive_link).
3. `smoke_estimate_model.ipynb` - Analyzes smoke estimates based on wildfire data, providing insights into the smoke estimate model.
4. `correlation_analysis_prediction.ipynb`- Performs correlation analysis to explore relationships between air quality and economic indicators, and uses predictive modeling to forecast Boise’s economic performance.

To reproduce the results, run each notebook sequentially, ensuring file paths are correctly set based on your environment.

## Data Files
1. **Distance Data**
   - **Filename:** `distance.csv`
   - **Description:** Contains distances of wildfire occurrences from a specified reference point to analyze spatial patterns in fire distribution.

2. **EPA Air Quality Data**
   - **Filename:** `epa_air_quality_api_response.csv`
   - **Description:** Contains historical AQI data collected via the EPA API.

## Plot Files
1. **Histogram of Number of Fires by Distance**
   - **Filename:** `histogram_of_number_of_fires_by_distance.png`
   - **Description:** A histogram representing the distribution of fire incidents based on their distance from Boise.

2. **Total Acres Burned per Year**
   - **Filename:** `total_acres_burned_per_year.png`
   - **Description:** A time series plot showing the total area affected by wildfires annually.

3. **Fire, Smoke Estimates, and AQI**
   - **Filename:** `fire_smoke_estimates_and_AQI.png`
   - **Description:** A combined view of fire occurrences, smoke estimate, and AQI data over time, showing correlations between wildfire smoke estimate and AQI data.

4. **Correlation Analysis**
   - **Filename:** correlation_analysis.png
   - **Description:** A plot shows the relationships between GDP, and air quality, unemployment rates, and Micron's stock performance.

5. **GDP Prediction**
   - **Filename:** gdp_prediction.png
   - **Description:** A plot forecasts Boise's GDP over the next 25 years, factoring in air quality, unemployment rates, and Micron's stock performance, demonstrating the long-term economic impact of air quality.

   
## Known Issues or Special Considerations
- **Data Quality and Gaps**: Some datasets may have missing or inconsistent values, particularly in remote sensing smoke estimates, which can affect analysis quality.
- **Accuracy of Distance Calculations**: Distance values depend on accurate geolocation data, and any discrepancies in coordinates may impact proximity analysis.
