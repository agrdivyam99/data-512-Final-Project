
# DATA-512-FINAL-PROJECT: Wildfire Impact Assessment for Olathe, Kansas

This repository contains the complete code, data, and analysis for evaluating the far-reaching impact of wildfires on both air quality and economic stability in Olathe, Kansas. By leveraging historical wildfire data, this project quantifies smoke exposure using a novel Smoke Impact Score and explores its correlation with Air Quality Index (AQI) values and unemployment trends over time. Advanced time-series models are employed to predict future smoke exposure trends up to 2050, providing insights into the long-term risks posed by wildfires. The primary objective is to offer actionable recommendations for policymakers, city planners, and residents to mitigate the environmental and economic consequences of wildfire events, ensuring a resilient and sustainable future for Olathe.

## Repository Structure
```
DATA-512-FINAL-PROJECT
├── data
│   ├── annual_unemployment_rates.csv         # Annual unemployment rates for Olathe, Kansas
│   ├── combined_unemployment_aqi_data.csv    # Combined dataset with AQI, fire impact scores, and unemployment rates
│   ├── olathe_AQI.csv                        # Air Quality Index (AQI) data for Olathe
│   ├── olathe_fire_impact_1961_2021.csv      # Historical fire impact data (1961-2021)
│   ├── olathe_fire_impact_summary_1961_2021.csv  # Summarized fire impact data
│   ├── unemployment_data.xlsx                # Original unemployment dataset from Kansas labor statistics
│   ├── wildfire_impact_olathe_1961_2021.csv  # Refined annual wildfire impact data
│   ├── olathe_fire_final.json                # Filtered JSON files containing only fires within a specified radius of Olathe.
│   ├── predicted_impact_score_data.csv       # Contains the predicted impact scores of future years
├── plots
│   ├── acres_burnt_olathe.png                # Visualizing annual burned acres in Olathe over time
│   ├── correlation_heatmap.png               # Correlation heatmap of key metrics
│   ├── correlation_with_unemployment.png     # Bar plot of factors correlated with unemployment rate
│   ├── fire_impact_vs_burned_acres.png       # Smoke impact score vs burned acres
│   ├── pm25_levels_over_years.png            # Trends of PM2.5 levels (average, median, and peak) over years
│   ├── smoke_days_trend.png                  # Moderate and extreme smoke day trends over the years
│   ├── unemployment_rate_over_years.png      # Trend of unemployment rate over time
│   ├── unemployment_vs_fire_impact_line.png  # Line plot of unemployment rate vs fire impact score
│   ├── unemployment_vs_fire_impact_over_years.png  # Line plot comparing unemployment and fire impact over years
│   ├── unemployment_vs_fire_impact.png       # Scatter plot of unemployment rate vs fire impact score
│   ├── wildfire_analysis_olathe.png          # Distribution of wildfire distances from Olathe
├── wildfire
│   ├── __init__.py                           # Python package initialization file
│   ├── Reader.py                             # Script to read and process wildfire GeoJSON data
│   ├── Wildfire_short_sample_2024.json       # Sample GeoJSON data for testing
├── reports
│   ├── code.ipynb                            # Main notebook for analysis and modeling
│   ├── Report.pdf                            # Final report with findings and recommendations
│   ├── Visualization Explanations.docx       # Detailed visualization explanations
│   ├── README.md                             # Project documentation and introduction
│   ├── LICENSE                               # Project license information

```

## Project Structure

### **data/**
This directory contains both raw and processed datasets used throughout the project, including historical wildfire data, air quality indices (AQI), and unemployment data.

- **annual_unemployment_rates.csv**  
  - **Description:** Contains annual unemployment rates for Olathe, Kansas, derived from the Bureau of Labor Statistics.
  - **Purpose:** Used to analyze economic trends and correlate with wildfire impacts.

- **combined_unemployment_aqi_data.csv**  
  - **Description:** A combined dataset merging AQI, fire impact scores, and unemployment rates.
  - **Purpose:** Used for correlation analysis and generating visualizations.

- **olathe_AQI.csv**  
  - **Description:** Contains annual air quality index (AQI) data specific to Olathe.
  - **Purpose:** Used to measure the environmental impact of wildfires.

- **olathe_fire_impact_1961_2021.csv**  
  - **Description:** Historical data of fire impact scores from 1961 to 2021.
  - **Purpose:** Used for time-series analysis and impact modeling.

- **olathe_fire_final.json**  
  - **Description:** Filtered JSON files containing only fires within a specified radius of Olathe.

- **predicted_impact_score_data.csv**  
  - **Description:** Contains the predicted impact scores of future years

