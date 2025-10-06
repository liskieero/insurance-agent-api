# Autonomous Insurance Agent API 🤖📄

This project is an API service built on the Google Cloud Platform (GCP) that utilizes a generative AI agent to analyze insurance policy documents. The agent can interpret free-form user queries, retrieve information from insurance terms and conditions (PDFs), and calculate an estimated compensation amount, taking into account factors like deductibles and age-based depreciation.

## Why is this project useful?

* **Business Value:** Automates the manual work typically done by claims handlers. It provides customers with instant and consistent answers to questions about their insurance policies, improving the customer experience.
* **Technical Showcase:** Demonstrates how to build a modern AI architecture (RAG + Agents) in the cloud. It shows the ability to process unstructured data (PDFs), build multi-step reasoning chains, and utilize external tools (like a calculator).

---

## Architecture

The system consists of two main parts: an offline pipeline for data processing and an online API for handling real-time queries.

#### 1. Offline: Data Preprocessing
`PDF Document -> GCS -> Cloud Function -> Vertex AI Gemini API (Embeddings) -> Vertex AI Vector Search`

#### 2. Online: API Request Handling
`HTTPS Request -> Cloud Run (FastAPI) -> Agent (LangGraph) -> Tool Calls (RAG, Calculator) -> Vertex AI Gemini API (Synthesis) -> JSON Response`

---

## Technology Stack

* **Cloud Platform:** Google Cloud Platform (GCP)
* **Services:** Cloud Run, Cloud Storage, Cloud Functions, Vertex AI Gemini API, Vertex AI Vector Search
* **Language:** Python 3.11+
* **Backend:** FastAPI
* **AI/Agent Framework:** LangGraph
* **Containerization:** Docker
