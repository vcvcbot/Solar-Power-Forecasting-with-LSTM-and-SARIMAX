# Solar Power Analysis and Forecasting

## Project Overview

This project aims to provide a comprehensive analysis, forecasting, and fault detection system for solar power generation data. By integrating generation and weather sensor data, we apply various machine learning and time series models to understand the operational patterns of solar power plants and identify potential anomalies. The main objectives include:

*   **Data Integration and Preprocessing**: Combining generation and weather data from different sources and performing data cleaning.
*   **Feature Engineering**: Extracting useful temporal and environmental features from raw data.
*   **Power Generation Forecasting**: Utilizing SARIMAX and LSTM models for both short-term and long-term solar power generation prediction.
*   **Equipment Fault Detection**: Employing statistical methods, Isolation Forest, and K-Means clustering analysis to identify anomalous inverter behavior or potential equipment malfunctions.

## Project Features

*   **Comprehensive Data Analysis**: Combines power generation data with environmental data (e.g., temperature, irradiation).
*   **Advanced Forecasting Models**: Implements two powerful time series forecasting models: SARIMAX and LSTM.
*   **Multiple Fault Detection Mechanisms**: Utilizes statistical analysis, Isolation Forest, and K-Means clustering to enhance the accuracy of fault detection.
*   **Visualizations**: Clearly presents data trends, model prediction results, and fault detection findings through various plots and charts.

## Dataset Used

This project uses the "Solar Power Generation Data" dataset from KaggleHub. This dataset includes generation data and weather sensor data for two solar power plants, covering several months, providing rich information for analysis and modeling.

## Methodology

### 1. Data Loading and Preprocessing

*   Download and load generation data (`Generation_Data.csv`) and weather sensor data (`Weather_Sensor_Data.csv`) for Plant 1 and Plant 2 from KaggleHub.
*   Convert datetime columns to a standard format.
*   Merge generation and weather data.
*   Calculate conversion efficiency (`EFFICIENCY = AC_POWER / DC_POWER`) and clean invalid or anomalous values.

### 2. Feature Engineering

*   Extract temporal features such as hour, day of the week, day of the year, and month from the datetime index.
*   Calculate the difference between module temperature and ambient temperature (`temp_diff`).
*   Calculate irradiation per unit temperature (`irradiation_per_temp`).

### 3. Power Generation Forecasting

*   **SARIMAX Model**:
    *   Suitable for time series data with seasonal trends.
    *   Used for short-term forecasting, capturing autocorrelation in the data.
*   **LSTM Model**:
    *   Long Short-Term Memory network, a type of recurrent neural network adept at handling sequential data.
    *   Used for long-term forecasting, capable of learning complex temporal dependencies in the data.
    *   Data is standardized using MinMaxScaler and structured into sequences suitable for LSTM input.

### 4. Equipment Fault Detection

*   **Statistical Analysis**: Identifies inverters with abnormal generation or efficiency.
*   **Isolation Forest**: A tree-based anomaly detection algorithm used to identify outliers in the data.
*   **K-Means Clustering**: Clusters inverter data and identifies the cluster with the lowest efficiency as potentially faulty.

## Installation and Running

### Environment Requirements

This project requires the following Python libraries:

*   `kagglehub`
*   `pandas`
*   `numpy`
*   `matplotlib`
*   `seaborn`
*   `scikit-learn`
*   `statsmodels`
*   `tensorflow`

You can install all dependencies using the following command:

```bash
pip install kagglehub pandas numpy matplotlib seaborn scikit-learn statsmodels tensorflow
```

### How to Run

1.  **Clone the Repository**:
    ```bash
    git clone <Your GitHub Repository URL>
    cd <Your Project Directory>
    ```
2.  **Run the Jupyter Notebook**:
    ```bash
    jupyter notebook Solar_Power_Analysis_LSTM.ipynb
    ```
    Within the Jupyter environment, you can execute all cells in the Notebook step-by-step to reproduce the analysis and results.

## Contributing

Contributions to this project are welcome! If you have any suggestions, bug reports, or feature requests, please feel free to open an Issue or submit a Pull Request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

