AI and IoT-Enabled Smart Gardening System

An automated smart gardening system that integrates a handheld spectrometer with Raspberry Pi to measure spectral responses of plants and estimate soil moisture using machine learning regression. The system achieves **98.81% prediction accuracy** using Random Forest model.

Overview

A spectrometer-based system that captures 18-band spectral reflectances (410nm-940nm) from plant leaves along with environmental data to predict soil moisture levels accurately. The system processes data locally on Raspberry Pi, enabling real-time decision-making for precision agriculture.

Problem Statement

Traditional gardening relies on manual inspection and basic sensors, which are time-consuming, inaccurate, and unsuitable for large-scale operations. This leads to inefficient irrigation, delayed disease detection, and improper chemical application. Farmers need an intelligent, real-time monitoring system that works even in low-connectivity areas.

System Architecture

The system consists of:

- Spectrometer: Captures spectral reflectance data across 18 wavelength bands (410nm-940nm)
- Soil Moisture Sensor: Measures actual soil water content
- DHT22 Sensor: Monitors temperature and humidity
- ADS1115 ADC: Converts analog sensor signals to digital
- Raspberry Pi 4: Acts as edge computing device for data processing and ML inference

Dataset

- File: `final dataset-2 csv.csv`
- Contains 18-band spectral reflectance readings from handheld spectrometer
- Target variable: Soil moisture levels
- Pre-processed with outlier removal using IQR method

Tech Stack

Hardware
- Handheld Spectrometer (18 wavelength bands: 410nm-940nm)
- Raspberry Pi 4 (Edge computing device)
- DHT22 Temperature & Humidity Sensor
- Soil Moisture Sensor
- ADS1115 16-bit ADC

Software
- Python 3.9+
- Colab Notebook for data analysis
- Machine Learning: scikit-learn (Random Forest, SVR)
- Data Processing: pandas, numpy
- Visualization: matplotlib, seaborn
- Edge Computing: Local model deployment on Raspberry Pi

Methodology

1. Data Acquisition: Collected spectral readings and moisture values using handheld spectrometer and sensors
2. Data Preprocessing: Cleaned dataset, removed outliers using IQR method, normalized features
3. Feature Analysis: Analyzed correlations between spectral bands and moisture using scatter plots and polynomial curve fitting
4. Model Training: Trained multiple regression models (Random Forest, SVR) with K-Fold cross-validation
5. Evaluation: Assessed models using MAE, RMSE, and MAPE metrics

Machine Learning Models

Random Forest Regressor(Best Performance)
- Configuration: 300 estimators
- Training: 80-20 train-test split
- Validation: 5-fold K-Fold cross-validation and 10-fold ShuffleSplit
- Feature Importance: Identifies key spectral bands affecting moisture prediction

Support Vector Regressor (SVR)
- Kernel: RBF (Radial Basis Function)
- Parameters: C=100, gamma=0.01
- Performance: Evaluated using MAE and RMSE metrics

Results

The Random Forest Regressor outperformed other models:

| Metric | Value |
|--------|-------|
| **Accuracy** | 98.81% |
| **MAPE** | 1.19% |
| **MAE** | 116.98 |
| **RMSE** | 157.48 |

The model successfully captures non-linear relationships between spectral data and soil moisture, even with limited training samples.

Key Features

- Real-time soil moisture prediction from spectral data
- Edge computing for offline operation (works without internet)
- High accuracy (98.81%) with minimal dataset
- 18-band spectral analysis for comprehensive plant health monitoring
- Cost-effective hardware setup (~$150-200)
- Feature importance analysis to identify critical wavelength bands
- Suitable for precision agriculture and smart gardening



Analysis Workflow

The notebook (`Untitled5 (5).ipynb`) includes:
1. **Data Loading**: Import spectral and sensor readings from CSV
2. **Data Cleaning**: Handle missing values, format corrections (moisture column)
3. **Outlier Detection**: IQR-based filtering for robust training
4. **Exploratory Data Analysis**: Box plots for each spectral band and sensor
5. **Feature-Target Visualization**: Polynomial curve fitting between each feature and moisture
6. **Model Training**: Random Forest (300 trees) and SVM (RBF kernel)
7. **Cross-Validation**: K-Fold (5 splits) and ShuffleSplit (10 splits) validation
8. **Feature Importance**: Identify which spectral bands contribute most to predictions
9. **Performance Evaluation**: Calculate MAE, RMSE, and MAPE metrics

## 📁 Project Structure

```
smart-gardening-iot/
│
├── final dataset-2 csv.csv    # Spectral and sensor data
├── Untitled5 (5).ipynb        # ML analysis notebook
├── Bds (2).pdf                # Project documentation
├── README.md                  # This file


## 🌐 Applications

- **Precision Irrigation Management**: Optimize water usage based on actual plant needs
- **Early Plant Stress Detection**: Identify water stress before visible symptoms
- **Nutrient Deficiency Identification**: Detect nutrient issues via spectral signatures
- **Home & Commercial Gardening**: Suitable for both small and large-scale operations
- **Agricultural Research**: Study plant-water relationships using spectral data

## 🔮 Future Enhancements

- Real-time web dashboard for monitoring multiple plants
- Automated irrigation valve control based on predictions
- Mobile app with push notifications for critical moisture levels
- Time-series forecasting for predictive irrigation scheduling
- Deep learning models (CNN/LSTM) for temporal pattern recognition
- Multi-plant disease detection using spectral signatures
- Cloud integration for remote farm monitoring
- Solar-powered deployment for outdoor installations

## 👥 Team

**MTech Data Science, Semester 1**  
Institute of Technology, Nirma University, Ahmedabad, India

- **Aayushi Sheth** (25MCD023) - [@aayushisheth7](https://github.com/aayushisheth7)
- Khushi Patel (25MCD017)
- Soham Dave (25MCD005)

**Faculty Advisors**:
- Dr. Jaiprakash Verma (Associate Professor)
- Dr. Sumedha Arora (Assistant Professor)

## 🙏 Acknowledgments

This project was developed as part of the Big Data Systems course at Nirma University, demonstrating the integration of IoT, edge computing, and machine learning for precision agriculture.

