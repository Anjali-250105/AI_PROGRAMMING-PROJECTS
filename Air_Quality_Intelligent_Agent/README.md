# Air Quality Intelligent Agent

## Project Overview

The Air Quality Intelligent Agent is an Artificial Intelligence project that analyzes historical air quality data and predicts the Air Quality Index (AQI). The project uses data preprocessing, visualization, a Simple Reflex Agent, and Random Forest Regression to analyze and forecast air quality.

## Objective

The main objectives of this project are:

- To analyze historical air quality data.
- To handle missing values and preprocess the dataset.
- To visualize US AQI trends over time.
- To classify air quality using a Simple Reflex Agent.
- To predict US AQI using Machine Learning.
- To evaluate the prediction model.
- To forecast the next-day AQI.
- To determine the air quality category of the predicted AQI.

## Dataset

The project uses the `air_quality_historical.csv` dataset containing historical air quality data for Lahore.

The dataset includes parameters such as:

- PM10
- PM2.5
- Carbon Monoxide
- Nitrogen Dioxide
- Sulphur Dioxide
- Ozone
- Aerosol Optical Depth
- Dust
- UV Index
- US AQI
- European AQI
- Date

## Data Preprocessing

The following preprocessing steps are performed:

1. Load the air quality dataset.
2. Check the structure and information of the dataset.
3. Check for missing values.
4. Convert the date column into datetime format.
5. Sort the data chronologically.
6. Interpolate missing values in numerical air quality parameters.
7. Remove records with missing AQI values.
8. Generate descriptive statistics.

## AQI Visualization

The project visualizes the US AQI over time to understand the changes in air quality in Lahore.

It also visualizes the distribution of different AQI categories.

## Simple Reflex Agent

A Simple Reflex Agent is implemented to classify AQI values into different categories based on predefined AQI ranges:

- 0–50: Good
- 51–100: Moderate
- 101–150: Unhealthy for Sensitive Groups
- 151–200: Unhealthy
- 201–300: Very Unhealthy
- Above 300: Hazardous

The agent takes an AQI value as input and returns the corresponding air quality category.

## Machine Learning Model

A Random Forest Regressor is used to predict US AQI from different air quality parameters.

The input features include:

- PM10
- PM2.5
- Carbon Monoxide
- Nitrogen Dioxide
- Sulphur Dioxide
- Ozone
- Aerosol Optical Depth
- Dust
- UV Index

The dataset is divided into training and testing sets, and the Random Forest model is trained using the training data.

## Model Evaluation

The AQI prediction model is evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

The project also compares the actual AQI values with the predicted AQI values using a visualization.

## Next-Day AQI Forecasting

The project also includes a next-day AQI forecasting model.

Previous AQI values are used as input features:

- AQI from the previous observation
- AQI from two observations earlier
- AQI from three observations earlier
- AQI from seven observations earlier

A Random Forest Regression model is trained while maintaining the chronological order of the data.

The trained model is then used to predict the AQI for the next day.

## Agent Decision

After predicting the next-day AQI, the predicted value is passed to the Simple Reflex Agent.

The agent determines the corresponding air quality category based on the predicted AQI value.

## Technologies Used

- Python
- Google Colab
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Random Forest Regression
- Artificial Intelligence
- Machine Learning

## Project File

- `SE26MAID036_AI1.ipynb` – Main project notebook
- `air_quality_historical.csv` – Dataset used for the project
- `README.md` – Project documentation

## How to Run

1. Open `SE26MAID036_AI1.ipynb` in Google Colab or Jupyter Notebook.
2. Upload the `air_quality_historical.csv` dataset when prompted.
3. Run the notebook cells sequentially.
4. View the data preprocessing, visualizations, AQI classifications, machine learning predictions, and next-day AQI forecast.

## Expected Outcome

The project provides an AI-based approach for analyzing historical air quality data, classifying AQI levels, predicting AQI using machine learning, and forecasting the next day's air quality condition.
