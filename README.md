# Submission-for-AI-Engineer
Stakeholder aware payment document chatbot
# Stakeholder-Aware Document QA (Fine-Tuned Classifier + QA)

This project implements a **stakeholder-aware Question Answering system** over raw PDF documents. It combines a **fine-tuned document classifier**, a **fine-tuned QA model**, FAISS for semantic retrieval.
---

## Features
- **Fine-tuned Classifier**  
  DistilBERT-based model trained on custom labeled dataset to classify documents into types like `SLA_DOC`, `UPI_TRANSACTION`, `BANK_API`, and `AUDIT_REPORT`.  
- **Fine-tuned QA Model**  
  RoBERTa (SQuAD2-based) fine-tuned on domain-specific SQuAD-style data to extract accurate answers.
  **PDF Ingestion**
  Convert uploaded pdf to chunks and embedded it in in FAISS database using index to access required metadata like doc_type,context etc.
- **FAISS Semantic Retrieval**  
  SentenceTransformers embeddings (`all-MiniLM-L6-v2`) enable semantic search over document chunks.  
- **Stakeholder Access Rules**  
  Each stakeholder can only query specific document types based on their role.
  **Query Answering**
  Using fine tuned qa model answer the query of stakeholder.