- **olathe_fire_impact_summary_1961_2021.csv**  
  - **Description:** Summarized wildfire data for Olathe, including total acres burned and fire proximity.
  - **Purpose:** Provides input for smoke impact score calculations.

- **unemployment_data.xlsx**  
  - **Description:** Original unemployment data sourced for calculating annual rates for Olathe.
  - **Purpose:** Used for initial preprocessing and calculation of unemployment trends.

- **wildfire_impact_olathe_1961_2021.csv**  
  - **Description:** Refined dataset of wildfire impacts, including distance-adjusted metrics.
  - **Purpose:** Used for generating lagged correlation insights.

---

### **plots/**
Contains all visualizations generated from the analysis. Each plot provides insights into the relationship between wildfires, air quality, and unemployment.

- **acres_burnt_olathe.png**  
  - **Description:** Line chart of annual burned acres over time in Olathe.  
  - **Purpose:** Highlight trends in wildfire activity and scale over time.

- **correlation_heatmap.png**  
  - **Description:** Heatmap of correlations between wildfire metrics, AQI, and unemployment.  
  - **Purpose:** Identify key relationships between environmental and economic variables.

- **correlation_with_unemployment.png**  
  - **Description:** Bar chart of factors correlated with unemployment rate.  
  - **Purpose:** Identify which factors influence unemployment in Olathe.

- **fire_impact_vs_burned_acres.png**  
  - **Description:** Line chart comparing smoke impact score with acres burned.  
  - **Purpose:** Demonstrate how wildfire size affects the computed smoke impact.

- **pm25_levels_over_years.png**  
  - **Description:** Line chart of average, median, and peak PM2.5 levels over time.  
  - **Purpose:** Track air quality trends and link them to wildfire events.

- **smoke_days_trend.png**  
  - **Description:** Line chart showing trends in moderate and extreme smoke days.  
  - **Purpose:** Highlight air quality degradation caused by wildfire smoke.

- **unemployment_rate_over_years.png**  
  - **Description:** Line chart of unemployment rate trends in Olathe.  
  - **Purpose:** Visualize historical economic conditions and shifts.

- **unemployment_vs_fire_impact_line.png**  
  - **Description:** Line chart comparing unemployment rate with fire impact score.  
  - **Purpose:** Explore potential relationships between wildfire impacts and economic outcomes.

- **unemployment_vs_fire_impact_over_years.png**  
  - **Description:** Line chart of unemployment rate and fire impact score trends over time.  
  - **Purpose:** Compare yearly patterns of wildfires and economic conditions.

- **unemployment_vs_fire_impact.png**  
  - **Description:** Scatter plot of unemployment rate vs fire impact score.  
  - **Purpose:** Analyze direct relationships between wildfire impacts and unemployment.

- **wildfire_analysis_olathe.png**  
  - **Description:** Histogram of wildfire distances from Olathe, with a 650-mile threshold.  
  - **Purpose:** Understand the geographic proximity of wildfires and their potential impact on Olathe.


---

### **wildfire/**
This directory contains the core Python and Jupyter notebooks used for data extraction, analysis, and modeling.

- **code.ipynb**  
  - **Description:** Main notebook for executing data preprocessing, analysis, and modeling.
  - **Purpose:** Serves as the primary implementation file for this project.

- **Reader.py**  
  - **Description:** Python script for reading and parsing wildfire GeoJSON files.  
  - **Purpose:** Automates data extraction from raw datasets.

- **Wildfire_short_sample_2024.json**  
  - **Description:** Sample GeoJSON file containing wildfire data for testing.  
  - **Purpose:** Used for validating the code pipeline with smaller datasets.

---

### **Project Files**

- **README.md**  
  - **Description:** Documentation explaining the project structure, purpose, and key findings.  
  - **Purpose:** Serves as an entry point for understanding the repository.

- **LICENSE**  
  - **Description:** Licensing information for the project.  
  - **Purpose:** Ensures proper use and attribution of project resources.

- **Report.pdf**  
  - **Description:** Final comprehensive report detailing the analysis, findings, and recommendations.  
  - **Purpose:** Submitted as the final deliverable for the project.

- **Visualization Explanations.docx**  
  - **Description:** Word document providing detailed descriptions for all visualizations.  
  - **Purpose:** Supplements the report by explaining each visualization’s significance.


## **Project Overview**

The main objectives of this project are:

1. **Quantify Smoke Impact**: Calculate annual smoke exposure estimates based on the proximity and size of wildfires around Olathe, Kansas.
2. **Correlate Wildfire Activity with Economic and Environmental Metrics**: Analyze how smoke exposure estimates align with historical unemployment rates and AQI data to explore potential impacts.

