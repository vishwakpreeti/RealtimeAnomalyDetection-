# Anomaly Detection Pipeline with Quix Streams, Redpanda, and Docker

This project implements a real-time anomaly detection pipeline for stock market data. It utilizes **Quix Streams** for data streaming, **Redpanda** as the message broker, and **Isolation Forest** for anomaly detection. The pipeline detects anomalies in stock market data such as high-volume trades and price outliers, which could indicate unusual market behavior.

## Project Structure


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
input=stock_data_input_topic
output=anomalies_output_topic
output=stock_data_input_topic

**### For Anomaly Detector**
cd anomalydetector
pip install -r requirements.txt

# For Producer
cd ../producer
pip install -r requirements.txt

docker-compose -f compose.local.yaml up --build

Running the Pipeline
Data Producer: Reads data from .zst files in the producer/nasdaq/ folder and publishes it to the Kafka topic.

The main.py script in the producer folder publishes each row of stock data to the topic specified in the output environment variable.
Anomaly Detector: Consumes data from the Kafka topic and applies anomaly detection.

The main.py script in the anomalydetector folder reads from the input topic, detects anomalies using high-volume and Isolation Forest rules, and publishes results to the output topic.
Anomaly Detection Rules
High-Volume Rule: Flags a trade as an anomaly if the trade size exceeds a predefined threshold. The threshold can be modified in the code to adjust for different symbols.
Isolation Forest Rule: Uses an Isolation Forest model to identify price anomalies by fitting on recent price data and detecting outliers.
Example Usage
Start the Producer: Publish sample stock data to Kafka.
Make sure to place sample data in the producer/nasdaq/ folder.
Run the Anomaly Detector: Detect and publish anomalies to the output topic.
The output topic will contain messages with detected anomalies, which you can monitor for insights on unusual trading activity.

Testing and Verification
You can test individual components by running the main.py files within the producer and anomalydetector folders.
To verify that anomalies are being detected and published, check the output topic messages or add print statements to observe the output in the console.
Dependencies
The following dependencies are listed in requirements.txt files in each component’s folder:

quixstreams
python-dotenv
scikit-learn
zstandard (for reading .zst files in the producer)
pandas and tqdm (for data processing in the producer)
Troubleshooting
Connection Errors: Ensure your Kafka/Redpanda broker is running and accessible by both containers.
Environment Variables: Double-check the .env files in each folder to make sure the correct topic names are specified.
Future Enhancements
Database Integration: Store anomalies in a database like PostgreSQL for historical analysis.
Visualization: Use a tool like Streamlit to create a real-time dashboard for detected anomalies.
Additional Anomaly Rules: Implement additional detection rules based on domain-specific insights.
License
This project is open source under the Apache 2.0 license.

Contribute
Feel free to fork the repository and submit pull requests with improvements or bug fixes. Contributions are welcome!


---

This README file is ready to be pasted into your project. It includes all sections, setup instructions, and details to help users understand and run the project. Let me know if you need further assistance!
