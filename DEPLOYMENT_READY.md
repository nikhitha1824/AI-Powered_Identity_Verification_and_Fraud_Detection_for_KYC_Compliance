# Deployment Ready Guide

## Prerequisites
- Docker Desktop (or Docker Engine + Compose)

## 1) Configure environment variables
- Backend template: `backend/.env.example`
- Frontend template: `frontend/.env.example`

Set real values in `backend/.env` before production deployment.

## 2) Start all services
From project root:

```bash
docker compose up -d --build
```

This starts:
- MongoDB on port 27017
- Backend API on port 5000
- Frontend app on port 5173

## 3) Verify health
- Backend health endpoint: `http://localhost:5000/health`
- Frontend app: `http://localhost:5173`

## Notes
- Fraud scoring route now supports fallback logic if Python/ML stack is unavailable.
- For production, configure strong secrets and real SMTP credentials in `backend/.env`.
