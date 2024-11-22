# Multi-K8s Fibonacci Calculator

## Overview

This project is a simple Kubernetes learning experience demonstrating a microservices architecture for a Fibonacci number calculator. It showcases the basics of cloud-native application design, continuous integration/deployment, and Kubernetes cluster management.

## Project Architecture

### System Components

#### 1. Frontend (Client)
- **Technology**: React.js
- **Functionality**: 
  - Provides a user-friendly web interface
  - Allows users to input numbers
  - Displays Fibonacci calculation results
  - Communicates with backend services

#### 2. Backend (Server)
- **Technology**: Node.js
- **Key Responsibilities**:
  - Validate user input
  - Manage database interactions
  - Coordinate calculation requests
  - Handle data persistence and retrieval

#### 3. Worker
- **Technology**: Node.js
- **Pub/Sub Model**:
  - Subscribes to Redis message queue
  - Generates Fibonacci numbers
  - Publishes results back to Redis

#### 4. Databases
- **PostgreSQL**:
  - Stores user input indices
  - Provides persistent storage for requests

- **Redis**:
  - Serves as a message queue
  - Facilitates communication between server and worker
  - Caches calculation results

## Infrastructure and Deployment

### Kubernetes Cluster
- **Platform**: Google Kubernetes Engine (GKE)
- **Ingress Management**: 
  - Nginx Ingress Controller
  - URL-based routing
  - TLS encryption

### Continuous Integration/Continuous Deployment (CI/CD)
- **Platform**: GitHub Actions
- **Workflow**:
  1. Code changes trigger automated testing
  2. Successful merges to main branch initiate:
     - Docker image builds
     - Automatic deployment to GKE cluster

## Technical Highlights

- Microservices architecture
- Kubernetes orchestration
- Dockerized components
- Scalable design
- Secure communication
- Automated deployment pipeline

## Architectural Diagram

```
[User] --> [Nginx Ingress]
             |
    +--------+--------+
    |                 |
[React Client]   [Node.js Server]
                     |
            +--------+--------+
            |                 |
        [PostgreSQL]      [Redis]
                             |
                         [Worker]
```

## Future Improvements

- Implement advanced load balancing strategies
- Add horizontal pod autoscaling
- Enhance monitoring and logging
- Implement more robust error handling
- Add comprehensive performance metrics

## Getting Started

### Prerequisites
- Kubernetes cluster
- Docker
- kubectl
- GitHub Actions (for CI/CD)

### Local Development
1. Clone the repository
2. Set up local Kubernetes environment
3. Apply Kubernetes manifests
4. Configure environment variables

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request
