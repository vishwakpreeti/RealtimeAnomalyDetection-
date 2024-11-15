# Real-Time Anomaly Detection in Financial Data Streams

![image](https://github.com/user-attachments/assets/11dd9dc4-a684-4919-98d1-9faeb3a1af17)

This project implements real-time anomaly detection on streaming financial data, sourced from major providers like NASDAQ, CME Group, and NSE. The system uses Quix Streams for Kafka-based data streaming, Redpanda for message distribution, and Docker for containerized deployment. Anomalies are detected through a combination of high-volume trading thresholds and Isolation Forest machine learning models.

## Table of Contents

Architecture

Key Features

Installation

Usage

License

Architecture

### The system architecture is illustrated in the diagram above. Key components include:

### Data Providers: 
Financial data is streamed from providers (e.g., NASDAQ, CME, NSE) via Databento.

### Data Ingestion and Streaming: 
The data is processed and streamed using Redpanda.

### Real-Time Anomaly Detection: 
Anomaly detection is implemented with Quix Streams. Two primary detection rules are used:

### High Volume Rule: 
Flags transactions with unusually high trading volumes.

### Isolation Forest Model: 
Detects anomalies based on trade price patterns.

### Output Streaming: 
The results are visualized and stored via Streamlit and Elasticsearch.

## Key Features:

### Dockerized Environment: 
Fully containerized for easy deployment and scalability.

### High-Performance Streaming: 
Uses Quix Streams and Redpanda for efficient data streaming.

### Multiple Anomaly Detection Methods: 
High-volume thresholds and machine learning-based Isolation Forest.

### Real-Time Visualization: 
Visualize results using Streamlit and store data in Elasticsearch.

## Installation

### Prerequisites

Docker and Docker Compose
Python 3.12.5

## Setup

1. Clone the repository: 
git clone https://github.com/vishwakpreeti/RealtimeAnomalyDetection-.git
cd RealtimeAnomalyDetection-

2. Create a .env file with the required environment variables:

input=<input_topic_name>
output=<output_topic_name>

3. Build and start the Docker containers:

docker-compose up --build

# Usage
1. Data Ingestion: The producer script reads financial data from .zst files in the nasdaq folder and publishes it to Kafka.
2. Anomaly Detection: The consumer script applies the high-volume and Isolation Forest rules to detect anomalies in real-time.
3. Visualization: Detected anomalies are visualized in Streamlit and stored in Elasticsearch for analysis.

# Requirements
## List of dependencies:

quixstreams==2.9.0
python-dotenv
scikit-learn
zstandard
tqdm
pandas
License

This project is licensed under the IITJ License.
