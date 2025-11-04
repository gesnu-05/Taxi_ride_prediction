Taxi Ride Prediction 🚖

A machine-learning project that predicts taxi ride fares or ride duration (or other ride-related metrics) using historic taxi dataset.

Table of Contents

Project Overview

Features

Dataset

Modeling Approach

Application

Getting Started

Usage

Deployment

Folder Structure

Future Work

Contributing

License

Project Overview

This project builds a predictive model to estimate taxi ride metrics (such as fare amount or ride duration) based on ride-data features (pickup/dropoff times, locations, passenger count, etc.). Using the dataset taxi.csv and a trained model saved as model.pkl, the project exposes a simple web interface (app.py) so users can enter ride details and receive a prediction.

Features

Data ingestion and preprocessing of taxi rides dataset

Feature engineering (time of day, distance calculation, geographic encoding)

Training and evaluation of machine-learning model (included in Mlmodel.ipynb)

Serialization of trained model (model.pkl)

Simple web application (app.py) to make predictions interactively

Structure managed with pyproject.toml / poetry.lock for dependency management

Dataset

The dataset (taxi.csv) contains ride-level data with features such as:

pickup_datetime

dropoff_datetime

pickup_longitude / pickup_latitude

dropoff_longitude / dropoff_latitude

passenger_count

… and the target variable (fare_amount or ride_duration)

Feel free to explore the Mlmodel.ipynb to understand how the data is cleaned, transformed, and modeled.

Modeling Approach

Exploratory data analysis (EDA) and data cleaning

Feature engineering: e.g., compute Haversine distance between pickup/dropoff, extract hour/day from timestamps

Split into train/test sets

Model training (e.g., linear regression, random forest)

Model evaluation using suitable metrics (MAE, RMSE, R²)

Save best model to model.pkl for deployment

Application

The app.py script loads the serialized model and provides a web interface (Flask or Streamlit) where you can input ride details and get predictions in real time.

Getting Started
Prerequisites

Python version >= 3.8

Dependencies listed in pyproject.toml / poetry.lock

Installation
git clone https://github.com/gesnu-05/Taxi_ride_prediction.git
cd Taxi_ride_prediction
poetry install   # or pip install -r requirements.txt if you generate one

Usage

Run the web app:

python app.py


Open your browser at the given local address (e.g., http://127.0.0.1:5000)

Enter ride parameters (pickup & dropoff coordinates, passenger count, datetime)

Submit to get predicted output

Deployment

You can deploy this application using cloud services like Heroku, AWS Elastic Beanstalk, or Streamlit Cloud. Ensure you include your model.pkl and update configuration (e.g., Procfile, requirements.txt) as needed.

Folder Structure
Taxi_ride_prediction/
│
├── static/            # Static assets (CSS, JS, images) if used  
├── templates/         # HTML templates for web interface  
├── Mlmodel.ipynb      # Jupyter notebook for data analysis & modelling  
├── app.py             # Web application entry point  
├── model.pkl          # Serialized trained model  
├── taxi.csv           # Dataset used for training  
├── pyproject.toml     # Project metadata and dependencies  
├── poetry.lock        # Locked dependencies  
└── README.md          # This file  

Future Work

Experiment with advanced models (e.g., gradient boosting, deep learning)

Add geospatial visualizations on map (pickup/dropoff clusters)

Include live API endpoint for predictions

Handle dynamic feature updates (e.g., weather data, traffic congestion)

Improve UI/UX of web app

