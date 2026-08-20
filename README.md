# open-ths-kafka-docker
A clean, production-ready Docker configuration for deploying Apache Kafka in KRaft mode.

## 🚀 Getting Started

### Prerequisites
Ensure you have [Docker Desktop](https://www.docker.com/) installed and running.


# Kafka Docker Platform Setup

This guide explains how to start the Kafka platform and its administration services using Docker Compose.

## Prerequisites

Ensure the following are installed and running:

- Docker
- Docker Compose

## Setup

1. Navigate to the Kafka platform directory:

   ```bash
   cd open-ths-kafka-docker/kafka/platform
   ```

2. Create the local environment file from the provided example:

   ```bash
   cp .env.example .env
   ```

3. Open the environment file:

   ```bash
   vi .env
   ```

4. Update `KAFKA_EXTERNAL_HOST` in `.env`:

   - For access from other machines on your network, set it to the host machine's internal IP address.
   - For a local-only setup, use `127.0.0.1`.

   Example:

   ```env
   KAFKA_EXTERNAL_HOST=127.0.0.1
   ```

5. Start Kafka and the administration services in detached mode:

   ```bash
   docker compose --profile admin up -d
   ```

   If your environment uses the legacy standalone command, run:

   ```bash
   docker-compose --profile admin up -d
   ```

## Verify the Containers

List all containers and confirm that the Kafka services are running:

```bash
docker ps -a
```

Containers with an `Up` status started successfully. If a container has exited, inspect its logs with:

```bash
docker logs <container-name>
```

## Stop the Platform

From the same `open-ths-kafka-docker/kafka/platform` directory, run:

```bash
docker compose --profile admin down
```



Disclaimer: This is a personal open-source project. The views and code expressed here do not represent those of my employer or any corporate entities.
