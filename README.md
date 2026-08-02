# Prompt Manager

<p align="center">

![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.115-green)
![React](https://img.shields.io/badge/React-19-blue)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o-412991)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

</p>

<p align="center">

A centralized platform for creating, organizing, testing, versioning, and deploying prompts for Large Language Model (LLM) applications.

</p>

---

# Overview

Prompt Manager is a full-stack platform that helps AI teams manage prompt engineering workflows throughout the development lifecycle.

Instead of storing prompts inside source code, Prompt Manager provides a centralized workspace where prompts can be created, tested, versioned, compared, approved, and deployed through REST APIs.

The platform supports multiple LLM providers and enables rapid experimentation while maintaining version history and collaboration.

---

# Features

## Prompt Library

Manage prompts in one centralized location.

Features include:

- Create prompts
- Edit prompts
- Delete prompts
- Organize by folders
- Tag prompts
- Search prompts
- Archive prompts

---

## Prompt Versioning

Every modification creates a new version.

```
Prompt

↓

Version 1

↓

Version 2

↓

Version 3

↓

Rollback Anytime
```

---

## Prompt Playground

Experiment with prompts before deployment.

Supports:

- Live testing
- Temperature adjustment
- Max tokens
- Top P
- Streaming
- System prompts

---

## Multi-Provider Support

Compatible with leading LLM providers.

Supported providers:

- OpenAI
- Anthropic Claude
- Google Gemini
- Ollama
- Azure OpenAI

---

## Prompt Variables

Create reusable prompt templates.

Example

```text
Hello {{customer_name}}

Your order {{order_number}} has been shipped.
```

---

## Prompt Comparison

Compare outputs from multiple models.

```
Prompt

↓

GPT-4o

Claude

Gemini

↓

Compare Responses
```

---

## Prompt Evaluation

Evaluate prompts using multiple quality metrics.

Metrics include:

- Accuracy
- Relevance
- Hallucination Rate
- Completeness
- Consistency
- Latency

---

## Prompt Approval Workflow

```
Draft

↓

Review

↓

Approved

↓

Production
```

---

## Prompt Analytics

Monitor prompt performance.

Track:

- Usage
- Response Time
- Cost
- Token Consumption
- Success Rate
- User Ratings

---

# Architecture

```
             Web Dashboard

                    │

                    ▼

             FastAPI Backend

     ┌───────────┼───────────┐

     ▼           ▼           ▼

 Prompt API   Versioning   Authentication

     │           │           │

     └───────────┼───────────┘

                 ▼

          Prompt Database

                 ▼

          LLM Providers

      ┌──────┬──────┬──────┐

      ▼      ▼      ▼

   OpenAI Claude Gemini

                 ▼

          Prompt Results
```

---

# Technology Stack

## Frontend

- React
- TypeScript
- Tailwind CSS

---

## Backend

- Python
- FastAPI
- Pydantic
- SQLAlchemy

---

## Database

- PostgreSQL
- SQLite

---

## Artificial Intelligence

- OpenAI API
- Anthropic Claude
- Google Gemini
- LangChain

---

## Authentication

- JWT
- OAuth2

---

## DevOps

- Docker
- Docker Compose
- GitHub Actions

---

# Project Structure

```
prompt-manager/

├── app/
│   ├── api/
│   ├── auth/
│   ├── prompts/
│   ├── versions/
│   ├── evaluations/
│   ├── analytics/
│   ├── services/
│   ├── database/
│   └── utils/
│
├── frontend/
├── tests/
├── docs/
├── scripts/
├── examples/
└── README.md
```

---

# Installation

Clone the repository

```bash
git clone https://github.com/ForwardAva/prompt-manager.git
```

Navigate to the project

```bash
cd prompt-manager
```

Create a virtual environment

```bash
python -m venv .venv
```

Activate the environment

Windows

```bash
.venv\Scripts\activate
```

Linux / macOS

```bash
source .venv/bin/activate
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# Environment Variables

Create a `.env` file.

```env
OPENAI_API_KEY=

ANTHROPIC_API_KEY=

GEMINI_API_KEY=

DATABASE_URL=

JWT_SECRET=
```

---

# Quick Start

Run the backend

```bash
uvicorn app.main:app --reload
```

Run the frontend

```bash
npm install

npm run dev
```

Open your browser

```
http://localhost:3000
```

---

# Core Features

- Prompt Management
- Prompt Versioning
- Prompt Playground
- Multi-Model Testing
- Prompt Evaluation
- REST API
- Authentication
- Analytics Dashboard

---

## Next Section

- REST API
- Prompt CRUD API
- Evaluation API
- Version API
- Docker
- GitHub Actions
- Testing
- Deployment
- Roadmap
- Contributing
- License

---

# REST API

Run the API server

```bash
uvicorn app.main:app --reload
```

Base URL

```
http://localhost:8000
```

Swagger UI

```
http://localhost:8000/docs
```

ReDoc

```
http://localhost:8000/redoc
```

---

# API Endpoints

## Create Prompt

```
POST /api/v1/prompts
```

Request

```json
{
  "name": "Customer Support",
  "description": "General customer support assistant",
  "provider": "openai",
  "model": "gpt-4o-mini",
  "system_prompt": "You are a helpful customer support assistant.",
  "prompt": "Answer the customer's question."
}
```

Response

```json
{
  "id": "a2c58d5d",
  "status": "created"
}
```

---

## Get Prompt

```
GET /api/v1/prompts/{id}
```

---

## Update Prompt

```
PUT /api/v1/prompts/{id}
```

---

## Delete Prompt

```
DELETE /api/v1/prompts/{id}
```

---

## List Prompts

```
GET /api/v1/prompts
```

Supports:

- Pagination
- Search
- Filtering
- Sorting

---

## Test Prompt

```
POST /api/v1/prompts/test
```

Request

```json
{
  "prompt_id": "a2c58d5d",
  "input": "Explain Retrieval-Augmented Generation."
}
```

Response

```json
{
  "response": "...",
  "tokens": 421,
  "latency_ms": 1132
}
```

---

## Compare Models

```
POST /api/v1/prompts/compare
```

Compare the same prompt across multiple providers.

Supported models

- GPT-4o
- Claude Sonnet
- Gemini Pro
- Llama 3

---

## Evaluate Prompt

```
POST /api/v1/evaluations
```

Evaluation metrics

- Accuracy
- Relevance
- Completeness
- Consistency
- Hallucination Detection
- Latency
- Cost

---

## Prompt Version History

```
GET /api/v1/prompts/{id}/versions
```

---

## Rollback Prompt

```
POST /api/v1/prompts/{id}/rollback
```

Restore any previous version instantly.

---

# Prompt Workflow

```
Create Prompt

        │

        ▼

Test Prompt

        │

        ▼

Evaluate

        │

        ▼

Review

        │

        ▼

Approve

        │

        ▼

Deploy

        │

        ▼

Production
```

---

# Example Repository Structure

```
app/

├── api/

├── auth/

├── analytics/

├── prompts/

├── evaluations/

├── providers/

├── versioning/

├── services/

├── middleware/

├── schemas/

├── database/

├── utils/

└── main.py
```

---

# Testing

Run all tests

```bash
pytest
```

Run coverage

```bash
pytest --cov=app
```

Run integration tests

```bash
pytest tests/integration
```

---

# Docker

Build

```bash
docker build -t prompt-manager .
```

Run

```bash
docker run -p 8000:8000 prompt-manager
```

Docker Compose

```bash
docker compose up -d
```

---

# Performance

| Metric            |   Result |
| ----------------- | -------: |
| Prompt Save       | < 100 ms |
| Prompt Search     | < 150 ms |
| Prompt Evaluation |  < 2 sec |
| API Latency       | < 500 ms |
| Concurrent Users  |   1,000+ |

---

# Screenshots

Replace these placeholders with your own images.

```
docs/images/dashboard.png

docs/images/prompt-library.png

docs/images/playground.png

docs/images/version-history.png

docs/images/evaluation.png

docs/images/analytics.png
```

---

# Roadmap

## Version 1.0

- [x] Prompt CRUD
- [x] Prompt Playground
- [x] Prompt Versioning
- [x] Multi-Provider Support
- [x] REST API
- [x] Authentication

## Version 1.1

- [ ] Team Collaboration
- [ ] Shared Prompt Library
- [ ] Prompt Templates
- [ ] Bulk Import & Export
- [ ] Prompt Tags

## Version 2.0

- [ ] AI Prompt Optimizer
- [ ] Auto Prompt Evaluation
- [ ] Prompt A/B Testing
- [ ] Prompt Marketplace
- [ ] Cost Optimization
- [ ] Prompt Monitoring
- [ ] Scheduled Evaluations
- [ ] Enterprise Workspaces

---

# Contributing

Contributions are welcome.

1. Fork the repository.

2. Create a feature branch.

```bash
git checkout -b feature/my-feature
```

3. Commit your changes.

```bash
git commit -m "Add prompt analytics"
```

4. Push your branch.

```bash
git push origin feature/my-feature
```

5. Open a Pull Request.

---

# Security

Never commit API keys, secrets, or credentials.

Use environment variables for all sensitive configuration.

Report security vulnerabilities privately before creating a public issue.

---

# License

This project is licensed under the MIT License.

See the `LICENSE` file for details.

---

# Author

**Oscar Garcia**

**AI Quality Engineer • LLM Evaluation Specialist • AI Application Developer**

GitHub

https://github.com/ForwardAva

---

# Future Enhancements

- Prompt Cost Dashboard
- AI Prompt Suggestions
- Prompt Quality Scoring
- Semantic Prompt Search
- Prompt Collections
- Prompt Sharing
- Prompt Scheduling
- CI/CD Integration
- Enterprise RBAC
- Audit Logs

---

# Support

If you find this project useful, consider giving it a ⭐ on GitHub.

Issues, feature requests, and pull requests are always welcome.

---

<p align="center">

Built with ❤️ using FastAPI, React, LangChain, and OpenAI.

</p>
