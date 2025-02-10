#  Real-Time-Order-Processing Project

## [1. Introduction](#introduction)
This project implements a real-time data pipeline for processing orders and payments using **Apache Kafka** and **Spark Structured Streaming**. It enables seamless event-driven processing by capturing transactions as they occur, ensuring accurate and timely data updates.

The pipeline:<br>
- Streams orders and payments data from Kafka topics.<br>
- Performs stateful processing to process, correlate, and match orders with payments using Spark Streaming.<br>
- Writes enriched data to MongoDB for further analysis.<br>

This system is ideal for real-time analytics, fraud detection, and payment reconciliation in an e-commerce or fintech environment

## [2. Architecture](#architecture)


### 2.1 Kafka Producers (Order & Payment Producers)
- **Purpose**: Produce real-time events (orders and payments) and send them to Kafka topics.
- **Components**:
  - `orders_producer.py`: Sends order events to the `orders_topic`.
  - `payments_producer.py`: Sends payment events to the `payments_topic`.
- **Kafka Topics**: `orders_topic_data_v1`, `payments_topic_data_v1`
- *Note*: The Kafka topics are hosted on a Kafka cluster created using **Confluent**, providing a fully managed Kafka environment.


---
### 2.2 Spark Structured Streaming (Stateful Processing)
- **Purpose**: Process the streams of orders and payments in real-time.
- **Key Responsibilities**:
  - Consume Kafka topics (`orders_topic` and `payments_topic`).
  - Join streams of orders and payments on `order_id`.
  - Apply stateful logic to track orders and match payments.
  - Timeout for unmatched orders.
  - Write enriched data to MongoDB.
- **Components**:
  - `join_stream.py`: This script implements the core streaming logic, including stateful processing and writing output to MongoDB.


### 4. MongoDB
- **Purpose**: Store the processed and enriched data (orders with payments)


