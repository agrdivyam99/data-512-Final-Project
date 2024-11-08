
# DATA-512-FINAL-PROJECT: Wildfire Impact Assessment for Olathe, Kansas

This repository contains the code, data, and analysis for assessing the impact of wildfires on air quality in Olathe, Kansas. The primary focus is to analyze historical wildfire data, calculate smoke exposure estimates, and correlate these estimates with AQI (Air Quality Index) values over time. Additionally, time series models are used to forecast future smoke exposure trends up to 2050.

## Repository Structure

```
DATA-512-FINAL-PROJECT
├── data
│   ├── fire_analysis_olathe.png        # Analysis results of fire data for Olathe
│   ├── olathe_AQI.csv                  # AQI data specific to Olathe
│   ├── olathe_fire_impact_1961_2021.csv   # Historical fire impact data
│   ├── olathe_fire_impact_summary_1961_2021.csv  # Summarized fire impact data
│   ├── olathe_fires_final.json         # Final processed wildfire data for Olathe
│   ├── wildfire_analysis_olathe.png    # Visualization of wildfire analysis for Olathe
│   ├── wildfire_impact_olathe_1961_2021.csv  # Historical wildfire impact data for modeling
├── wildfire
│   ├── code.ipynb                      # Main notebook for data extraction, analysis, and modeling
│   ├── LICENSE                         # License file for the project
│   ├── README.md                       # Project README file (you are here)
│   ├── Report.pdf                      # Final report with refelctions
```

### Folder and File Explanations

- **`data/GeoJSON Exports/`**: Contains wildfire data files sourced from [ScienceBase.gov](https://www.sciencebase.gov/catalog/item/61707c2ad34ea36449a6b066) including comprehensive metadata and datasets.
  
- **`data/`**: Includes both raw and processed data files used in this analysis:
  - `olathe_AQI.csv`: AQI data specific to particulate pollutants for Olathe.
  - `olathe_fire_impact_1961_2021.csv`, `olathe_fire_impact_summary_1961_2021.csv`: Fire impact data summarized for historical analysis.
  - `olathe_fires_final.json`: Filtered JSON files containing only fires within a specified radius of Olathe.
  - `wildfire_impact_olathe_1961_2021.csv`: Annual wildfire impact data used in modeling and forecasting.

- **`wildfire/`**: Contains the main Jupyter notebook, `code.ipynb`, for analysis, model building, and visualization.

## Project Overview

The main objectives of this project are:
1. **Quantify Smoke Impact**: Calculate annual smoke exposure estimates based on the proximity and size of wildfires around Olathe, Kansas.
2. **Correlate Wildfire Activity with AQI**: Analyze how smoke exposure estimates align with historical AQI data to understand potential impacts on air quality.

## Key Methods and Techniques

1. **Data Processing**:
   - **Filtering Fires by Distance**: Fires within specific distance thresholds (e.g., 650 miles) of Olathe are selected to focus on those most likely to impact local air quality.
   - **Annual Aggregation of Smoke Estimates**: Each fire’s smoke impact is calculated based on its size and distance from Olathe, then aggregated yearly to form historical smoke estimates.

2. **Calculating Smoke Impact**:
   The smoke impact for each fire is calculated using the formula:

   **Smoke Impact** = (Fire Size × Scaling Factor) / Distance

   - **Fire Size** represents the area of the fire in acres.
   - **Distance** is the distance of the fire from Olathe in miles.
   - The **Scaling Factor** is used to adjust the measurement. This formula emphasizes that closer fires have a proportionally greater smoke impact on Olathe’s air quality.


## Visualizations

1. **Distribution of Wildfire Distances from Olathe**: A histogram shows the distribution of fires by their distance from Olathe, with key cutoff points to visualize spatial distribution.
   
2. **Annual Total Acres Burned in Olathe**: A line plot shows annual burned acres within a defined radius, highlighting trends and temporal patterns over time.
   
3. **Correlation between Smoke Impact Score and PM2.5 AQI in Olathe**: A line plot overlays smoke exposure estimates with AQI values, showing correlations between wildfire activity and air quality impacts.

## Installation and Usage

### Requirements

- Python 3.x
- Required packages: `pandas`, `numpy`, `matplotlib`, `statsmodels`, `pmdarima`, `geopy`, `fiona`, `shapely`

### Running the Analysis

Clone the repository:
```bash
git clone https://github.com/yourusername/DATA-512-FINAL-PROJECT.git
```

1. Navigate to the project directory and open `code.ipynb` in Jupyter Notebook or Jupyter Lab.
2. Run each cell sequentially to reproduce the analysis, visualizations, and model predictions.


## Acknowledgments

- **Professor’s Resources**: Example notebooks on AQI and wildfire data were instrumental in setting up initial data processing.
- **Libraries and Tools**: Python libraries (`pandas`, `statsmodels`, `matplotlib`) were essential for data analysis and visualization.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
