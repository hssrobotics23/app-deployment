# DGMD Application Deployment

This repository provides docker-compose definitions for deployment of the DGMD application including:

* MLFlow model artifact hosting backend
* Model training pipeline
* FastAPI api front-end

## Requirements

For application to be fully launched the following secrets need to be placed in a user-created `/secrets` folder:

* /secrets/aws_credentials - provide AWS credentials for access to S3 bucket used for MLFlow model storage
* /secrets/.env - provide `OPENAI_KEY` environment variable used for ChatGPT queries

## Launching Application

Fully application can be launched via:

```bash
>> cd app-deployment
>> docker compose up -d
```

This will download required container images and launch containers as needed.  Application can be stopped via `docker compose down`.

## Configuration

Multiple environment variables can be set within the [docker-compose.yml](docker-compose.yml) file to customize application performance (e.g. application asset names, storage locations or model training parameters).  It is recommended to review [/app-deployment/docker-compose.yml](docker-compose.yml) as well as individual container Dockerfiles (e.g. [/api/Dockerfile](https://github.com/hssrobotics23/api/blob/main/Dockerfile)) for full understanding of configuration defaults.

