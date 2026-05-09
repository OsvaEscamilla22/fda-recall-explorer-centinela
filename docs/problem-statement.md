# Problem Statement

## Context

Food industry teams often need to review external recall information when assessing ingredients, product categories, or potential food safety concerns. 
In practice, this review is frequently performed manually by searching public sources and interpreting individual recall cases one by one.

Although this approach may provide useful examples, it has important limitations. It does not consistently account for the full historical window, does not explicitly weight events by severity, and does not provide an objective way to determine whether a recall signal is unusually high or simply part of the normal baseline.

## Core Problem

The core problem addressed by Centinela is the lack of a structured analytical framework to convert public FDA recall data into a more interpretable risk signal for technical decision-making.

Without such a framework, recall review may become:

- anecdotal rather than systematic
- reactive rather than analytical
- difficult to compare across time
- vulnerable to subjective interpretation

## Why It Matters

For food industry teams, this gap matters because public recall data can contain useful signals related to contamination patterns, labeling issues, allergen failures, process breakdowns, and recurring technical drivers. 
However, these signals are difficult to interpret consistently when they are reviewed only as isolated cases.

A more robust approach should help answer questions such as:

- Is the observed recall activity historically unusual?
- Is the signal driven by low-severity events or by higher-severity recalls?
- Are there recurrent patterns that deserve closer technical review?
- Can public regulatory data be summarized into a format that supports faster technical judgment?

## Project Response

Centinela addresses this problem by reframing recall monitoring as a time-series analytics problem supported by structured interpretation.

Instead of treating recalls as disconnected events, the project converts them into a continuous monthly signal, applies severity weighting, smooths volatility through a moving average, and uses a statistical threshold to identify alert periods. A grounded LLM layer then translates the structured outputs into a technical narrative for decision support.

## Intended Value

The project is intended to support better evidence-based interpretation in contexts such as:

- food safety review
- supplier assessment
- ingredient/category screening
- regulatory intelligence
- technical risk communication

Centinela does not replace domain expertise or formal regulatory procedures. Its purpose is to strengthen technical interpretation by turning public recall data into a clearer analytical signal.
