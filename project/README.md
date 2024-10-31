# Wildfire Data Common Analysis

## Overview
The Wildfire Data Common Analysis project investigates the relationship between wildfire occurrences, smoke estimates, and air quality, specifically focusing on the impacts of wildfires on the designated city, **Boise, Idaho**, in the United States.

## Goal
The primary objective is to answer the research question: **What are the estimated wildfire smoke impacts on Boise, Idaho, each year for the most recent 60 years of wildfire data?** The ultimate goal is to provide actionable insights for policymakers, city managers, city councils, and other civic institutions to inform and guide their planning for future wildfire impacts.

## License
This project utilizes wildfire and air quality data subject to data-sharing policies from relevant sources. It adheres to data-sharing agreements and licensing terms from data providers. Any visualizations or datasets created from this analysis are available under the [Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/deed.en).

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
smoke\_estimate = \frac{GIS\_Hectares}{average\_distance\_miles} \times normalized\_weight_{fire\_type}
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

## API Documentation
The following APIs were used to gather data for this analysis:
- **EPA Air Quality API**: Provides historical air quality index (AQI) measurements.
[Documentation](https://www.google.com/url?q=https%3A%2F%2Faqs.epa.gov%2Faqsweb%2Fdocuments%2Fdata_api.html)

### Jupyter Notebooks
The project includes the following Jupyter notebooks for data collection, processing, and analysis:
1. `epa_air_quality_history.ipynb` - Collects and processes historical air quality data from the EPA with this example code: [Example Code](https://drive.google.com/file/d/1fwS60QStiMDqwINvW2LEDFBX5xg6Wnmg/view?usp=drive_link).
2. `wildfire_geo_proximity.ipynb` - Calculates the proximity of fire occurrences using this example code: [Example Code](https://drive.google.com/file/d/1B7AGlaW7d-27bHKLVXGBwLt8T-Elx-HB/view?usp=drive_link).
3. `smoke_estimate_model.ipynb` - Analyzes smoke estimates based on wildfire data, providing insights into the smoke estimate model.

To reproduce the results, run each notebook sequentially, ensuring file paths are correctly set based on your environment.

### Data Files
1. **Distance Data**
   - **Filename:** `distance.csv`
   - **Description:** Contains distances of wildfire occurrences from a specified reference point to analyze spatial patterns in fire distribution.

2. **EPA Air Quality Data**
   - **Filename:** `epa_air_quality_api_response.csv`
   - **Description:** Contains historical AQI data collected via the EPA API.

### Plot Files
1. **Histogram of Number of Fires by Distance**
   - **Filename:** `histogram_of_number_of_fires_by_distance.png`
   - **Description:** A histogram representing the distribution of fire incidents based on their distance from Boise.

2. **Total Acres Burned per Year**
   - **Filename:** `total_acres_burned_per_year.png`
   - **Description:** A time series plot showing the total area affected by wildfires annually.

3. **Fire, Smoke Estimates, and AQI**
   - **Filename:** `fire_smoke_estimates_and_AQI.png`
   - **Description:** A combined view of fire occurrences, smoke estimate, and AQI data over time, showing correlations between wildfire smoke estimate and AQI data.

### Known Issues or Special Considerations
- **Data Quality and Gaps**: Some datasets may have missing or inconsistent values, particularly in remote sensing smoke estimates, which can affect analysis quality.
- **Accuracy of Distance Calculations**: Distance values depend on accurate geolocation data, and any discrepancies in coordinates may impact proximity analysis.
