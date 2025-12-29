### Kafka Event Streaming Pipeline (Docker + Python)
## Description
A beginner-friendly Kafka setup using Docker, Confluent Kafka (Python client), and a simple producer–consumer example.

This project demonstrates:
- Running Kafka in KRaft mode
- Creating and inspecting topics
- Producing messages with Python
- Consuming messages with Python

## Overview
- start a Kafka broker with Docker Compose
- create + inspect a Kafka topic
- run a Python producer that sends “orders”
- run a Python consumer that prints received orders

## Download PyCHarm from JetBrains' official website

## Start Kafka (Docker)
```bash
docker compose up 
```
Check the container is running:
```bash
docker ps
```
## Install confluent-kafka dependency in the terminal of PyCharm
```bash
pip3 install confluent-kafka
```
## Run the Python consumer
```bash
python tracker.py
```
## Run the Python producer
```bash
python producer.py
```
Your consumer should print something like:
```bash
📦 Received order: 1 x chicken burger from nicole
```
## Validate that the topic was created in kafka container
```bash
docker exec -it kafka kafka-topics --list --bootstrap-server localhost:9092
```
## Describe that topic and see its partitions
```bash
docker exec -it kafka kafkSa-topics --bootstrap-server localhost:9092 --describe --topic new_orders
```
## View all events in a topic
```bash
docker exec -it kafka kafka-console-consumer --bootstrap-server localhost:9092 --topic orders --from-beginning
```