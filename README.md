# Containerized Web App Infrastructure

Test Web App Deployment Architecture (Work In Progress)

Overview: This project deploys a docker-containerized app onto a privately managed on-prem server using CI/CD automation. The system wil employ industry-standard tools for traffic routing and app lifecycle monitoring.

Purpose: The purpose of this project is to further implement DevOps principles in a production-like environment. My previous project focused on cloud deployment with AWS ECS + Cloudwatch; this project explores deplpying services in an on-prem environment. The app employs a spring boot backend to expand my experience beyond flask and node. App traffic will be handled with nginx, which replicates industry practices. Grafana will be used to monitor app health, with plans to send out alerts in cases of service errors.

# Tech Stack:

Frontend: (TBD)
Backend: Spring Boot
Database: MongoDB (TBD)
Deployment: Github Actions, Docker
Tools: Nginx, Grafana

## Architecture:
```
User
 │
 │ HTTP Requests
 ▼
Nginx (Reverse Proxy)
 │
 └── Routes "/api" → Backend Container


GitHub Repository
 │
 │ Code Push
 ▼
GitHub Actions (CI/CD)
 │
 ├── Build Docker Images
 ├── Tag Images (latest + commit)
 └── Deploy Update
        │
        ▼
   On-Prem Server
        │
        ├── Pull Updated Images
        └── Restart Backend
```
