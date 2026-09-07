# Retail + Finance Forecasting & Risk Platform (M5 Flagship)

## Problem
An end-to-end pipeline spanning retail demand forecasting, financial risk modeling, and a RAG layer for query-driven insights — designed to demonstrate cross-domain capability (retail + finance) in a single connected system rather than isolated single-technique projects.

## Data
M5 Walmart Forecasting dataset (real, Kaggle) — store-level and item-store level sales data.

## Approach
- SQL-based EDA and feature engineering via DuckDB (star schema)
- Demand forecasting: Prophet, ARIMA, and LightGBM compared across store/item granularity
- Financial risk layer: XGBoost risk model with SHAP-based explainability
- ChromaDB-backed RAG layer for natural-language querying of forecasting and risk outputs

## Key Results
- Multi-method forecasting comparison across store-level and item-store-level granularity
- XGBoost risk model with full SHAP interpretability for risk driver analysis
- RAG layer allows querying pipeline outputs conversationally rather than only via static dashboards/reports

## Scope note
This is the analytical core of a larger planned platform. Multi-agent orchestration and a full MLOps deployment layer (Prefect, FastAPI, Streamlit, Docker) were designed but deliberately not built into this version, since the project already demonstrates multi-agent orchestration capability through other portfolio projects — this one focuses on forecasting + risk + RAG depth instead.

## Limitations (disclosed)
- Forecasting accuracy varies meaningfully by item/store granularity — reported per-method rather than as a single blended number
- RAG layer's retrieval quality depends on chunking strategy over structured tabular outputs, an area with less mature tooling than text-document RAG

## Why this approach
Most portfolio projects demonstrate one technique in isolation. This project connects three (forecasting, risk modeling, RAG) into one coherent pipeline, closer to how a real cross-functional analytics platform would actually be structured.
