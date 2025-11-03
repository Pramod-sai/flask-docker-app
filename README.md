# flask-docker-app
A production-ready Flask web application containerized with Docker and orchestrated with Docker Compose. The app uses Redis as a lightweight in-memory store to demonstrate inter-container communication, persistent caching, and modern container orchestration practices.

# 🐳 Flask + Redis (Docker) — Production Demo

This repository showcases a **Flask web application containerized using Docker**, served by **Gunicorn**, and backed by a **Redis** cache service. It’s designed as a professional demo to understand microservice communication, container orchestration, and environment configuration with Docker Compose.

---

## 🚀 Features
- Flask API served by Gunicorn (production-ready WSGI)
- Redis-based counter and caching layer
- Multi-container setup via `docker-compose.yml`
- Makefile shortcuts for easy management
- Lightweight Python 3.11 slim base image
- Visuals, charts, and PDF documentation included

---

## 🧩 Architecture
![Architecture Diagram](images/architecture_diagram.jpg)

- **Web Container:** Flask app running on Gunicorn  
- **Cache Container:** Redis for in-memory data store  
- **Network:** Docker Compose bridge network  
- **Volume:** Redis persistence via `redis-data`

---

## 🧠 Endpoints
| Method | Endpoint | Description |
|:--|:--|:--|
| GET | `/` | HTML page showing visit count |
| GET | `/api/ping` | JSON health ping |
| GET/POST | `/cache/incr` | Increment Redis counter |
| GET | `/health` | Basic health check |

---

## ⚙️ Setup & Run
```bash
# Build and run containers
docker compose up --build -d

# View logs
docker compose logs -f

# Stop and clean up
docker compose down -v
