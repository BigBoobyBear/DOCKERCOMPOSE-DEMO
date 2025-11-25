# Docker Compose Demo

A demonstration project showcasing Docker Compose with multiple services running in containers.

## Project Structure

```
DOCKERCOMPOSE-DEMO/
├── course-service/    # Course service application
├── website/          # Static website served by nginx
└── docker-compose.yml
```

## Services

### Course Service
- Runs on port **5001**
- Maps to container port 8080
- Custom application built from `./course-service`

### Website
- Runs on port **5002**
- Static content served by nginx:alpine
- Content served from `./website` directory

## Prerequisites

- Docker
- Docker Compose

## Getting Started

1. Start all services:
```bash
docker-compose up
```

2. Start services in detached mode:
```bash
docker-compose up -d
```

3. Stop all services:
```bash
docker-compose down
```

## Accessing Services

- Course Service: http://localhost:5001
- Website: http://localhost:5002

## Development

The services use volume mounting, so changes to the code will be reflected without rebuilding:
- Course service mounts `./course-service` to `/usr/src/app`
- Website mounts `./website` to `/usr/share/nginx/html`
