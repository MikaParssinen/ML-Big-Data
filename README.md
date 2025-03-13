# ✈️ Flight Delay Prediction

A machine learning project that predicts flight delays using Apache Spark and PySpark ML. This project analyzes the 2008 American Airlines dataset to identify factors that contribute to flight delays and builds a predictive model using linear regression.

## 📑 Table of Contents
- [Overview](#overview)
- [Key Features](#key-features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Methodology](#methodology)
- [Results](#results)
- [Future Work](#future-work)

## 🔍 Overview

Flight delays are a persistent issue in air travel, causing inconvenience for passengers and significant economic consequences for airlines. This project uses big data tools and machine learning techniques to analyze flight data and develop predictive models for flight delays.

The model achieved an R² value of 0.9739 and RMSE of 17.45 minutes, demonstrating strong predictive performance, especially for shorter delays.

## ⭐ Key Features

- Data preprocessing and cleaning of flight information
- Feature selection and engineering to identify key delay factors
- Linear regression modeling with hyperparameter tuning
- Comprehensive evaluation metrics and visualizations
- Temporal analysis of delay patterns by day of week and month
- Carrier performance analysis

## 🔧 Requirements

- Python 3.7+
- Apache Spark 3.0+
- PySpark
- Pandas
- NumPy
- Matplotlib
- Seaborn

## 📥 Installation

1. Clone this repository:
```bash
git clone https://github.com/MikaParssinen/ML-Big-Data.git
cd ML-Big-Data
```

2. Install the required packages:
```bash
pip install pyspark pandas numpy matplotlib seaborn
```

3. Install Jupyter if you don't have it already:
```bash
pip install jupyter
```

4. Download the 2008 American Airlines dataset:
   - Download from [Kaggle](https://www.kaggle.com/datasets/artomas/us-flights/data)
   - Place the CSV file in the `Dataset` directory

## 🚀 Usage

Run the Jupyter notebook to perform the complete analysis:

```bash
jupyter notebook code.ipynb
```

You can run the notebook cells sequentially to:
1. Load and explore the dataset
2. Preprocess the data
3. Train the linear regression model
4. Evaluate model performance
5. Visualize results

You can also run individual cells to execute specific parts of the analysis.

## 📁 Project Structure

- `project/report`: LaTeX code for the report
- `project/work/code/code.ipynb`: Jupyter notebook containing the complete analysis
- `project/Dataset/`: Directory for storing the flight data CSV
- `README.md`: This documentation file

## 🔬 Methodology

### 🧹 Data Preprocessing
- Removal of unnecessary columns and cancelled flights
- Handling of missing values in key fields
- Creation of a "TotalDelay" feature combining different types of delays

### 🔎 Feature Selection
Based on correlation analysis and domain knowledge, the following features were selected:
- Departure Delay
- Distance
- Taxi-In Time
- Taxi-Out Time
- Carrier Delay
- Weather Delay

### 🤖 Model Development
- Linear Regression with PySpark ML
- Hyperparameter tuning using CrossValidator with 3-fold cross-validation
- Grid search for optimal RegParam and ElasticNetParam values

### 📊 Evaluation
- Performance metrics: RMSE, MAE, R², MSE
- Feature importance analysis
- Residual analysis
- Performance analysis across different delay ranges

## 📈 Results

The model achieved:
- R² value of 0.9739
- RMSE of 17.45 minutes
- MAE of 11.88 minutes

Feature importance analysis revealed:
- Departure delay was the most significant predictor (coefficient: 2.88)
- Followed by taxi-out time (1.41) and taxi-in time (1.27)
- Weather delays (0.15) and carrier delays (0.10) showed smaller influences
- Distance had minimal impact (-0.004)

The model performed better for shorter delays:
- Very Low Delays: MAE of 8.95 minutes
- Low Delays: MAE of 8.01 minutes
- Medium Delays: MAE of 8.93 minutes
- High Delays: MAE of 14.45 minutes
- Very High Delays: MAE of 19.53 minutes

Temporal analysis identified peak delay periods:
- Highest average delays on Day 5 (Friday): 10.95 minutes
- December had the highest monthly delays: 16.68 minutes

## 🔮 Future Work

- Enhanced Feature Engineering: Incorporate additional features such as detailed weather data, airport congestion metrics, and seasonal patterns
- Advanced Modeling Techniques: Explore non-linear models or ensemble methods for better capturing complex relationships
- Real-time Prediction: Develop a system for real-time delay prediction by incorporating live data feeds

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
