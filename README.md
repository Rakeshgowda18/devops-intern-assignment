Project Structure

├── docker-compose.yml
├── nginx
│ ├── nginx.conf
│ └── Dockerfile
├── service_1 (Golang)
│ ├── main.go
│ ├── Dockerfile
│ └── go.mod
├── service_2 (Python Flask)
│ ├── main.py
│ ├── requirements.txt
│ └── Dockerfile
└── README.md

yaml file,


---

# Setup Instructions

# 1. Prerequisites

- Docker Desktop installed and running
- Docker Compose enabled
- Git (for version control)

---

### 2. How to Run the Project

In the root of the project directory:

```bash
docker compose up --build

-----------
This builds and starts:

Golang service at /service1

Python Flask service at /service2

Nginx reverse proxy on localhost:8080

3. Test Endpoints
Open the browser or use curl:

http://localhost:8080/service1 – Golang app

http://localhost:8080/service2 – Python Flask app

Routing Logic
The Nginx reverse proxy handles path-based routing:

/service1 → forwards to Golang backend

/service2 → forwards to Python backend

All traffic passes through the proxy container.

Logging
Nginx logs all incoming requests with timestamps and paths in the container logs. To view:
bash : docker logs <nginx-container-id>


Bonus Features:'
Path-based routing with reverse proxy

 Centralized access via localhost:8080

 Basic request logging

 (Optional) Add HEALTHCHECK in Dockerfiles for service status

Tech Stack
Docker

Docker Compose

Golang

Python Flask

Nginx (reverse proxy)
