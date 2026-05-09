# Architecture

## Architecture Philosophy

Centinela is presented in this repository as a **sanitized showcase architecture**.

The goal of this document is to explain how the solution works at a system level without exposing proprietary implementation details or production source code.

---

## High-Level Flow

The architecture can be understood as a sequence of analytical layers:

1. **User Input Layer**  
   A user provides a search term and date range to define the scope of the recall query.

2. **Public Data Retrieval Layer**  
   The system retrieves public recall records from the openFDA Food Enforcement API.

3. **Processing and Normalization Layer**  
   Retrieved records are filtered, parsed, and transformed into a structured analytical dataset.

4. **Time-Series Engineering Layer**  
   Recall events are aggregated into a monthly time series, including zero-event months for continuity.

5. **Risk Analytics Layer**  
   The system computes:
   - class-specific monthly counts
   - weighted Risk Index
   - 3-month moving average
   - P95 alert threshold
   - alert-month detection

6. **Structured Summary Layer**  
   Key analytical outputs are converted into a structured summary used for downstream interpretation.

7. **LLM Interpretation Layer**  
   The LLM receives the structured summary and generates a grounded technical narrative under explicit consistency constraints.

8. **Output Layer**  
   The final user-facing outputs include:
   - dashboard visualization
   - recall detail table
   - downloadable CSV
   - technical narrative

---

## Design Principles

The architecture was guided by the following principles:

### 1. Public-Data-Driven
The workflow is built around public FDA data, making the analytical logic explainable and externally grounded.

### 2. Analytical Before Generative
The LLM is positioned downstream of the statistical workflow. This means the analytical core generates the signal first, and the LLM interprets it second.

### 3. Explainability Through Structure
The use of explicit class counts, weighted severity, moving averages, and alert thresholds helps preserve interpretability.

### 4. Portfolio-Safe Abstraction
This showcase intentionally describes the system at a conceptual level. It communicates architecture, analytical flow, and business value without exposing confidential source code.

---

## What Is Not Included

This document does not disclose:

- production JavaScript / Apps Script files
- exact deployment implementation
- proprietary front-end logic
- private configuration details
- operational secrets or credentials

---

## Related Asset

See the main repository architecture image:

- `assets/architecture-diagram.png`
