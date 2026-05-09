# Limitations

Centinela is designed as a decision-support analytics workflow, not as a formal regulatory decision engine or a standalone supplier approval system.

## 1. Term-Based Retrieval Has Contextual Limits

Searches based on terms such as ingredient or product keywords may capture a wide variety of commercial contexts. For example, a search term may appear in finished products, formulations, blended foods, or secondary product descriptions.

This means the resulting signal should be interpreted as a regulatory and market-facing pattern, not as proof of causality for a single ingredient source.

## 2. Recall Frequency Does Not Equal Root Cause

A higher number of recalls does not automatically imply that a specific raw material, supplier, or process is inherently unsafe. Public recall data should be interpreted carefully and combined with internal technical evidence.

## 3. Severity Weighting Is a Deliberate Simplification

The weighted Risk Index is useful for monitoring and comparison, but it is still a simplified representation of severity. It does not capture every technical nuance of food safety risk.

## 4. Statistical Alerts Are Relative to Historical Baseline

The P95 threshold identifies unusually high periods relative to the observed historical distribution in the selected query window. It should not be interpreted as a universal regulatory cutoff.

## 5. LLM Narratives Depend on Upstream Structure

The quality of the LLM-generated explanation depends directly on the correctness and completeness of the structured summary provided to it. A grounded LLM can improve interpretation, but it does not replace the analytical integrity of the upstream workflow.

## 6. Decision Support, Not Final Judgment

Centinela is intended to support technical review, prioritization, and communication. Final decisions should still rely on domain expertise, internal data, supplier evidence, and applicable regulatory frameworks.
