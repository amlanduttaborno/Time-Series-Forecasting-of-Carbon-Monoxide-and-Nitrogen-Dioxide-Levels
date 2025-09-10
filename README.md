# Time-Series Forecasting of Carbon Monoxide and Nitrogen Dioxide Levels

## Project Overview
This project focuses on building predictive models to forecast daily concentrations of Carbon Monoxide (CO) and Nitrogen Dioxide (NO₂) based on historical air quality data. The goal is to provide accurate predictions and actionable insights for environmental monitoring and public health advisories.

## Dataset
- **Source**: Air quality dataset containing hourly measurements of various pollutants and meteorological factors
- **Target Variables**: CO(GT) and NO2(GT) concentrations
- **Features**: Temperature, humidity, absolute humidity, and various sensor readings
- **Time Period**: Multiple years of hourly measurements

## Project Workflow

### 1. Data Preprocessing
- **Date-Time Parsing**: Combined Date and Time columns into a single datetime index
- **Resampling**: Aggregated hourly data into daily averages for more stable forecasting
- **Missing Value Handling**: Used linear interpolation followed by mean imputation for remaining missing values
- **Outlier Treatment**: Capped extreme values using 1st and 99th percentiles to improve model stability

### 2. Exploratory Data Analysis (EDA)
- **Trend Analysis**: Visualized long-term patterns in CO and NO₂ levels
- **Seasonality Analysis**: Identified monthly patterns using boxplots to understand seasonal variations
- **Correlation Analysis**: Examined relationships between pollutants and environmental factors using heatmaps

### 3. Feature Engineering
- **Lag Features**: Created lag variables (1-day, 2-day, 3-day) to capture temporal dependencies
- **Time-Based Features**: Added day of week, month, and weekend indicators
- **Environmental Predictors**: Incorporated temperature, relative humidity, and absolute humidity as features

### 4. Model Development
**Approach 1: ARIMA (Univariate)**
- Used for CO(GT) forecasting
- Parameters: (3,1,2) order after experimentation

**Approach 2: Random Forest (Multivariate)**
- Used for NO₂(GT) forecasting
- Incorporated lag features and environmental predictors
- 100 estimators with random state for reproducibility

### 5. Model Evaluation
**Evaluation Metrics:**
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Percentage Error (MAPE)

**Performance:**
- CO(GT) ARIMA: Achieved competitive error metrics on test data
- NO₂(GT) Random Forest: Demonstrated strong predictive performance

### 6. Forecasting & Visualization
- Generated 7-day forecasts for both pollutants
- Created visualizations showing historical trends and future predictions
- Implemented iterative forecasting for multivariate approach

### 7. Insights & Recommendations
- **High Concentration Alerts**: Implemented threshold-based warnings for unsafe levels
- **Seasonal Patterns**: Identified periods of typically higher pollution
- **Mitigation Strategies**: Suggested traffic restrictions and public advisories based on forecasts

## Technical Implementation
- **Programming Language**: Python
- **Key Libraries**: pandas, numpy, matplotlib, seaborn, statsmodels, scikit-learn
- **Time Series Techniques**: ARIMA, lag features, seasonal decomposition
- **Machine Learning**: Random Forest regression

## Results
The project successfully:
- Built accurate forecasting models for both pollutants
- Provided visualizations of trends and predictions
- Delivered actionable insights for environmental management
- Established a framework for ongoing air quality monitoring

## Usage
The code can be adapted for:
- Environmental monitoring systems
- Urban planning and pollution control
- Public health advisory systems
- Research on air quality patterns
