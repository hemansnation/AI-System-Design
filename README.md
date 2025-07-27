# AI System Design

## Table of Contents

### [Module 1] - Foundations of Scalable Systems
  - **Compute Infrastructure**

    - [Virtual machines (VMs)](#virtual-machines-vms)
    - [Containers (Docker)](#containers-docker)
    - [Container orchestration (Kubernetes)](#container-orchestration-kubernetes)
  - **Networking Fundamentals**

    - [IP (internet protocol)](#ip-internet-protocol)
    - [DNS (domain name system)](#dns-domain-name-system)
    - [Load balancing](#load-balancing)
  - **Application Programming Interfaces (APIs)**

    - [REST (representational state transfer)](#rest-representational-state-transfer)
    - [gRPC (gRPC remote procedure call)](#grpc-grpc-remote-procedure-call)
  - **Data Storage**

    - [Storage Tiers](#storage-tiers)
        - Block storage
        - File storage
        - Object storage 
    - [Databases](#databases)
        - Relational databases (SQL)
        - Non-relational databases (NoSQL)
        - Vector databases
    - [Caching](#caching)
        - In-Memory data stores
        - Cache eviction policies
  - **System Architecture**

    - [Monolithic architecture](#monolithic-architecture)
    - [Microservices architecture](#microservices-architecture)
    - [Asynchronous communication](#asynchronous-communication)
        - Message queues
        - Streaming platforms (Apache Kafka)

### [Module 2] - The Machine Learning Systems Lifecycle
  - Data Engineering for AI
    - [Data Ingestion](#data-ingestion)
    - [Data Processing & Transformation](#data-processing--transformation)
    - [Data Lakes & Data Warehouses](#data-lakes--data-warehouses)
    - [Data Versioning (DVC)](#data-versioning-dvc)
    - [Feature Stores](#feature-stores)
  - Model Training
    - [Experiment Tracking (MLflow, Weights & Biases)](#experiment-tracking-mlflow-weights--biases)
    - [Distributed Training](#distributed-training)
    - [Hyperparameter Optimization](#hyperparameter-optimization)
  - Model Deployment & Serving
    - [Model Packaging & Registries](#model-packaging--registries)
    - [Serving Patterns](#serving-patterns)
    - [Serving Infrastructure](#serving-infrastructure)
    - [Deployment Strategies](#deployment-strategies)
  - Model Monitoring & Maintenance
    - [The "Silent Failure" of ML Models](#the-silent-failure-of-ml-models)
    - [Monitoring for Drift](#monitoring-for-drift)
    - [System Performance Monitoring](#system-performance-monitoring)
    - [Feedback Loops](#feedback-loops)
    - [Explainability & Bias Detection](#explainability--bias-detection)

### [Module 3] - Advanced AI System Architectures & Patterns
  - Big Data Architectural Patterns
    - [Lambda Architecture](#lambda-architecture)
    - [Kappa Architecture](#kappa-architecture)
  - Design Pattern: Real-time Recommendation System
    - [Multi-Stage Recommendation Funnel](#multi-stage-recommendation-funnel)
    - [Embedding Generation and Serving](#embedding-generation-and-serving)
    - [Real-time & Batch Feature Engineering](#real-time--batch-feature-engineering)
    - [Feature Store Integration](#feature-store-integration)
    - [A/B Testing Framework for Ranking Models](#ab-testing-framework-for-ranking-models)
  - Design Pattern: Retrieval-Augmented Generation (RAG) for LLMs
    - [Data Ingestion and Chunking Pipeline](#data-ingestion-and-chunking-pipeline)
    - [Embedding Generation for Knowledge Corpus](#embedding-generation-for-knowledge-corpus)
    - [Vector Database Indexing and Search](#vector-database-indexing-and-search)
    - [User Query Handling](#user-query-handling)
    - [Prompt Engineering and Augmentation](#prompt-engineering-and-augmentation)
    - [LLM Invocation and Response Generation](#llm-invocation-and-response-generation)
  - Design Pattern: Computer Vision System
    - [Image / Video Stream Ingestion](#image--video-stream-ingestion)
    - [Automated Inference Pipeline](#automated-inference-pipeline)
    - [Human-in-the-Loop (HITL) Subsystem](#human-in-the-loop-hitl-subsystem)
    - [Active Learning and Retraining Feedback Loop](#active-learning-and-retraining-feedback-loop)
    - [Massive-scale Media Storage](#massive-scale-media-storage)

### [Module 4] - Professional Practice & The Cutting Edge
  - Economics of AI Systems
    - [Build vs. Buy Decision Framework](#build-vs-buy-decision-framework)
    - [Compute Cost Management](#compute-cost-management)
    - [Data Cost Management](#data-cost-management)
  - Responsible AI by Design
    - [Privacy](#privacy)
    - [Security](#security)
    - [Fairness & Bias](#fairness--bias)
    - [Regulatory Compliance](#regulatory-compliance)
  - Performance Optimization
    - [Hardware Selection Tradeoffs](#hardware-selection-tradeoffs)
    - [Inference Optimization Techniques](#inference-optimization-techniques)
  - Capstone Design Projects
    - [Design a Ride-hailing ETA and Dynamic Pricing System](#design-a-ride-hailing-eta-and-dynamic-pricing-system)
    - [Design a Real-time Ad Bidding Platform](#design-a-real-time-ad-bidding-platform)
    - [Design a Personalized E-commerce Search Engine](#design-a-personalized-e-commerce-search-engine)

---

## Module 1: Foundations of Scalable Systems

### Compute Infrastructure
#### Virtual Machines (VMs)
#### Containers (Docker)
#### Container Orchestration (Kubernetes)

### Networking Fundamentals
#### IP (Internet Protocol)
#### DNS (Domain Name System)
#### Load Balancing

### Application Programming Interfaces (APIs)
#### REST (Representational State Transfer)
#### gRPC (gRPC Remote Procedure Call)

### Data Storage
#### Storage Tiers
#### Databases
#### Caching

### System Architecture
#### Monolithic Architecture
#### Microservices Architecture
#### Asynchronous Communication

## Module 2: The Machine Learning Systems Lifecycle

### Data Engineering for AI
#### Data Ingestion
#### Data Processing & Transformation
#### Data Lakes & Data Warehouses
#### Data Versioning (DVC)
#### Feature Stores

### Model Training
#### Experiment Tracking (MLflow, Weights & Biases)
#### Distributed Training
#### Hyperparameter Optimization

### Model Deployment & Serving
#### Model Packaging & Registries
#### Serving Patterns
#### Serving Infrastructure
#### Deployment Strategies

### Model Monitoring & Maintenance
#### The "Silent Failure" of ML Models
#### Monitoring for Drift
#### System Performance Monitoring
#### Feedback Loops
#### Explainability & Bias Detection

## Module 3: Advanced AI System Architectures & Patterns

### Big Data Architectural Patterns
#### Lambda Architecture
#### Kappa Architecture

### Design Pattern: Real-time Recommendation System
#### Multi-Stage Recommendation Funnel
#### Embedding Generation and Serving
#### Real-time & Batch Feature Engineering
#### Feature Store Integration
#### A/B Testing Framework for Ranking Models

### Design Pattern: Retrieval-Augmented Generation (RAG) for LLMs
#### Data Ingestion and Chunking Pipeline
#### Embedding Generation for Knowledge Corpus
#### Vector Database Indexing and Search
#### User Query Handling
#### Prompt Engineering and Augmentation
#### LLM Invocation and Response Generation

### Design Pattern: Computer Vision System
#### Image / Video Stream Ingestion
#### Automated Inference Pipeline
#### Human-in-the-Loop (HITL) Subsystem
#### Active Learning and Retraining Feedback Loop
#### Massive-scale Media Storage

## Module 4: Professional Practice & The Cutting Edge

### Economics of AI Systems
#### Build vs. Buy Decision Framework
#### Compute Cost Management
#### Data Cost Management

### Responsible AI by Design
#### Privacy
#### Security
#### Fairness & Bias
#### Regulatory Compliance

### Performance Optimization
#### Hardware Selection Tradeoffs
#### Inference Optimization Techniques

### Capstone Design Projects
#### Design a Ride-hailing ETA and Dynamic Pricing System
#### Design a Real-time Ad Bidding Platform
#### Design a Personalized E-commerce Search Engine
