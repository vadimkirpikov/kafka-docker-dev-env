# Kafka docker development environment

This repository provides a configuration for deploying Apache Kafka and Zookeeper using Docker and Docker Compose.

## Setup and Deployment

1. Clone the repository:

   ```bash
   git clone https://github.com/vadimkirpikov/kafka-docker-dev-env.git
   cd kafka-docker-dev-env
   ```

2. Start the Docker containers:

   ```bash
   docker-compose up -d
   ```

3. Check the status of the containers:

   ```bash
   docker-compose ps
   ```

## Basic testing

1. Create a topic:

   ```bash
   docker exec -it kafka kafka-topics --create --topic test_topic --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
   ```

2. Send a message:

   ```bash
   docker exec -it kafka kafka-console-producer --topic test_topic --bootstrap-server localhost:9092
   ```

   Type your message and press `Enter`. To exit the producer, press `Ctrl+C`.

3. Consume messages:

   ```bash
   docker exec -it kafka kafka-console-consumer --topic test_topic --bootstrap-server localhost:9092 --from-beginning
   ```