## **Key Methods and Techniques**

### **Data Processing**
1. **Wildfire Data**:
   - Sourced from the USGS dataset covering fires within a 650-mile radius of Olathe (1965–2020).
   - Focused on metrics such as burned acres, proximity, and fire severity.

2. **Unemployment Data**:
   - Collected annual unemployment rates for Olathe from the Kansas Department of Labor.

3. **Air Quality Data**:
   - Integrated PM2.5 levels from the Environmental Protection Agency for comparative smoke analysis.

### **Metrics**
1. **Smoke Impact Score**:
   - **Formula**: `Smoke Impact = (Fire Size × Scaling Factor) / Distance`
   - Adjusted with factors such as cube root normalization, proximity weighting, and severity adjustments for fires >100,000 acres.

2. **Lagged Correlation**:
   - Explored temporal relationships between wildfires and unemployment rates over multiple years to uncover delayed impacts.

### **Forecasting Model**
- **ARIMA (Autoregressive Integrated Moving Average)**:
   - Used for time-series predictions of Smoke Impact Scores.
   - Modeled trends from 2024–2050 with confidence intervals to guide long-term planning.

## **Visualizations**

 **1. Distribution of Wildfire Distances from Olathe**
- **Purpose**: Understand the geographic distribution of wildfires and their proximity to Olathe.  
- **Visualization**: A histogram showing the frequency of wildfires at different distances, with a cutoff threshold of 650 miles marked to highlight the fires most likely to impact air quality in Olathe.

 **2. Trends in Annual Burned Acres**
- **Purpose**: Highlight wildfire activity over time, focusing on long-term trends.  
- **Visualization**: A line graph illustrating annual burned acres within a 650-mile radius of Olathe, with a significant increase in activity post-2000.

 **3. AQI vs Smoke Impact**
- **Purpose**: Analyze how wildfire activity influences air quality in Olathe.  
- **Visualization**: A boxplot comparing Smoke Impact Scores with AQI values for PM2.5, showing variability in air quality impacts from wildfire events.

 **4. Lagged Correlation Between Wildfires and Unemployment**
- **Purpose**: Reveal delayed economic impacts of wildfire events on unemployment in Olathe.  
- **Visualization**: A bar chart of lagged correlations, peaking at a 2-year lag, indicating significant delayed effects of wildfires on unemployment rates.

 **5. Fire Impact Score vs Burned Acres**
- **Purpose**: Examine the relationship between wildfire size and its calculated Smoke Impact Score.  
- **Visualization**: A scatter plot showing a positive linear relationship between burned acres and the impact score.

 **6. Unemployment Rate Over the Years**
- **Purpose**: Track economic trends and variations in unemployment over time in Olathe.  
- **Visualization**: A line chart displaying annual unemployment rates from 2000 to 2020, revealing periods of economic distress.

 **7. Unemployment Rate vs Fire Impact Score**
- **Purpose**: Directly compare unemployment rates with annual wildfire impact scores.  
- **Visualization**: A line graph overlaying unemployment rates and fire impact scores, showing potential correlations and shared trends.


## **Findings and Implications**

1. **Wildfires Have Delayed Economic Effects**:
   - Strong lagged correlation (0.54) between wildfire activity and unemployment rates after 2 years.

2. **Smoke Impacts Air Quality Variably**:
   - While higher Smoke Impact Scores align with elevated AQI levels, additional factors like weather influence air quality.

3. **Policy Recommendations**:
   - **Economic Resilience**: Invest in less wildfire-dependent industries.
   - **Workforce Support**: Create recovery initiatives and training programs.
   - **Enhanced Monitoring**: Deploy real-time air quality tracking and smoke modeling tools.

4. **Future Planning**:
   - Incorporate wildfire risks into economic and urban development strategies.


## **Installation and Usage**

### **Requirements**
- Python 3.x
- Required Packages: `pandas`, `numpy`, `matplotlib`, `statsmodels`, `pmdarima`, `geopy`, `fiona`, `shapely`

### **Steps**
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/DATA-512-FINAL-PROJECT.git
2. Navigate to the project directory and open `code.ipynb` in Jupyter Notebook or Jupyter Lab.
3. Run each cell sequentially to reproduce the analysis, visualizations, and model predictions.


## Acknowledgments

- **Professor’s Resources**: Example notebooks on AQI and wildfire data were instrumental in setting up initial data processing.
- **Libraries and Tools**: Python libraries (`pandas`, `statsmodels`, `matplotlib`) were essential for data analysis and visualization.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
