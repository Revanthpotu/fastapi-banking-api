# FastAPI Banking API

A production-style banking backend built with FastAPI demonstrating secure account management, transactions, and transfer operations with proper database consistency.

This project was designed to showcase backend engineering concepts such as API design, database transactions, authentication, containerization, and CI/CD pipelines.

---

## Architecture Overview

Client (Swagger / Postman)
        |
        v
FastAPI Application
        |
        v
Service Layer (Business Logic)
        |
        v
SQLAlchemy ORM
        |
        v
PostgreSQL Database

The application is containerized using Docker and includes a Jenkins-style CI pipeline.

---

## Features

User authentication using JWT tokens

Account management
- Create bank accounts
- View account balances
- List accounts

Transaction operations
- Deposit funds
- Withdraw funds
- Transfer money between accounts

Transaction safety
- Atomic database transactions
- Row-level locking to prevent race conditions
- Balance validation

Developer features
- Auto generated API docs via Swagger
- Dockerized environment
- Database migrations with Alembic
- Basic API testing with Pytest
- Jenkins pipeline configuration

---

## Tech Stack

Backend Framework  
FastAPI

Database  
PostgreSQL

ORM  
SQLAlchemy

Authentication  
JWT (JSON Web Tokens)

Containerization  
Docker & Docker Compose

CI/CD  
Jenkins Pipeline

Testing  
Pytest

---

## Running the Project Locally

### 1 Start PostgreSQL

docker compose up -d db

### 2 Apply database migrations
alembic upgrade head

### 3 Start the API server
uvicorn app.main:app –reload

Open the API documentation
http://localhost:8000/docs


## Running the Full Stack with Docker
docker compose up -d –build

---

## Example API Flow

1 Register user

POST /auth/register

2 Login

POST /auth/login

3 Create account

POST /accounts

4 Deposit funds

POST /transactions/deposit

5 Transfer funds

POST /transactions/transfer

---

## CI/CD Pipeline

A Jenkins pipeline configuration is included.

Pipeline stages

1 Checkout source code  
2 Install dependencies  
3 Run tests  
4 Build Docker image

This simulates a production CI workflow.

---

## Future Improvements

Account freezing support  
Daily transfer limits  
Idempotent transaction processing  
Integration tests with test database  
Kubernetes deployment

---

## Author

Revanth Potu

Backend Engineer | Data Engineer

This project was created as part of backend system design practice and interview preparation.
