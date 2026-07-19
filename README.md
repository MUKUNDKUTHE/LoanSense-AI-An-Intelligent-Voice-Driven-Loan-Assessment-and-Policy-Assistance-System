LoanSense AI: Intelligent Voice-Driven Loan Assessment & Policy Assistant
An AI-powered voice-first loan assistant that provides instant loan eligibility insights using Machine Learning, Retrieval-Augmented Generation (RAG), and Large Language Models. Users simply call a US phone number and interact naturally to receive personalized loan guidance in real time.

Live Demo
Call the AI Loan Assistant (US Number)

+1 220-226-7592

Ask about loan eligibility, estimated loan amount, banking policies, documentation requirements, or repayment guidance through a natural voice conversation.

Problem Statement
Traditional loan eligibility assessment is often slow and requires multiple manual verification steps. Customers typically need to:

Visit a bank branch
Submit multiple documents
Wait 2–3 working days
Undergo manual verification
Receive no immediate estimate of their loan eligibility

LoanSense AI simplifies this process by providing an intelligent conversational experience that delivers instant, explainable loan assessments.

Features
Voice-driven AI assistant
Machine learning-based loan risk prediction
Retrieval-Augmented Generation (RAG)
Policy-backed loan guidance
Natural language conversations
Real-time responses
Secure API architecture
Cloud deployment

Architecture
                 User
                   │
                   ▼
           Phone Call (Vapi AI)
                   │
                   ▼
            Speech-to-Text
                   │
                   ▼
             FastAPI Backend
          ┌────────┴─────────┐
          │                  │
          ▼                  ▼
    ML Risk Model        RAG Pipeline
          │                  │
          ▼                  ▼
      Risk Score      Policy Retrieval
          └────────┬─────────┘
                   ▼
             Groq Llama 3.3
                   │
                   ▼
          AI Loan Recommendation
                   │
                   ▼
          Text-to-Speech (Vapi)
                   │
                   ▼
                 Caller
                 
Machine Learning
LoanSense AI uses an ensemble Machine Learning model to estimate an applicant's loan risk.

Input Parameters
Annual Income
Loan Amount
Credit Score
Employment Years
Existing Loans
Loan Term
Home Ownership
Marital Status
Number of Dependents
Education Level
Output
Risk Score
Prediction Confidence
Loan Eligibility Estimate

Retrieval-Augmented Generation (RAG)
The assistant retrieves relevant banking policies from official documents before generating responses.

Bank Policy PDFs
        │
        ▼
Text Extraction
        │
        ▼
Chunking
        │
        ▼
Hugging Face Embeddings
        │
        ▼
FAISS Vector Database
        │
        ▼
Relevant Context Retrieval
        │
        ▼
Groq Llama 3.3
        │
        ▼
Natural Language Response

Voice AI Workflow
Phone Call
     │
     ▼
Speech Recognition
     │
     ▼
FastAPI Backend
     │
     ▼
Machine Learning Prediction
     │
     ▼
Policy Retrieval
     │
     ▼
LLM Response
     │
     ▼
Speech Synthesis

Tech Stack
Artificial Intelligence & Machine Learning
Python
Scikit-learn
XGBoost
LightGBM
CatBoost
LLM & RAG
LangChain
FAISS
Hugging Face Embeddings
Groq API
Llama 3.3
Backend
FastAPI
Uvicorn
Pydantic
Voice
Vapi AI
Twilio
Deployment
Docker
Hugging Face Spaces


Workflow
User calls the AI assistant.
Speech is converted into text.
Applicant details are collected.
The Machine Learning model predicts the loan risk score.
Relevant banking policies are retrieved using RAG.
Llama 3.3 generates an explainable response.
The response is converted back to speech.
The user receives instant loan guidance.

API Endpoint
POST
/loan-assessment

Sample Response
{
  "risk_score": 715,
  "confidence": 0.92,
  "answer": "Based on your financial profile, you are likely eligible for the requested loan amount."
}

Future Enhancements
Multi-bank policy support
Multilingual voice interaction
Real-time credit score integration
Aadhaar and PAN verification
OCR-based document processing
Personalized EMI optimization
Loan comparison across multiple banks

License
This project is intended for educational, research, and hackathon purposes.
