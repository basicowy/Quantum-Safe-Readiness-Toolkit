# Quantum-Safe Readiness Toolkit

## Overview

**Quantum-Safe Readiness Toolkit** is a web application designed to help organizations assess their preparedness for the transition to post-quantum cryptography (PQC).

The system identifies risks related to currently used cryptographic mechanisms and provides recommendations for improving quantum readiness.

---

## Features

### Organization Management

* Create organizations
* Retrieve organization details
* Delete organizations
* Store organization metadata

### Security Assessments

* Complete quantum readiness questionnaires
* Calculate risk scores
* Determine overall risk levels
* Store assessment history

### Recommendations Engine

* Generate recommendations based on assessment results
* Assign priorities to recommendations

### Dashboard

* View assessment history
* Display total number of analyses
* Show current risk level
* Provide quick insights into organizational readiness

---

## Technology Stack

### Backend

* Python
* FastAPI

### Frontend

* React
* TypeScript
* Tailwind CSS

### Database

* PostgreSQL

### Testing

* pytest

### Containerization

* Docker
* Docker Compose

### CI/CD

* GitHub Actions

---

## Project Architecture

```
React Frontend
        ↓
FastAPI Backend
        ↓
PostgreSQL Database

GitHub Actions
        ↓
Docker Build
        ↓
Deployment
```

---

## REST API Endpoints

### Organizations

| Method | Endpoint              |
| ------ | --------------------- |
| GET    | `/organizations`      |
| POST   | `/organizations`      |
| GET    | `/organizations/{id}` |
| DELETE | `/organizations/{id}` |

### Assessments

| Method | Endpoint            |
| ------ | ------------------- |
| GET    | `/assessments`      |
| POST   | `/assessments`      |
| GET    | `/assessments/{id}` |

### Recommendations

| Method | Endpoint                           |
| ------ | ---------------------------------- |
| GET    | `/recommendations/{assessment_id}` |

### Dashboard

| Method | Endpoint     |
| ------ | ------------ |
| GET    | `/dashboard` |

---

## Data Models

### Organization

```text
id
name
industry
size
created_at
```

### Assessment

```text
id
organization_id
crypto_inventory
migration_plan
nist_awareness
legacy_algorithms
score
risk_level
created_at
```

### Recommendation

```text
id
assessment_id
title
description
priority
```

---

## Installation

### Clone repository

```bash
git clone https://github.com/your-username/quantum-safe-readiness-toolkit.git

cd quantum-safe-readiness-toolkit
```

### Start with Docker Compose

```bash
docker compose up --build
```

---

## Docker Services

The application consists of three containers:

* **backend**
* **frontend**
* **postgres**

---

## Running Tests

### Unit Tests

```bash
pytest
```

Unit tests cover:

* score calculation
* risk level determination
* recommendation generation

### Integration Tests

Integration tests verify:

* `POST /assessments`
* `GET /assessments`
* PostgreSQL connectivity

---

## API Documentation

FastAPI automatically generates Swagger documentation.

After starting the application:

```text
http://localhost:8000/docs
```

---

## Project Structure

```text
quantum-safe-readiness-toolkit/
│
├── backend/
│   ├── app/
│   ├── tests/
│   ├── Dockerfile
│   └── requirements.txt
│
├── frontend/
│   ├── src/
│   ├── public/
│   ├── Dockerfile
│   └── package.json
│
├── docker-compose.yml
├── .github/workflows/
├── README.md
└── docs/
```

---

## CI/CD Pipeline

GitHub Actions performs:

1. Running tests
2. Code quality checks
3. Docker image build
4. Optional image publishing

---

## Future Improvements

* User authentication and authorization
* Export reports to PDF
* Support for multiple assessments per organization
* Visualization charts on the dashboard
* Integration with external asset inventories
* Support for NIST PQC migration checklists

---

## Background

Large-scale quantum computers may threaten widely used public-key cryptographic algorithms such as RSA and ECC. Organizations should begin preparing for this transition by:

* creating a crypto inventory,
* identifying legacy algorithms,
* improving crypto agility,
* following NIST post-quantum standards,
* developing migration plans.

---

## License

This project is created for educational purposes.
