# LoanSense AI

An AI-powered intelligent loan assessment platform that combines Machine
Learning, Retrieval-Augmented Generation (RAG), Large Language Models
(LLMs), Voice AI, and Telephony to automate loan eligibility assessment,
financial risk analysis, and customer assistance.

## Overview

LoanSense AI provides an end-to-end solution for intelligent loan
processing by integrating predictive analytics with conversational AI.
The platform evaluates an applicant's financial profile, estimates loan
default probability, generates an interpretable risk score, retrieves
relevant financial policies, and delivers personalized recommendations
through a natural voice conversation.

The system is designed to improve transparency, reduce manual effort,
and provide explainable AI-driven loan recommendations.

------------------------------------------------------------------------

## Key Features

-   AI-powered loan default prediction using an ensemble Machine
    Learning model
-   Financial risk score generation
-   Retrieval-Augmented Generation (RAG) for policy-aware responses
-   Explainable recommendations using Large Language Models
-   Voice-based loan assessment through Vapi AI
-   Telephony integration using Twilio
-   FastAPI REST backend
-   Dockerized deployment
-   Cloud deployment on Hugging Face Spaces

------------------------------------------------------------------------

## System Architecture

``` text
Applicant
      │
      ▼
Voice Call (Twilio)
      │
      ▼
Vapi AI Voice Assistant
      │
      ▼
FastAPI Backend
      │
      ├───────────────► Machine Learning Model
      │                     │
      │                     ▼
      │               Risk Score
      │
      ├───────────────► RAG Pipeline
      │                     │
      │                     ▼
      │               FAISS Vector Store
      │                     │
      │                     ▼
      │           Financial Policy Retrieval
      │
      ▼
Groq LLM
      │
      ▼
Personalized Loan Recommendation
      │
      ▼
Voice Response to Applicant
```

## Technology Stack

  Category               Technologies
  ---------------------- ------------------------------------
  Programming Language   Python
  Machine Learning       Scikit-learn, XGBoost
  AI Framework           LangChain
  Vector Database        FAISS
  Embedding Model        Hugging Face Sentence Transformers
  Large Language Model   Groq (Llama 3.3 70B Versatile)
  Backend                FastAPI
  Voice AI               Vapi
  Telephony              Twilio
  Data Processing        Pandas
  Model Serialization    Joblib
  Deployment             Docker, Hugging Face Spaces

## Workflow

1.  Applicant initiates a voice call.
2.  Vapi AI collects applicant information.
3.  FastAPI validates the data.
4.  The ML model predicts loan default probability.
5.  A financial Risk Score is generated.
6.  The RAG pipeline retrieves relevant financial policies.
7.  The retrieved context and applicant information are sent to the Groq
    LLM.
8.  The LLM generates a personalized recommendation.
9.  Vapi delivers the response to the applicant.

## Machine Learning

**Model Performance**

-   Accuracy: **89%**
-   ROC-AUC Score: **0.757**

Outputs: - Default Probability - Risk Score - Prediction Confidence

## Retrieval-Augmented Generation (RAG)

Pipeline: - PDF Processing - Text Chunking - Embedding Generation -
FAISS Vector Database - Semantic Search - Context Retrieval - Prompt
Construction - LLM Response Generation

## Backend

Responsibilities: - Request validation - Loan risk prediction - Risk
score generation - RAG retrieval - Prompt generation - LLM
communication - API response generation

## Deployment

-   Docker
-   Hugging Face Spaces
-   Secure environment variables
-   Scalable cloud deployment


## Future Improvements

-   OCR-based document verification
-   Credit bureau API integration
-   Fraud detection
-   Multi-language support
-   Loan comparison engine
-   Financial planning recommendations

## License

This project is intended for educational, research, and demonstration
purposes.
