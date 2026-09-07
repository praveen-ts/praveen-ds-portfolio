# CRM Retention Intelligence Agent

## Problem
Built a customer retention risk model paired with a LangGraph agent that generates per-customer retention insights via retrieval-augmented generation (RAG), reusing the Olist e-commerce dataset from a different analytical angle (churn/retention rather than LTV).

## Data
Olist Brazilian e-commerce dataset (real, public) — same base dataset as the LTV/Attribution project, repurposed for retention risk scoring.

## Approach
- Retention/churn risk classification model
- LangGraph-based agent architecture for orchestration
- ChromaDB vector store for per-customer RAG — retrieves relevant customer history to generate contextual retention insights, rather than generic scoring alone

## Key Results
- Retention risk model: **AUC = 0.76**
- Per-customer RAG layer allows natural-language querying of "why is this customer at risk," not just a risk score in isolation

## Limitations (disclosed)
- Reuses the Olist dataset, so findings should be read as a methodology demonstration rather than a novel retention insight distinct from the LTV project
- ChromaDB retrieval quality depends on how well customer history text is chunked/embedded — not independently validated against a labeled relevance benchmark

## Why this approach
Most churn models stop at a risk score. Pairing the model with a RAG layer lets a business user ask "why" in natural language and get a grounded, customer-specific answer — closer to how retention teams actually want to consume this kind of output.
