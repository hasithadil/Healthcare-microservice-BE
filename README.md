# Healthcare Management Microservices System

A production-style healthcare management system built with **Spring Boot Microservices**. This project demonstrates modern backend development using REST APIs, gRPC, Apache Kafka, JWT authentication, Docker, PostgreSQL, API Gateway, automated testing, and AWS infrastructure deployment.

The project was developed by following an end-to-end microservices architecture while implementing production-oriented design patterns and best practices.

---

## Project Overview

This system consists of multiple independent microservices that communicate through synchronous and asynchronous communication patterns.

### Services

- Patient Service
- Billing Service
- Analytics Service
- Authentication Service
- API Gateway

Each service is independently deployable and containerized using Docker.

---

## Architecture

```
                        Client
                           │
                    API Gateway
                           │
        ┌───────────┬─────────────┬─────────────┐
        │           │             │             │
        ▼           ▼             ▼             ▼
 Patient Service  Auth Service  Billing Service Analytics Service
        │              │
        │              │
        ▼              ▼
 PostgreSQL      PostgreSQL

Patient Service ───── gRPC ─────► Billing Service

Patient Service ───── Kafka ─────► Analytics Service
```

---

# Features

## Patient Service

- CRUD Operations
- Request Validation
- Global Exception Handling
- REST API
- OpenAPI / Swagger Documentation
- PostgreSQL Integration

---

## Billing Service

- gRPC Server
- Billing Creation
- Protocol Buffers
- Dockerized Deployment

---

## Analytics Service

- Kafka Consumer
- Event Processing
- Analytics Logging

---

## Authentication Service

- User Login
- JWT Token Generation
- Token Validation
- Spring Security
- Password Encryption
- PostgreSQL Database

---

## API Gateway

- Route Configuration
- JWT Authentication Filter
- Request Forwarding
- Service Integration

---

# Technologies Used

### Backend

- Java 21
- Spring Boot 3
- Spring MVC
- Spring Data JPA
- Spring Security

### Databases

- PostgreSQL
- H2 (Initial Development)

### Communication

- REST API
- gRPC
- Protocol Buffers
- Apache Kafka

### Containerization

- Docker
- Docker Compose

### Authentication

- JWT
- BCrypt Password Encoder

### Documentation

- Swagger / OpenAPI

### Testing

- Integration Testing
- JUnit 5

### Cloud & Infrastructure

- AWS
- CloudFormation
- LocalStack
- ECS
- Application Load Balancer
- VPC
- MSK (Managed Kafka)
- RDS

### Tools

- IntelliJ IDEA
- Maven
- Git
- GitHub

---

# Project Structure

```
healthcare-system
│
├── patient-service
├── billing-service
├── analytics-service
├── auth-service
├── api-gateway
└── infrastructure
```

---

# Communication Flow

## REST

Client

↓

API Gateway

↓

Patient Service

---

## gRPC

Patient Service

↓

Billing Service

---

## Kafka

Patient Service

↓

Kafka Topic

↓

Analytics Service

---

# Authentication Flow

```
User
 │
 ▼
Auth Service
 │
 ▼
JWT Token
 │
 ▼
API Gateway
 │
 ▼
Protected Microservices
```

---

# Infrastructure

Infrastructure is provisioned using AWS CloudFormation.

Resources include:

- VPC
- PostgreSQL Databases
- MSK Kafka Cluster
- ECS Cluster
- ECS Services
- Application Load Balancer

Local development and testing are performed using LocalStack.

---

# Running the Project

## Prerequisites

- Java 21
- Maven
- Docker
- PostgreSQL
- Kafka
- LocalStack
- AWS CLI

---

## Clone Repository

```bash
git clone https://github.com/<your-username>/<repository-name>.git
```

---

## Build

```bash
mvn clean install
```

---

## Run Services

Each service can be started individually.

Example:

```bash
cd patient-service

mvn spring-boot:run
```

Or run using Docker.

---

# API Documentation

Swagger UI is available once services are running.

Example:

```
http://localhost:<port>/swagger-ui/index.html
```

---

# Learning Outcomes

This project demonstrates practical experience with:

- Microservices Architecture
- Spring Boot
- REST API Development
- gRPC Communication
- Apache Kafka Messaging
- JWT Authentication
- Spring Security
- Docker Containerization
- PostgreSQL
- API Gateway
- Integration Testing
- AWS CloudFormation
- LocalStack
- Infrastructure as Code (IaC)

---

# Future Improvements

- Service Discovery
- Centralized Configuration
- Distributed Tracing
- Monitoring with Prometheus & Grafana
- CI/CD Pipeline
- Kubernetes Deployment
- Resilience4j Circuit Breaker

---

# Acknowledgements

This project was built as part of a comprehensive Spring Boot Microservices learning journey and extended with production-oriented practices to gain hands-on experience with modern backend development.
