# Credit Card Fraud Detection API

This project deploys a machine learning model using FastAPI, Docker, and Kafka to detect fraudulent transactions in real time.

## Features
- Logistic Regression model trained on Kaggle's credit card fraud dataset
- REST API for predictions
- Kafka streaming for real-time data
- Dockerized for easy deployment

## How to Run
1. Clone the repo
2. Build the Docker image
3. Start with Docker Compose
4. Send transactions via Kafka or REST

## Author
Ademoye — built for 3MTT Final Project



+----------------+       POST /predict       +------------------+
| Kafka Producer |  ---------------------->  |   FastAPI App    |
| (streaming.py) |                          |  (main.py)       |
+----------------+                          +------------------+
        |                                           ^
        |                                           |
        v                                           |
+----------------+       Prediction Response       |
| Kafka Broker   |  <-----------------------------+
| (creditcard-transactions topic)                 |
+----------------+
        ^
        |
        |
+----------------+
| Kafka Consumer |
| (streaming.py) |
+----------------+