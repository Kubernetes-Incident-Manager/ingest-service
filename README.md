# Ingest Service

## Overview
The **Ingest Service** is responsible for receiving external events, alerts, and webhooks from various monitoring tools (e.g., Datadog, Prometheus, New Relic) and normalizing them into a standard incident format. It acts as the event ingestion layer before incidents are officially created in the system.

## Features
- Receives external HTTP POST webhooks for alert ingestion.
- Validates and normalizes payload structures.
- Publishes processed events to message queues or calls internal services.
- Built with Python and FastAPI.

## Getting Started

### Prerequisites
- Python 3.10+
- `pip` package manager
- Docker (optional for containerized deployment)

### Installation
1. Navigate to the service directory:
   ```bash
   cd services/ingest-service
   ```
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Running the Service
To run the service locally for development:
```bash
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

## Docker
Build the Docker image:
```bash
docker build -t incident-tracker/ingest-service .
```
Run the Docker container:
```bash
docker run -p 8000:8000 incident-tracker/ingest-service
```
