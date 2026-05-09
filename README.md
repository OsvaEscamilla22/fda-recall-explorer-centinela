# fda-recall-explorer-centinela
AI-assisted recall intelligence tool using public FDA data, statistical time-series analysis, and LLM-based explanation to support food safety hazard analysis.

## Confidentiality Notice
This repository is a public, sanitized showcase of the FDA Recall Explorer – Centinela project.

The project was designed to support food safety and R&D decision-making by combining public FDA recall data, statistical time series analysis, and LLM-assisted explanation in the hazard analysis.

To protect confidential implementation details, this repository does not include:
- Google Apps Script source code
- Proprietary JavaScript logic
- API keys or deployment configuration
- Internal business rules
- Private prompts or operational workflows
- Any confidential company information

All examples, screenshots, and outputs shown here are based on public OpenFDA data or sanitized demonstrations. The purpose of this repository is to communicate the problem, methodology, architecture, insights, and business value of the solution without exposing proprietary implementation details.

---

## Overview

**Centinela FDA Recall Analysis** is a decision-support solution designed to transform public FDA recall records into a more structured and actionable risk signal for food industry teams.

Instead of reviewing recalls manually as isolated events, this project reframes them as a **time-series risk monitoring problem**. It combines:

- **Public regulatory data** from the openFDA Food Enforcement API  
- **Severity-weighted analytics** based on FDA recall classes  
- **Time-series smoothing and alert logic** to detect unusual risk periods  
- **LLM-based grounded interpretation** to convert structured outputs into technical narratives for decision-making  

This showcase is intended to demonstrate how **APIs, JavaScript-based analytical logic, statistical time-series methods, and LLMs** can be applied to solve real-world problems in the food industry.

---

## Objective

The objective of this project was to build a practical analytical framework that helps translate **public FDA recall data** into technical risk intelligence for food safety, supplier review, and product development contexts.

More specifically, the project was developed to demonstrate how external recalal data can be transformed into:

- a continuous **monthly risk signal**
- an interpretable **severity score**
- an objective **statistical alert threshold**
- and a structured **LLM-assisted technical explanation**

---

## Business Problem

In the food industry, New Product Development involves a comprehensive analysis of the hazards associated with ingredients. 
This is a shared responsibility between R&D and Food Safety teams, who must conduct and validate a hazard analysis to identify and implement control measures for risk mitigation.

This analysis requires the use of data and scientific literature from multiple sources, including the FDA Draft Guidance, while also considering recall events monitored by the FDA in the marketplace.

It is precisely at this stage that a key challenge emerges.

In many food industry workflows, recall review is still performed manually and interpreted through isolated examples. This creates several limitations:

* the full historical window is not consistently considered
* event severity is not always weighted explicitly
* there is often no objective alert threshold
* temporal patterns, such as recurrence and recency, are difficult to assess

Centinela addresses this gap by converting FDA recall records into a reproducible monitoring framework that supports a more evidence-based technical interpretation.

---

## Solution Summary

At a high level, the system follows this logic:

1. A user submits a **search term** and **date range**
2. The system retrieves relevant records from the **openFDA Food Enforcement API**
3. Recall events are aggregated into a **monthly time series**
4. Each month receives a **weighted Risk Index** based on FDA recall class severity
5. A **3-month moving average (MA 3M)** is calculated to smooth volatility
6. A **P95 threshold** is used to identify unusually high-risk periods
7. A structured summary is sent to an **LLM** with consistency rules
8. The system returns:
   - a dashboard view
   - a detailed recall table
   - CSV export
   - a technical risk narrative

---

## Key Analytical Components

### 1. Public API Integration
The project uses the **openFDA Food Enforcement API** to retrieve recall events based on search terms and date filters.

### 2. Severity Encoding
FDA recall classes are transformed into a weighted monthly index:

**Risk Index = 3 × Class I + 2 × Class II + 1 × Class III**

This makes severity quantifiable and reproducible.

### 3. Time-Series Analysis
Recall events are converted into a monthly time series, including zero-event months, to preserve continuity and trend interpretation.

### 4. Signal Smoothing
A **3-month moving average (MA 3M)** is applied to reduce short-term noise and reveal the underlying temporal risk signal.

### 5. Statistical Alert Detection
A **P95 threshold** is calculated from the moving-average distribution. Months where MA 3M exceeds this threshold are flagged as alert periods.

### 6. LLM Interpretation
A structured JSON summary is generated from the analytical outputs and passed to an LLM with explicit consistency rules.  
The LLM does not replace the analysis; it translates quantified results into a technical narrative for decision support.

---

## Showcase Assets

### Solution Architecture
![Architecture Diagram](assets/architecture-diagram.png)

### Dashboard Screenshots
Dashboard images are available in:
- [`assets/dashboard-screenshots/`](assets/dashboard-screenshots/)

### Sample Outputs
Example outputs are available in:
- [`assets/sample-outputs/`](assets/sample-outputs/)

### Public Sample Data
A small public sample dataset is available in:
- [`sample-data/public-openfda-sample.csv`](sample-data/public-openfda-sample.csv)

---

## Repository Guide

### Core Documentation
- [`docs/problem-statement.md`](docs/problem-statement.md)
- [`docs/methodology.md`](docs/methodology.md)
- [`docs/architecture.md`](docs/architecture.md)
- [`docs/llm-evaluation.md`](docs/llm-evaluation.md)
- [`docs/privacy-and-confidentiality.md`](docs/privacy-and-confidentiality.md)
- [`docs/limitations.md`](docs/limitations.md)

### References
- [`references/sources.md`](references/sources.md)

---

## Example Value for Food Industry Teams

This project is relevant for teams and roles working across:

- Food Safety
- Quality and Supplier Assurance
- R&D / Product Development
- Regulatory Intelligence
- Technical Risk Assessment
- Digital Transformation in Food Operations

It shows how external regulatory data can be operationalized as a decision-support signal rather than reviewed only as anecdotal evidence.

---

## Confidentiality

This repository is intentionally presented as a **showcase** rather than a production codebase.

Included:
- problem framing
- methodology
- sanitized architecture
- screenshots
- sample outputs
- public sample data
- insights and technical interpretation

Not included:
- production JavaScript / Apps Script source code
- deployment configuration
- internal prompts in full production form
- keys, secrets, or proprietary implementation details

---

## Limitations

This project is designed as a decision-support and exploratory intelligence tool, not as a standalone regulatory or supplier approval system.

Important considerations include:

- term-based searches may capture product-level signals across multiple commercial contexts
- recall frequency does not imply direct causality for a single ingredient or supplier
- public recall data should be interpreted alongside domain expertise and internal risk assessment procedures
- LLM-generated narratives depend on the quality and structure of the analytical summary provided upstream

See [`docs/limitations.md`](docs/limitations.md) for a fuller discussion.

---

## Why This Project Matters

Centinela illustrates how a hybrid profile at the intersection of **Food Science, Data Science, API integration, time-series analytics, and LLMs** can create practical business value.

The project is not only about retrieving recalls. It is about converting public regulatory data into a clearer analytical signal that supports technical judgment in the food industry.

---

## References

A curated list of scientific and regulatory references used to frame this showcase is available at:

- [`references/sources.md`](references/sources.md)
