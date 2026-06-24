# MLops-RTG6-docker

A simple Flask web app containerized with Docker for MLOps practice.

## Project Overview

This app provides:
- A home page with a form to enter a username.
- A `/greet` endpoint that returns a personalized greeting.

The app runs on port `5000`.

## Tech Stack

- Python 3.8
- Flask
- Docker

## Project Structure

- `app.py` - Flask application.
- `requirements.txt` - Python dependencies.
- `dockerfile` - Docker image instructions.

## Run with Docker

### 1. Build image

```bash
docker build -t mlops-docker-demo .
```

### 2. Run container

```bash
docker run -p 5000:5000 mlops-docker-demo
```

Open: `http://localhost:5000`

## Push Image to Docker Hub

### 1. Login

```bash
docker login
```

### 2. Tag image

Replace `<dockerhub-username>` with your Docker Hub username.

```bash
docker tag mlops-docker-demo <dockerhub-username>/mlops-docker-demo:latest
```

### 3. Push image

```bash
docker push <dockerhub-username>/mlops-docker-demo:latest
```

## Pull and Run from Docker Hub

```bash
docker pull <dockerhub-username>/mlops-docker-demo:latest
docker run -p 5000:5000 <dockerhub-username>/mlops-docker-demo:latest
```

## Local Python Run (Optional)

```bash
pip install -r requirements.txt
python app.py
```