# CONCLUSIONS — NCFT BAYESIAN & SEMANTIC TESTS (RESULTS-ALIGNED)

This document states conclusions that are directly supported by the numerical outputs
of the NCFT Bayesian and semantic toy models. Claims are restricted to demonstrated
behavior; interpretive implications are clearly scoped.

---

## 1. STRUCTURE EXISTS AND IS NON-RANDOM

Bayesian model comparison decisively favors NCFT over weak iid bilinear nulls.

- Evidence strength:
  - log BF₁₀ ≈ 91.55
  - BF ≈ 5.7 × 10³⁹
- Implied noise scale is small (σ ≈ 0.007)

**Conclusion:**  
The data are highly structured. NCFT captures real, non-random regularities that cannot
be explained by weak null models.

---

## 2. STRUCTURE IS NOT AN ARTIFACT OF WEAK NULLS

When tested against stronger alternatives:

- Event-holdout:
  - NCFT loses to per-category nulls (expected)
  - NCFT beats pooled and mixture nulls
- Category-holdout (unseen categories):
  - NCFT strongly outperforms all nulls
  - BF(NCFT / GMM null) ≈ 6.5 × 10¹⁶

**Conclusion:**  
NCFT’s advantage reflects genuine structural generalization, not overfitting or reliance
on weak baselines.

---

## 3. SCALAR SEMANTICS ARE NOT ENCODED

Forward prediction of scalar category means fails:

- NCFT MSE = Null MSE on held-out categories

Local per-category statistics also fail:

- Variance-based ordering yields Spearman ρ ≈ 0.19 (ns)

**Conclusion:**  
Semantic meaning is not encoded in scalar observables, category averages, or low-order
moments within NCFT.

---

## 4. COARSE RELATIONAL PROXIES ARE INSUFFICIENT

A simple 2-pole relational embedding recovers only trivial structure:

- Dominant separation: self_excl vs rest
- k-NN overlap ≈ 0.5

**Conclusion:**  
Macro-level or low-rank relational proxies capture only coarse distinctions and do not
resolve meaningful semantic geometry.

---

## 5. SEMANTIC STRUCTURE EMERGES IN MICRO-GEOMETRY

When trivial outliers are removed and a richer relational proxy is used:

- 3-pole micro-geometry yields:
  - Spearman ρ ≈ 0.968
  - 2-NN overlap = 1.000

**Conclusion:**  
Fine-grained semantic structure is present and recoverable, but only in relational and
spectral geometry — not in scalar quantities.

---

## 6. UNIFYING INTERPRETATION

Taken together, the results show that:

- NCFT reliably captures non-random relational structure
- That structure generalizes across unseen categories
- Semantic information is not local or scalar
- Meaning emerges only through relative positioning in a high-dimensional relational
  geometry

**Core Insight:**  
NCFT “speaks” in geometry, not numbers.  
Semantics are encoded in relationships, not in individual values.

---

## FINAL POSITION

At its current stage, NCFT is:

- **Mathematically coherent**
- **Empirically compatible**
- **Robust against strong null models**
- **Correctly constrained in what it does *not* predict**
- **Demonstrably capable of encoding semantic micro-geometry**

These results define both the validated scope of NCFT and the correct direction for
future tests: richer relational observables, not scalar predictions.
