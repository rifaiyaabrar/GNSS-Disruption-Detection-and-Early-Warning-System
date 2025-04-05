# GNSS Disruption Detection and Early Warning System

An advanced machine learning-based system for detecting, classifying, and predicting Global Navigation Satellite System (GNSS) signal disruptions caused by intentional or unintentional jamming.

## Project Overview

GNSS systems are essential for modern technologies including autonomous vehicles, aviation, and maritime navigation. However, these systems are vulnerable to signal disruptions, particularly from jamming, which can impact navigation, communication, and safety. This project addresses these challenges through:

1. **GNSS Jamming Detection and Classification**: Detecting and classifying signal anomalies in real-time
2. **Early Warning System**: Predicting potential future disruptions based on historical patterns

## Features

- **Anomaly Detection**: Using Isolation Forest and DBSCAN algorithms to identify signal disruptions
- **Clustering Analysis**: Grouping related disruptions to understand patterns and sources
- **Predictive Forecasting**: LSTM-based prediction of potential future signal issues
- **Interactive Visualization**: Maps and graphs showing anomaly locations and patterns
- **Distance Calculation**: Accurate travel distance computation using geodesic measurements

## Data Processing Pipeline

### Preprocessing
- Handling missing values in critical columns (lat, lon, speed)
- Outlier detection and handling for features like speed and SNR
- Standardization using StandardScaler for ML algorithm compatibility

### Feature Engineering
- **Speed**: Calculated using the Haversine formula for consecutive coordinates
- **Time Difference**: Derived from consecutive timestamps
- **Direction Change**: Calculated as the arctangent of latitude and longitude changes
- **Speed Difference**: Rate of change in movement speed

## Machine Learning Models

### Detection and Classification
- **Isolation Forest**: Unsupervised anomaly detection based on feature distributions
- **DBSCAN**: Density-based clustering to identify groups of related disruptions
- **KMeans**: Geographical clustering of anomalies based on location

### Early Warning System
- **LSTM Networks**: Deep learning model that captures temporal patterns in GNSS data
- **Sequential Model**: Neural network architecture for predicting future anomalies
- **Binary Classification**: Identifying potential disruptions before they occur

## Results

- Successfully detected and classified GNSS anomalies in the test dataset
- Created geographical clustering of anomalies to identify potential jamming zones
- Developed an early warning system with promising prediction capabilities
- Generated comprehensive visualizations including:
  - Interactive maps of travel paths with anomalies highlighted
  - Speed and time difference plots showing detected disruptions
  - Cluster visualizations showing geographical patterns of anomalies

## Limitations

- The system was developed and tested primarily on rural/countryside data
- Performance in urban environments with high-rise buildings may require additional tuning
- Limited validation due to the specific nature of the available dataset

## Future Work

- Extend the model to urban environments with more complex signal patterns
- Incorporate additional data sources for improved prediction accuracy
- Develop real-time alerting mechanisms for critical applications
- Expand clustering analysis to better distinguish between intentional and unintentional jamming

## Installation and Usage

```bash
# Clone the repository
git clone https://github.com/rifaiyaabrar/gnss-disruption-detection.git
cd gnss-disruption-detection

# Install dependencies
pip install -r requirements.txt

# Run the detection system
python detect_anomalies.py --input path/to/nmea.csv

# Run the early warning system
python predict_disruptions.py --model lstm --window 10
```

## Required Dependencies

- Python 3.8+
- NumPy
- Pandas
- Scikit-learn
- TensorFlow/Keras
- Folium
- Matplotlib
- Seaborn
- Geopy


## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Petri Välisuo (Supervisor) - University of Vaasa
- Data collection source: https://github.com/pevalisuo/AML/blob/master/Exercises/Jammer_detection
