# Stock Analysis Project

This project implements a real-time stock market data processing system using Apache Kafka for data streaming and AWS S3 for data storage. The system consists of two main components: a producer and a consumer.

## Project Structure

```
stock-analysis/
├── data/
│   └── indexProcessed.csv    # Source stock market data
├── stock_analysis_producer.ipynb  # Kafka producer notebook
├── stock_analysis_consumer.ipynb  # Kafka consumer notebook
└── .gitignore
```

## Components

### 1. Producer (`stock_analysis_producer.ipynb`)
- Reads stock market data from `indexProcessed.csv`
- Sends random stock data samples to a Kafka topic every second
- Uses Kafka producer to stream data to the broker

### 2. Consumer (`stock_analysis_consumer.ipynb`)
- Consumes stock market data from the Kafka topic
- Stores the received data in AWS S3 as JSON files
- Uses S3FileSystem for AWS S3 integration

## Prerequisites

- Python 3.x
- Required Python packages:
  - kafka-python
  - pandas
  - s3fs
  - json

## Setup and Installation

1. Install required packages:
```bash
pip install kafka-python pandas s3fs
```

2. Configure AWS credentials for S3 access (if using AWS S3)

3. Ensure Kafka broker is running and accessible at the specified address

## Usage

1. Start the producer:
   - Open `stock_analysis_producer.ipynb`
   - Run all cells to start sending stock data to Kafka

2. Start the consumer:
   - Open `stock_analysis_consumer.ipynb`
   - Run all cells to start consuming and storing data in S3

## Data Flow

1. Producer reads from CSV → Kafka topic
2. Consumer reads from Kafka topic → AWS S3 storage

## Security Note

- The `.pem` file is excluded from version control for security reasons
- Make sure to keep your AWS credentials and Kafka broker details secure

## License

This project is open source and available under the MIT License. 