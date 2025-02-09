#  Real-Time-Order-Processing Project

## [1. Introduction](#introduction)
This project implements a real-time data pipeline for processing orders and payments using Apache Kafka and Spark Structured Streaming. It enables seamless event-driven processing by capturing transactions as they occur, ensuring accurate and timely data updates.

The pipeline:<br>
- Streams orders and payments data from Kafka topics.<br>
- Performs stateful processing to process, correlate, and match orders with payments using Spark Streaming.<br>
- Writes enriched data to MongoDB for further analysis.<br>

This system is ideal for real-time analytics, fraud detection, and payment reconciliation in an e-commerce or fintech environment
