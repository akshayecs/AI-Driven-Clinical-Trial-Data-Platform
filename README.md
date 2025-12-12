# AI-Driven Clinical Trial Data Platform
A Production-Ready HealthTech System with AI, Realtime Monitoring, Secure Payments & DevOps

##🚀 Overview
The AI-Driven Clinical Trial Data Platform is a full-stack, cloud-deployable HealthTech application designed to simulate the workflows of modern decentralized clinical trials (DCTs).
It integrates:
AI-powered clinical reasoning (LangChain.js + OpenAI + RAG)
Real-time clinician dashboards
Secure patient data management
Subscription billing via Razorpay
Production-grade DevOps with Docker, AWS EC2, CI/CD
System monitoring using Prometheus & Grafana
This project demonstrates enterprise engineering practices and is ideal for showcasing full-stack, backend, AI, and DevOps capabilities.

##🏗️ Architecture Overview
The platform follows a monorepo architecture with modular boundaries:
ai-clinical-trials/
│── apps/
│   ├── frontend/      → Next.js (Patient + Clinician portals)
│   └── backend/       → NestJS API (modular: auth, ai, billing, trials)
│── packages/
│   ├── shared-types/  → Reusable DTOs / TypeScript types
│   └── utils/         → Common utilities & logger
│── infra/
│   ├── docker/        → Dockerfiles, docker-compose, Prometheus config
│   └── nginx/         → Reverse proxy config (for EC2)
│── .github/workflows/ → CI/CD pipelines
└── README.md

#TechStacks
| Layer      | Technology                                              |
| ---------- | ------------------------------------------------------- |
| Frontend   | Next.js, React, Tailwind CSS                            |
| Backend    | Node.js, NestJS, Prisma                                 |
| Database   | PostgreSQL                                              |
| AI/ML      | OpenAI API, LangChain.js, LangGraph-style orchestration |
| Vector DB  | Chroma / Pinecone                                       |
| Realtime   | Socket.io                                               |
| Payments   | Razorpay (Subscriptions + Webhooks)                     |
| Infra      | Docker, Nginx, AWS EC2                                  |
| Monitoring | Prometheus, Grafana                                     |
| CI/CD      | GitHub Actions                                          |


##🎯 Key Features
🧑‍⚕️ 1. Patient & Clinician Portals (Next.js)
Clean and responsive UI
Authenticated workflows
Patient symptom submission
Clinician dashboard with real-time severity analysis

🤖 2. AI Clinical Assistant (LangChain.js + RAG)
A multi-step AI workflow inspired by LangGraph:
Extract symptoms from patient text
Retrieve relevant clinical guidelines (RAG)
Evaluate severity based on embeddings + rules
Trigger real-time clinician alerts if needed
Log safe severity reports into DB
###Key AI Components:
LLM reasoning via OpenAI
Vector similarity search
Embedding-based guideline matching
Stateful agent pipeline

##🧱 3. Modular Backend (NestJS + Prisma + PostgreSQL)
Modules: auth, users, trials, ai, billing, monitoring
JWT-based authentication (access + refresh tokens)
RBAC (Patient / Clinician / Admin)
Prisma migrations & type-safe DB access
WebSocket gateway for real-time alerts
Secure Razorpay subscription & webhook handlers

##💳 4. Razorpay Billing (UPI Supported)
Subscription creation
Order history
Webhook signature verification
Role activation/deactivation based on payment status

##📡 5. Real-Time Monitoring (Prometheus + Grafana)
Backend exposes metrics:
API latency
Error rate
AI inference counts
Database query performance
Grafana visualizes dashboards for system health.

##⚙️ 6. DevOps & CI/CD

Fully containerized:

command : "docker compose up --build"

GitHub Actions Pipeline:
Lint
Test
Build
Deploy to EC2 over SSH
Restart Docker services automatically
AWS EC2 Setup Includes:
Nginx reverse proxy
HTTPS via Certbot
Docker Compose runtime

##📂 Project Structure
ai-clinical-trials/
├── apps/
│   ├── frontend/          # Next.js web application
│   └── backend/           # NestJS API server
├── packages/
│   ├── shared-types/      # Global DTOs and TS interfaces
│   └── utils/             # Logging, helpers
├── infra/
│   ├── docker/            # Dockerfiles + compose
│   └── prometheus/        # Prometheus config
├── .github/workflows/     # CI/CD YAML
├── .env.example
└── README.md
