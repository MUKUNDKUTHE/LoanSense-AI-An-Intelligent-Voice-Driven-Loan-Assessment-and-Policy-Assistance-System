<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/251e05ef-f2b8-4c48-9a10-cc87c2910b7e" />
# LoanSense AI: Intelligent AI-Powered Loan Assessment & Voice Assistant

An end-to-end Artificial Intelligence platform that combines Machine Learning, Retrieval-Augmented Generation (RAG), Large Language Models (LLMs), Voice AI, and Telephony to automate loan eligibility assessment, risk analysis, and intelligent customer assistance.

---

## Live Demo

Experience LoanSense AI by making a phone call to the AI assistant.

* **Phone Number:** +1 (220) 226 7592
* **Currency Requirement:** Please ensure that all monetary values mentioned during the conversation are in Indian Rupees (INR).

During the call, the assistant collects applicant information, performs a real-time loan risk assessment, calculates a financial Risk Score, retrieves relevant financial policies using the RAG pipeline, and generates an AI-powered recommendation.

---

## Project Overview

Traditional loan assessment involves significant manual effort, repetitive customer interactions, and lengthy verification procedures. Applicants often struggle to understand their eligibility, financial risk, required documentation, and institution-specific lending policies.

LoanSense AI simplifies and automates this process using modern AI technologies. Instead of functioning as a conventional chatbot or loan calculator, the system integrates predictive Machine Learning, Retrieval-Augmented Generation (RAG), Large Language Models (LLMs), Voice AI, and cloud-native backend services into a unified solution capable of performing both financial analysis and conversational assistance over a standard phone call.

---

## Problem Statement

Traditional loan processing systems face several operational and customer experience challenges:

* **Manual Verification:** Manual verification of applicant information increases overall processing times.
* **Lack of Transparency:** Customers receive limited explanations regarding loan approval or rejection decisions.
* **Complex Guidelines:** Financial policies are distributed across lengthy documents that are difficult to interpret.
* **Inaccurate Chatbots:** Existing chatbots generate generic or inaccurate responses because they lack access to verified organizational knowledge.
* **Fragmented Architectures:** Existing solutions rarely combine predictive analytics, document retrieval, conversational AI, and voice communication into a single integrated platform.

---

## Proposed Solution

LoanSense AI addresses these core industry challenges through an integrated Artificial Intelligence architecture:

1. **Predictive Analytics:** Processes structured applicant information using an ensemble Machine Learning model to estimate the probability of loan default and generate an interpretable financial Risk Score.
2. **Knowledge Retrieval (RAG):** Searches a FAISS vector database containing financial guidelines and institutional policy documents using semantic similarity search to ground responses.
3. **Conversational Intelligence:** Processes the combined context (applicant info, risk score, and retrieved policies) via a Large Language Model hosted through Groq to produce personalized, explainable recommendations.
4. **Voice Interface:** Integrates with Vapi Voice AI and Twilio to enable users to communicate naturally over a standard telephone call.

---

## Project Objectives

* Develop an intelligent Machine Learning model capable of predicting loan default probability with high accuracy.
* Generate an interpretable Risk Score that reflects the applicant's financial credibility.
* Build a Retrieval-Augmented Generation (RAG) pipeline to minimize LLM hallucinations by grounding responses in verified document context.
* Provide explainable AI-based loan recommendations instead of simple binary outcomes.
* Automate customer support using telephony integration and deploy a scalable, cloud-native backend.

---

## Key Features

* **Machine Learning-Based Risk Prediction:** Estimates loan default probability and generates a financial Risk Score.
* **Retrieval-Augmented Generation (RAG):** Retrieves relevant sections from financial guideline documents using semantic embeddings.
* **Groq LLM Integration:** Uses Llama 3.3 70B Versatile for context-aware and natural language synthesis.
* **Voice AI Support:** Vapi integration allows natural conversational interaction, handling context and interruptions gracefully.
* **Telephony Integration:** Twilio integration enables voice calls over traditional telephone networks.
* **RESTful Backend API:** High-performance asynchronous API built using FastAPI.
* **Cloud Deployment:** Fully containerized with Docker and deployed on Hugging Face Spaces.

