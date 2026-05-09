# LLM Evaluation

## Role of the LLM in Centinela

In Centinela, the LLM is used as an interpretation layer rather than as the primary analytical engine.

This distinction is important. The system does not ask the model to infer risk directly from unstructured raw recall records. Instead, the analytical workflow first calculates a structured summary based on deterministic rules and statistical logic. The LLM then converts that summary into a technical narrative for decision support.

## Why This Matters

A common weakness in LLM-based analytical tools is the tendency to rely too heavily on free-form generation. In regulatory and food safety contexts, this creates obvious risks:

- hallucinated conclusions
- confusion between event counts and alert counts
- unsupported causal claims
- inconsistent explanations across runs

Centinela addresses this by constraining the LLM with structured inputs and explicit logic rules.

## Grounding Strategy

The LLM layer is grounded through:

- structured upstream calculations
- explicit severity metrics
- probability proxy indicators
- controlled summary fields
- consistency instructions embedded in the generation logic

This makes the model operate more as a narrative translator than as a standalone reasoner.

## Example of Consistency Control

One critical rule in the project is that **alert count refers to the number of months in which the 3-month moving average exceeds the P95 threshold**, not to the number of raw recall events.

This distinction is essential for preserving analytical accuracy in the narrative layer.

## Evaluation Perspective

From a portfolio perspective, the LLM component demonstrates:

- controlled use of generative AI
- grounding through structured analytics
- risk-aware prompt design
- alignment between quantitative outputs and narrative explanation

The project therefore showcases not only LLM usage, but also **LLM governance within an analytical workflow**.

## Practical Conclusion

The LLM adds value when it is placed at the correct point in the pipeline: after the core calculations have already defined the signal.

In Centinela, the model improves communication and interpretability, but the credibility of the output depends on the analytical structure that comes before it.
