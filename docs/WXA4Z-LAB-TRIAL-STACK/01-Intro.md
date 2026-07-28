# Lab Introduction

watsonx Assistant for Z Trial provides agentic capabilities across Z systems, offering faster deployment, ease of setup, and lower infrastructure demands.

watsonx Assistant for Z Trial integrates a central router, agents, and supporting services to deliver intelligent, conversational automation and insights across IBM Z environments.

At the core of its architecture is the central router, which acts as the primary coordination and routing layer between agents.

## watsonx Assistant for Z Architecture

![alt text](image.png)


| Core architecture component                                 | Description                                                                                                                 |
| ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| Central router                 | A unified, AI-powered routing layer that interprets user intent, gathers context, and coordinates tasks across multiple agents.    |
| Agent Lite Manager                 | A centralized interface for registering, configuring, and managing agents, ensuring streamlined onboarding, consistent settings, and efficient connectivity management.        |
| AI Agents         | Includes foundational agents, enabling domain-specific processing and supporting immediate deployment and experimentation.    |
| Chat Interface   | A conversational interface that allows users to interact with the system using natural language, providing intuitive and responsive access to platform capabilities.   |
| Model Gateway                  | A lightweight, Go-based proxy that acts as the central entry point for all model inference requests, routing them to either on-premises environments or IBM Cloud watsonx.ai while abstracting backend complexity.                         |
---

## Sections of this Lab

- Getting environment access

- Agent deployment and testing
  - zRAG Agent
  - IBM Z OMEGAMON Insights Agent
  - IBM Z Upgrade Agent

- Content Ingestion of external documents

- Testing Q&A leveraging ingested docs

