# Quantum-Safe Readiness Toolkit – Project Plan

## 1. Project Goal

The goal of the project is to develop a web application that helps organizations assess their readiness for the transition to post-quantum cryptography and identify risks associated with currently used cryptographic solutions.

The system provides a simple assessment mechanism, calculates the risk level, and generates recommendations that support migration planning.

---

## 2. Objectives

* Create a REST API for managing organizations and assessments.
* Store assessment results in a database.
* Implement a risk-scoring mechanism.
* Generate recommendations based on identified weaknesses.
* Provide a dashboard presenting current readiness status.
* Ensure easy deployment using Docker.
* Implement automated testing and CI/CD.

---

## 3. Scope of the Project

### Included Features

#### Organization Management

* Add organizations
* Retrieve organizations
* Delete organizations

#### Assessments

* Fill in readiness questionnaires
* Store assessment results
* Calculate risk scores
* Determine risk levels

#### Recommendations

* Generate recommendations based on assessment outcomes
* Assign priorities to recommendations

#### Dashboard

* Assessment history
* Number of completed assessments
* Current risk level

---

## 4. Technology Stack

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

## 5. Functional Requirements

### FR1 – Organization Management

The system shall allow users to:

* create organizations,
* retrieve organization details,
* delete organizations.

### FR2 – Assessment Management

The system shall:

* accept questionnaire responses,
* calculate scores,
* assign risk levels,
* store assessment history.

### FR3 – Recommendation Engine

The system shall generate recommendations according to assessment results.

### FR4 – Dashboard

The system shall display:

* current risk level,
* total number of assessments,
* assessment history.

---

## 6. Non-Functional Requirements

* REST API architecture.
* Persistent data storage using PostgreSQL.
* Docker-based deployment.
* Unit and integration tests.
* Automatic API documentation with Swagger.
* Source code versioning using Git.

---

## 7. Data Model

### Organization

* id
* name
* industry
* size
* created_at

### Assessment

* id
* organization_id
* crypto_inventory
* migration_plan
* nist_awareness
* legacy_algorithms
* score
* risk_level
* created_at

### Recommendation

* id
* assessment_id
* title
* description
* priority

---

## 8. REST API

### Organizations

* GET /organizations
* POST /organizations
* GET /organizations/{id}
* DELETE /organizations/{id}

### Assessments

* GET /assessments
* POST /assessments
* GET /assessments/{id}

### Recommendations

* GET /recommendations/{assessment_id}

### Dashboard

* GET /dashboard

---

## 9. Testing Strategy

### Unit Tests

* score calculation,
* risk-level determination,
* recommendation generation.

### Integration Tests

* POST /assessments,
* GET /assessments,
* PostgreSQL communication.

---

## 10. CI/CD Pipeline

GitHub Actions will:

1. Execute automated tests.
2. Perform code quality checks.
3. Build Docker images.
4. Prepare the application for deployment.

---

## 11. Project Architecture

```text
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

## 12. Development Stages

### Stage 1 – Project Initialization

* Create repository
* Configure FastAPI
* Configure React application
* Create Docker environment

### Stage 2 – Database Layer

* Design database schema
* Create models
* Configure PostgreSQL connection

### Stage 3 – REST API

* Implement organization endpoints
* Implement assessment endpoints
* Implement recommendation endpoints

### Stage 4 – Business Logic

* Implement score calculation
* Implement risk classification
* Implement recommendation engine

### Stage 5 – Frontend

* Create forms
* Display results
* Build dashboard

### Stage 6 – Testing

* Unit tests
* Integration tests

### Stage 7 – Documentation

* README
* Architecture diagram
* API documentation

---

## 13. Future Improvements

* Authentication and authorization
* PDF report generation
* Advanced analytics dashboard
* Support for additional PQC frameworks
* Integration with external asset inventories
* Multi-user suppor