# NYC Taxi Trip Data Analysis using Machine Learning and PySpark

## Introduction
The **NYC Taxi Trip Dataset** consists of trip records from taxis in New York City, provided by the **NYC Taxi and Limousine Commission (TLC)**. This dataset contains billions of taxi rides dating back to 2009, making it a valuable resource for urban transportation research. The analysis focuses on **Yellow Taxi** trips stored in **Parquet format**.

## Features of the Dataset
Each row in the dataset represents a taxi trip with the following key features:
- **Pickup and Drop-off Timestamps**: When the trip started and ended.
- **Pickup and Drop-off Locations**: Latitude and longitude coordinates.
- **Trip Distance**: Distance traveled in miles.
- **Fare Amount**: Total fare including base fare, taxes, and surcharges.
- **Payment Type**: Payment method used (cash or card).

These features enable the analysis of trip duration, travel patterns, pricing, and customer behavior.

## Data Collection Process
The dataset is collected in real-time from **GPS-enabled taxi meters**, then anonymized and made publicly available by the **NYC TLC**.

## Project Overview
This project utilizes **PySpark** and **Machine Learning** techniques to analyze NYC taxi trip data with the following objectives:

### 1. **Data Preprocessing & Feature Engineering**
- Converted timestamps into structured date and time features.
- Extracted features such as **pickup hour, pickup day of the week, and trip duration**.
- Combined multiple months of taxi data into a single Parquet file for efficient processing.

### 2. **Taxi Demand Analysis**
- Identified high-demand areas by aggregating pickups by **PULocationID and week**.
- Mapped demand hotspots using **GeoPandas** and **DBSCAN clustering**.

### 3. **Trip Duration Prediction**
- Used a **Random Forest Regressor** to predict trip duration based on pickup time, location, and distance.
- Model Performance:
  - **RMSE**: 3.81 minutes
  - **MAE**: 2.79 minutes
  - **R² Score**: 72%

### 4. **Passenger Segmentation**
- Clustered passengers based on **trip distance, fare, time of day, and payment method**.
- Used **K-Means Clustering** with an optimal **k=5** based on the **Elbow Method**.
- Visualized clusters of short, medium, and long-distance trips with different fare structures.

### 5. **Payment Type Prediction**
- Built a **Logistic Regression Model** to classify payment type (cash or card).
- Model Performance:
  - **Accuracy**: 64.1%
  - **Precision**: 64.4%
  - **Recall**: 96.2%
  - **F1 Score**: 77.2%

### 6. **Fare Prediction & Borough Analysis**
- Merged taxi data with borough information for deeper fare analysis.
- Used **Random Forest Regression** to predict fare amounts based on borough-specific factors.
- Model Performance:
  - **RMSE**: 3.53
  - **MAE**: 1.39
  - **R² Score**: 89%
- Mapped **average fares by boroughs** to visualize inter-borough fare variations.

### 7. **Tip Amount Prediction**
- Built a **Random Forest Model** to predict tip amounts.
- Model Performance:
  - **RMSE**: 1.03
  - **MAE**: 0.42
  - **R² Score**: 82%

### 8. **High vs. Low Fare Classification**
- Created a binary classification model using **Logistic Regression** to predict whether a trip will have a **high or low fare**.
- Model Performance:
  - **Accuracy**: 89.4%
  - **Precision**: 94.8%
  - **Recall**: 82.1%
  - **F1 Score**: 88.0%

### 9. **Traffic Congestion Analysis & Prediction**
- Classified congestion levels based on **average speed thresholds**.
- Built a **Random Forest Classifier** to predict congestion levels.
- Model Performance:
  - **Accuracy**: 83.9%
  - **F1 Score**: 80.3%
  - **Precision**: 80.9%
  - **Recall**: 83.9%
- Visualized **congestion hotspots on a Mapbox map**.

## Setup & Installation
### 1. Clone Repository
```bash
git clone https://github.com/your-repo/NYC-Taxi-Trip-Analysis.git
cd NYC-Taxi-Trip-Analysis
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run Analysis in PySpark
```bash
python main.py
```

## Technologies Used
- **PySpark**: Large-scale data processing
- **Pandas & NumPy**: Data handling and manipulation
- **Scikit-Learn**: Machine learning models
- **Matplotlib & Seaborn**: Data visualization
- **Plotly & GeoPandas**: Mapping taxi trip trends

## Results & Insights
- **Manhattan has the highest taxi demand**, with consistent pickup activity throughout the day.
- **Trips involving airports and outer boroughs have significantly higher fares**.
- **Credit card payments dominate taxi rides**, but cash transactions remain common for short trips.
- **Predictive models achieved strong accuracy**, making them useful for fare estimation and congestion monitoring.

## License
This project is licensed under the **MIT License**.

---
🚖 **Happy Analyzing!** 🚀


