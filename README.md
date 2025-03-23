
# TrendLine App - Kubernetes Deployment

This repository contains the Kubernetes configuration files for deploying the TrendLine e-commerce application in multiple environments. The application is deployed using a microservices architecture with separate components for frontend, backend, database, search, and monitoring.

## Architecture Overview

TrendLine is a clothing e-commerce application with the following components:

- **Frontend**: React.js-based web interface
- **Backend**: ASP.NET Core API
- **Database**: PostgreSQL for persistent storage
- **Search**: Apache Solr for product search functionality
- **Monitoring**: Prometheus and Grafana for metrics and visualization

## Environment Setup

The application is deployed across three separate environments, each with its own namespace:

1. **Development** - For active development and testing
2. **Staging** - For pre-production verification
3. **Production** - For live customer-facing deployment

### Resource Management

Each environment has different resource allocations and scaling configurations:

- **Development**: Single replicas with minimal resources
- **Staging**: Multiple replicas with medium resources, limited by quotas
- **Production**: Multiple replicas with higher resources, no quota limitations

## Prerequisites

- Kubernetes cluster (local or cloud-based)
- kubectl CLI tool
- Docker to build the application images

## Deployment Components

### Core Application

- **Frontend Deployment**: Web interface serving the React application
- **Backend Deployment**: API service handling business logic
- **Database StatefulSet**: PostgreSQL database for persistent storage
- **Solr StatefulSet**: Search engine for product discovery

### Monitoring Stack

- **Prometheus Deployment**: Metrics collection and storage
- **Grafana Deployment**: Metrics visualization and dashboards

### Auto-scaling

- **Horizontal Pod Autoscalers (HPAs)**: Automatically adjust pod counts based on CPU utilization
- **Vertical Pod Autoscalers (VPAs)**: Provide resource requirement recommendations


## Environment-Specific Configurations

### Development Environment

-   Single replica per component
-   Low resource requests/limits
-   No HPAs

### Staging Environment

-   Three replicas per component
-   Medium resource allocations
-   Limited by resource quota (3 CPU cores, 8GB RAM)
-   HPAs configured but with limited scaling range

### Production Environment

-   Three or more replicas per component
-   Higher resource allocations
-   No resource quota limitations
-   HPAs configured for wider scaling range

## Monitoring and Management

### Services

All environments expose services as NodePorts:

-   Frontend: port 3001
-   Backend: port 5000
-   Grafana: port 3000
-   Prometheus: port 9090

### Persistent Storage

The application uses PersistentVolumeClaims for:

-   PostgreSQL data
-   Solr indexes

## Best Practices Implemented

1.  **Environment isolation** using Kubernetes namespaces
2.  **Resource management** with requests and limits
3.  **High availability** using multiple replicas in staging/production
4.  **Auto-scaling** using HPAs for handling variable loads
5.  **Optimization assistance** using VPAs in recommendation mode
6.  **Persistent storage** for stateful components
7.  **Comprehensive monitoring** with Prometheus and Grafana
8.  **Progressive deployment** across dev/staging/prod environments

## Contact

[](https://github.com/VullnetA/TrendLine?tab=readme-ov-file#contact)

For any inquiries or support, please contact me at  [vullnetazizi9@gmail.com](mailto:vullnetazizi9@gmail.com).
