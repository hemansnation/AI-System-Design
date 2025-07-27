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

Let's begin with a simple picture. Imagine you have a very powerful, expensive computer server in your office. It has a lot of processing power, a huge amount of memory, and tons of storage.

Now, one of your teams needs to run a web server. They set it up, and it only uses about 10% of the computer’s power. Another team needs to run a database, and they use another 15%. A huge portion of that powerful computer is just sitting there doing nothing. This is wasteful and expensive.

What if we could safely split that one big computer into several smaller, independent computers? That is the core idea behind a Virtual Machine.

A Virtual Machine, or VM, is a complete computer that is created inside another physical computer using software.

**The Apartment Building Analogy**

Think of a physical server as a large apartment building. It has foundational resources like plumbing, electricity, and a concrete structure.

A Virtual Machine is like an individual apartment inside that building. Each apartment is a self-contained home. It has its own kitchen, its own living room, and its own front door with a lock. Even though all apartments share the building's main water line and electrical grid, what you do in your apartment does not affect your neighbor. A leak in your sink will not flood their kitchen.

The physical server is the building. The VMs are the apartments.

<img width="1198" height="957" alt="image" src="https://github.com/user-attachments/assets/e59c8a77-063e-40b1-91d3-2ba862c50b56" />


**How Does a Computer Pretend to be Many?**

It is done with a special piece of software called a hypervisor.

The hypervisor is the architect’s blueprint.

It is the first thing installed on the physical computer, and its job is to do two things:

1. The hypervisor carves up the physical computer’s resources. It says, "Okay, VM number 1 gets two CPU cores and 16 gigabytes of memory. VM number 2 gets four CPU cores and 32 gigabytes of memory." It manages access to these shared resources, making sure every VM gets its fair share.
2. The hypervisor builds "virtual walls" between the VMs. The code running in one VM has no idea that other VMs even exist. They cannot see each other’s files or interfere with each other's memory. If one VM crashes, the others keep running, just like one apartment having a power outage does not black out the entire building.


Each VM gets to run its own complete operating system. You could have one VM run Linux while another VM next to it runs Windows, all on the same physical machine.

**Why You Will Use Virtual Machines as an AI Engineer**

This concept is fundamental to almost everything you will do when building AI systems.

- You need to test a new machine learning library, but you are worried it might conflict with the other software on your machine. You can create a new, clean VM in minutes. Install whatever you want inside it. If it works, great. If it breaks everything, you just delete the VM. Your main machine is untouched. It is a clean, disposable workshop.
- You trained your model on a computer with a very specific setup. It used Ubuntu 20.04, a certain version of Python, and specific GPU drivers. To make sure it runs the same way for your colleague or in production, you can save the entire VM as a file. Anyone can then load that file and get an identical, perfectly configured computer. This solves the classic "but it works on my machine" problem.
- When you go to a cloud provider like Amazon Web Services (AWS), Google Cloud, or Microsoft Azure and ask for a "server", you are almost always getting a Virtual Machine. The cloud provider manages giant physical servers in their data centers and uses a hypervisor to rent out virtual "apartments" to you.

As an AI engineer, you will say, "I need a VM with 8 CPU cores and an NVIDIA A100 GPU" to train your model. The cloud gives you exactly that, as a self-contained unit, without you ever having to see the physical building.

So, in short, a Virtual Machine lets us use one physical computer as many separate, isolated computers. This gives us efficiency, safety, and flexibility, which are the building blocks for creating any complex AI system.

#### Containers (Docker)

We just learned how Virtual machines let us split one big computer into several smaller, independent ones. This is a huge improvement over wasting a physical server's resources. However, VMs have a noticeable inefficiency.

Each VM runs a complete, separate operating system. This means each one takes up a good chunk of disk space and memory, and can be slow to start up, sometimes taking minutes.

This led engineers to ask a follow-up question: 

`"What if we could get the isolation of a VM but let all our applications share the same underlying operating system?"`

This is the core idea behind a container.

A container is a lightweight, standalone package of software that includes everything needed to run it: the code, its runtime (like Python), system tools, and libraries.

**How It Works? Sharing the Operating System**

Instead of virtualizing the physical hardware like a VM does, a container virtualizes the operating system.

Imagine one host computer running a single Linux operating system. On top of this OS, we can run multiple containers. Each container gets its own isolated space for its files, its processes, and its network connections. However, all of these containers are directly using the kernel (the core) of the one host Linux operating system.

They are essentially just carefully separated processes from the host OS's point of view. This direct sharing of the OS kernel makes them incredibly efficient.

A quick analogy might help here. If a VM is like a separate apartment with its own plumbing and electrical box, a container is like a room within a single house. All rooms share the house's main plumbing and electricity, making them much faster and simpler to build, but they still have their own locked doors for privacy.

Docker is the tool that made this concept easy and popular. 

It provides a simple way to build a "recipe" for your container (a Dockerfile) and package it into a portable blueprint (an Image) that you can run anywhere.

**Why You Will Use Containers as an AI Engineer**

For modern AI development, containers have become the standard.

Here’s why this matters directly to your work:

- Your machine learning model is not just a single model file. It is the model file plus the specific version of PyTorch or TensorFlow you used, the exact Python version, a particular system library, and other dependencies. A container bundles all of this together into a single, predictable package. When you send this container to someone else, you are sending a guaranteed working environment.
- Imagine your AI application suddenly gets a huge burst of traffic. You need to launch 100 new copies of your model's prediction service right now. Starting 100 VMs could take many minutes. Starting 100 containers often takes just a few seconds. This speed is critical for building systems that can react quickly to changes in demand.
- With containers, the environment you build and test on your laptop is the exact same environment that runs in the cloud for production. This eliminates a massive category of bugs that come from small differences between machines. It is the ultimate solution to the "but it works on my machine" problem.

**To summarize the key difference:**

- A Virtual machine is a full OS on top of virtualized hardware. It is heavy but provides very strong isolation.
- A Container is just your application and its dependencies running on a shared OS. It is light and fast.


For most modern AI applications, containers are the preferred choice because of their incredible speed and efficiency.



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
