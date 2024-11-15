# Anomaly Detection Pipeline with Quix Streams, Redpanda, and Docker

This project implements a real-time anomaly detection pipeline for stock market data. It utilizes **Quix Streams** for data streaming, **Redpanda** as the message broker, and **Isolation Forest** for anomaly detection. The pipeline detects anomalies in stock market data such as high-volume trades and price outliers, which could indicate unusual market behavior.

## Project Structure

 ├── anomalydetector/ │ ├── .env # Environment variables specific to the anomaly detector │ ├── app.yaml # Application configuration file │ ├── dockerfile # Dockerfile for the anomaly detector │ ├── main.py # Anomaly detection script │ ├── README.md # Readme specific to the anomaly detector │ ├── requirements.txt # Python dependencies ├── producer/ │ ├── nasdaq/ # Folder containing sample stock data files │ ├── .env # Environment variables specific to the producer │ ├── app.yaml # Application configuration file │ ├── dockerfile # Dockerfile for the producer │ ├── main.py # Data producer script │ ├── README.md # Readme specific to the producer │ ├── requirements.txt # Python dependencies ├── .gitignore # Files to ignore in the repository ├── compose.local.yaml # Docker Compose configuration for local setup ├── pipeline.md # Pipeline details document └── quix.yaml # General configuration for Quix Streams
