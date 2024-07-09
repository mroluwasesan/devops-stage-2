# Full Stack Web Application Deployment

This repository contains the Docker configuration files for deploying a full stack web application, which includes a React frontend and a FastAPI backend.

## Prerequisites

- Docker installed
- Docker Compose installed
- npm installed
- git installed
- python installed

## Getting Started

To get started with this template, please follow the instructions in the respective directories:

- [Frontend README](./frontend/README.md)
- [Backend README](./backend/README.md)

## Deploy using Docker locally

```sh
git clone https://github.com/yourusername/your-repo.git
cd your-repo
```
### Frontend
```sh
cd frontend

docker build -t frontend-image .

docker run -d -p 5173:5173 frontend-image
```
Access the frontend application at 'http://localhost:5173'.

### Backend
```sh
cd backend

docker build -t backend-image .

docker run -d -p 8000:8000 backend-image
```
Access the backend application at 'http://localhost:8000'.

## Deploy using Docker-compose

Ensure you're in the root directory of the project:
```sh
cd your-repo
```
Add your [docker-compose.yml](./docker-compose.yml) file to the root folder.

Run the command:
```sh
docker-compose up -d --build
```
If it was from a virtual environment like AWS, you can simply create a subdomain name at Afraid DNS and then link your backend and frontend using the proxy manager already existing in the docker-compose.yml file.

## Configuration

### Environment Variables

Ensure you have the necessary environment variables set in the '.env' files located in the 'frontend' and 'backend' directories.

## Docker Compose Configuration

The 'docker-compose.yml' file defines the services and their configurations.

## Troubleshooting

1. Ensure Docker and Docker Compose are installed and running.

2. Check for any port conflicts on your machine.

3. Verify that the .env files are correctly configured.

## Cleanup

To stop the containers and remove the network:
```sh
docker-compose down
```

To remove all Docker containers, images, and volumes (use with caution):
```sh
docker system prune -a --volumes
```
