# Paired Bootstrap Test for Classifier Comparison

**Course Assignment — Natural Language Processing (Bonus)**  
**Author:** Eleftheria Trimpou  
**Supervisor:** Ioannis Refanidis  
**University of Macedonia, 2024–2025**

---

## Overview

Implementation of the Paired Bootstrap Test in Python for statistically 
comparing two classifiers (A and B) across different sample sizes.  
True accuracies: AccA = 0.85, AccB = 0.70 (true difference = 0.15).

---

## Hypotheses Tested

Three alternative hypotheses at significance level α = 0.01:

| Hypothesis | Δ |
|-----------|---|
| H1: AccA > AccB | 0.00 |
| H1: AccA > AccB + 0.05 | 0.05 |
| H1: AccA > AccB + 0.10 | 0.10 |

---

## Methodology

- **Bootstrap replications:** 10⁶ per sample size
- **Sample sizes:** N = 100, 1000, 10000
- **Confidence intervals:** 99% (percentile method)
- **Comparison:** Results validated against `scipy.stats.bootstrap` (BCa method)

---

## Key Results

| N | Δ=0.00 | Δ=0.05 | Δ=0.10 |
|-------|--------|--------|--------|
| 100 | ❌ Fail | ❌ Fail | ❌ Fail |
| 1000 | ✅ Reject H0 | ✅ Reject H0 | ✅ Reject H0 |
| 10000 | ✅ Reject H0 | ✅ Reject H0 | ✅ Reject H0 |

**Key finding:** Statistical power increases with sample size. For N=100, 
the test fails to detect the true difference due to high sampling variance. 
For N≥1000, all hypotheses are confirmed with p≈0.

---

## Technologies

`Python` `NumPy` `Pandas` `Matplotlib` `Seaborn` `SciPy` `Kaggle`

---

## Repository Structure

```
├── hw4bonustrimpoueleftheria.ipynb   # Full implementation
└── report/
    └── hw4bonustrimpoueleftheria_report.pdf
```
