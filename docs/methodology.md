# Methodology

## Overview

Centinela FDA Recall Analysis was designed as a structured workflow to transform public FDA recall records into a more interpretable technical risk signal.

The methodology combines public API retrieval, severity encoding, time-series engineering, statistical alert logic, and LLM-grounded narrative generation.

---

## 1. Data Retrieval

The system retrieves records from the openFDA Food Enforcement API using:

- a search term
- a date range
- filtering logic applied to recall-related fields

This allows the analytical workflow to focus on a category, ingredient term, or product-related signal within a defined time window.

---

## 2. Event Classification and Severity Encoding

FDA recall events are classified according to the standard FDA recall classes:

- **Class I**: highest relative health risk
- **Class II**: intermediate relative health risk
- **Class III**: lowest relative health risk

To make these events analytically comparable over time, recall classes are converted into a weighted monthly score:

**Risk Index = 3 × Class I + 2 × Class II + 1 × Class III**

This weighting scheme transforms categorical severity into a reproducible quantitative signal.

---

## 3. Monthly Time-Series Construction

Recall records are aggregated by month based on recall initiation date.

To preserve continuity and enable trend interpretation, the time series includes months with no events. These zero-event months are important because they prevent misleading visual jumps and allow a more accurate temporal baseline.

The output of this stage is a continuous monthly series containing:

- Class I counts
- Class II counts
- Class III counts
- weighted Risk Index

---

## 4. Signal Smoothing with a 3-Month Moving Average

Because monthly recall activity can be volatile, Centinela applies a **3-month moving average (MA 3M)** to the Risk Index.

This smoothing step helps reveal the underlying signal by reducing short-term noise. It provides a more stable view of temporal behavior than raw monthly counts alone.

---

## 5. Statistical Alert Detection

To identify unusual periods, the system calculates a **P95 threshold** from the historical distribution of the moving-average series.

Months in which the MA 3M is greater than or equal to the P95 threshold are flagged as **alert months**.

This is an important methodological step because it replaces subjective judgments such as “there seem to be many recalls” with a simple statistical rule based on the project’s own historical baseline.

---

## 6. Structured Summary Generation

After the time-series calculations are completed, the system produces a structured analytical summary including:

- total recall count
- class distribution
- severity score
- threshold value
- alert count
- moving-average metrics
- top recall drivers

This summary acts as the bridge between the statistical layer and the LLM interpretation layer.

---

## 7. LLM-Grounded Technical Narrative

The project uses an LLM to generate a technical narrative from the structured summary.

Importantly, the LLM is not used as a free-form chatbot. It is constrained by:

- upstream analytical calculations
- structured JSON-like summary inputs
- explicit consistency rules
- restrictions against inventing unsupported conclusions

This design improves interpretability while reducing the risk of hallucinated explanations.

---

## 8. Final Outputs

The final outputs of the methodology include:

- time-series dashboard
- recall detail table
- CSV export
- structured risk narrative

Together, these outputs make public FDA recall data easier to interpret for technical and business stakeholders.

---

## Methodological Positioning

Centinela should be understood as a decision-support analytics workflow. It does not establish causality, replace supplier approval procedures, or function as a formal regulatory decision engine.

Its value lies in turning public recall data into a clearer analytical signal that can support faster and more consistent technical interpretation.
