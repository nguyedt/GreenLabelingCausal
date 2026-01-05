# Causal Analysis of Green Delivery Slot Labeling

This repository contains an applied causal research memo analyzing the impact of a real-time “Less CO₂” labeling mechanism on customer choice behavior and delivery efficiency for an online grocery platform in Singapore.

## Project Overview

Online delivery platforms increasingly use sustainability labels to encourage customers to select delivery options that allow orders to be batched or clustered. While such design choices are intuitive, their causal effects on user behavior and downstream logistics efficiency are rarely evaluated using real operational data.

This project addresses two related causal questions using observational order-level data:

1. **Behavioral response:**  
   Does increased exposure to green-labeled delivery slots causally increase the probability that customers select a green slot?

2. **Operational impact:**  
   Does higher green-slot uptake translate into improved delivery clustering efficiency at the district level?

## Data and Constraints

- ~150,000 orders from an online grocery platform in Singapore  
- Sampling window: 15 delivery days  
- Partial observability: the platform records the *number* of green-labeled slots available at order time, but not slot-level labeling status  
- No randomized experiment or rollout information available

These constraints require a careful identification strategy based on within-district variation and aggregation.

## Methodology

- **Order-level analysis (RQ1):**
  - Logistic regression with district fixed effects
  - Treatment defined as the proportion of available delivery slots labeled “Less CO₂” at order time
  - Identification relies on short-run variation in exposure conditional on district and slot characteristics

- **District-level analysis (RQ2):**
  - District-by-date panel models by delivery type (express, 2-hour, 6-hour)
  - Outcome: average number of orders per delivery window (clustering efficiency)
  - Controls for total order volume and district fixed effects
  - Aggregation mitigates individual-level interference and captures system-level effects

## Key Findings

- Increasing the share of green-labeled slots substantially raises the probability that customers choose green delivery options.
- Higher green-slot uptake causally improves delivery clustering efficiency, particularly for wider delivery windows that allow greater routing flexibility.
- Results are robust to alternative specifications and diagnostic checks, including aggregation choices and temporal patterns.

## Files

- **`causal_memo.pdf`**  
  Full research memo detailing the causal framework, estimation strategy, results, diagnostics, and limitations.

## Notes

This repository is intended as a research portfolio artifact. Code and raw data are omitted due to confidentiality constraints.

---

**Contact:**  
Dung Nguyen  
(LinkedIn / email available upon request)