---

## Technology Stack

| Category | Technologies Used |
| :--- | :--- |
| **Programming Language** | Python |
| **Machine Learning** | Scikit-learn, XGBoost |
| **AI Framework** | LangChain |
| **Vector Database** | FAISS |
| **Embedding Model** | Hugging Face Sentence Transformers |
| **Large Language Model** | Groq (Llama 3.3 70B Versatile) |
| **Backend Framework** | FastAPI |
| **Voice AI** | Vapi |
| **Telephony** | Twilio |
| **Data Processing** | Pandas |
| **Model Serialization** | Joblib |
| **Deployment** | Docker, Hugging Face Spaces |

---

## Model Evaluation and Metrics

The ensemble machine learning model was evaluated on a testing dataset of 51,070 samples. The model achieved an overall accuracy of 89% and a ROC-AUC score of 0.757.

### Classification Report

| Class | Precision | Recall | F1-Score | Support |
| :--- | :--- | :--- | :--- | :--- |
| **Non-Default (Class 0)** | 0.89 | 0.99 | 0.94 | 45,139 |
| **Default (Class 1)** | 0.58 | 0.08 | 0.15 | 5,931 |
| **Accuracy** | — | — | 0.89 | 51,070 |
| **Macro Average** | 0.74 | 0.54 | 0.54 | 51,070 |
| **Weighted Average** | 0.86 | 0.89 | 0.85 | 51,070 |

### Performance Analysis

* **High Non-Default Recall (0.99):** Successfully identifies the majority of low-risk applicants, minimizing false alarms for reliable candidates.
* **Class Imbalance Challenges:** The model performs exceptionally well for the majority class but is comparatively less effective in identifying minority default cases, highlighting opportunities for future improvements via class balancing or cost-sensitive learning.

---

## System Architecture and Workflow

### Intelligent Conversation Flow

1. **Call Establishment:** Twilio receives the incoming phone call and routes the audio stream to Vapi AI.
2. **Information Collection:** Vapi welcomes the applicant and gathers financial details through interactive dialogue (Age, Income, Loan Amount, Credit Score, etc.).
3. **Function Calling:** Once all required data fields are gathered, Vapi automatically invokes the FastAPI backend.
4. **Backend Processing:**
   * FastAPI validates incoming information using structured data models.
   * The Machine Learning module calculates the Probability of Default, Risk Score, and Confidence Value.
   * The RAG Pipeline converts user context into embeddings, queries the FAISS database, and extracts relevant policy clauses.
   * The Groq LLM synthesizes the financial profile, risk score, and policy text into a personalized, coherent recommendation.
5. **Speech Response:** Vapi converts the backend's structured output into speech, and Twilio delivers the audio back to the caller in real time.

---

## Backend API Endpoints

The FastAPI backend exposes the following primary RESTful endpoints:

### 1. Home / Health Check
* **Endpoint:** `GET /`
* **Purpose:** Handles health checks, deployment verification, and API availability confirmation.

### 2. Loan Assessment Endpoint
* **Endpoint:** `POST /` (or designated inference path)
* **Purpose:** Accepts the JSON payload containing applicant parameters from Vapi, triggers the internal ML/RAG execution pipeline, and returns the generated risk analysis and transcript text.

---

## Deployment and Containerization

* **Docker:** The entire application is containerized to package the FastAPI backend, ML model files, FAISS vector indexes, and Python libraries into a single isolated environment that behaves identically across all platforms.
* **Hugging Face Spaces:** Deployed as a Docker Space providing public API accessibility, continuous deployment from Git, and secure handling of critical credentials (such as the Groq API key) via environment variables.

---

## Conclusion

LoanSense AI demonstrates a production-ready paradigm for financial automation. By bridging the gap between predictive accuracy and document-backed compliance, it delivers transparent, explainable, and accessible financial assistance via an intuitive telephone interface.


## License

This project is intended for educational, research, and demonstration
purposes.
