# Anomaly Detection Pipeline with Quix Streams, Redpanda, and Docker

This project implements a real-time anomaly detection pipeline for stock market data. It utilizes **Quix Streams** for data streaming, **Redpanda** as the message broker, and **Isolation Forest** for anomaly detection. The pipeline detects anomalies in stock market data such as high-volume trades and price outliers, which could indicate unusual market behavior.

## Project Structure

├── anomalydetector/ │ ├── .env # Environment variables specific to the anomaly detector │ ├── app.yaml # Application configuration file │ ├── dockerfile # Dockerfile for the anomaly detector │ ├── main.py # Anomaly detection script │ ├── README.md # Readme specific to the anomaly detector │ ├── requirements.txt # Python dependencies ├── producer/ │ ├── nasdaq/ # Folder containing sample stock data files │ ├── .env # Environment variables specific to the producer │ ├── app.yaml # Application configuration file │ ├── dockerfile # Dockerfile for the producer │ ├── main.py # Data producer script │ ├── README.md # Readme specific to the producer │ ├── requirements.txt # Python dependencies ├── .gitignore # Files to ignore in the repository ├── compose.local.yaml # Docker Compose configuration for local setup ├── pipeline.md # Pipeline details document └── quix.yaml # General configuration for Quix Streams

## Features

- **Real-time Stock Data Processing**: Streams data from a local source to a Kafka-compatible message broker.
- **Anomaly Detection**: Identifies high-volume trades and price anomalies using Isolation Forest.
- **Containerized Deployment**: Dockerized services for easy setup and deployment.

## Prerequisites

- **Docker**: Ensure Docker is installed and running on your system.
- **Python**: If you want to run scripts directly, Python 3.12.5 is required.
- **Redpanda or Kafka**: A Kafka-compatible message broker (e.g., Redpanda) is needed to run the pipeline.

## Setup Instructions

### Step 1: Clone the Repository

```bash
git clone <repo-url>
cd <repo-folder>

### Step 2: Configure Environment Variables
Each component (anomalydetector and producer) requires environment variables stored in .env files. You can copy and modify the following sample configurations:

anomalydetector/.env
input=stock_data_input_topic
output=anomalies_output_topic

### Step 2: Configure Environment Variables
