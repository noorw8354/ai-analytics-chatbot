# Retail Intelligence System — AI-Powered Analytics Chatbot

A conversational analytics assistant built on real retail sales data. Ask business questions in plain English and get instant, data-grounded answers — no SQL required.

---

## What it does

This project demonstrates an end-to-end data pipeline from raw retail data through SQL-modelled views to an AI analyst layer powered by Google Gemini.

- Load and clean the Superstore sales dataset (9,994 rows, 2014–2017)
- Transform data into 5 structured SQL views covering monthly performance, product profitability, regional analysis, customer segmentation, and discount impact
- Feed live view data into a Gemini LLM with a structured system prompt acting as a senior retail analyst
- Answer natural language business questions with full context from all 5 views simultaneously
- Interactive chat widget for ongoing conversation with memory across turns
- Sales forecasting using Prophet with trend and seasonality decomposition

---

## Tech stack

| Layer | Tools |
|---|---|
| Data ingestion | Python, Pandas |
| Data transformation | SQL (SQLite views), NumPy |
| AI / LLM layer | Google Gemini 2.5 Flash via `google-genai` |
| Forecasting | Prophet |
| Interface | ipywidgets (interactive chat UI) |
| Environment | Google Colab |

---

## Architecture

```
Raw CSV (Superstore Sales)
        ↓
  Data Cleaning & Feature Engineering
  (dates, margins, ship days, derived columns)
        ↓
  SQLite In-Memory Database
        ↓
  5 SQL Views (semantic layer)
  ├── vw_monthly_performance
  ├── vw_product_performance
  ├── vw_region_performance
  ├── vw_customer_segments
  └── vw_discount_impact
        ↓
  Gemini LLM (RAG-style: all views injected as context)
        ↓
  Natural Language Answer + Multi-turn Chat
```

---

## Sample questions you can ask

- Which category has the worst profit margins?
- Are our discounts helping sales or destroying margins?
- Which states should we prioritise or consider exiting?
- Who are the top 10 most profitable customers?
- Give me a full business health check.

---

## Dataset

[Superstore Sales Dataset](https://github.com/leonism/sample-superstore) — public retail dataset covering US orders across Furniture, Office Supplies, and Technology categories across 4 regions (West, East, Central, South).

---

## How to run

1. Open the notebook in Google Colab
2. Add your Gemini API key where indicated (`API_KEY = "..."`)
3. Run all cells in order
4. Use the chat widget at the bottom to ask business questions

Get a free Gemini API key at [aistudio.google.com](https://aistudio.google.com)

---

## Author

**Noor Wali** — Senior Data Analyst | Analytics · AI · eCommerce  
[LinkedIn](https://www.linkedin.com/in/noor-wali-data-analyst/)· [Portfolio](https://linktr.ee/noorwale)
