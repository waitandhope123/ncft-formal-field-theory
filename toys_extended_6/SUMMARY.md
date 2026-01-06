# NCFT — Discriminative Toy Summary

This document summarizes the executable discriminative toys included in the NCFT
repository, their intended purpose, and the observed numerical outcomes.

---

## ncft_discriminative_validation_toy.py

**Purpose:**  
Test whether NCFT-constrained dynamics produce relational structure distinguishable
from a generic normalized bilinear null model.

**Comparison:**  
- NCFT-constrained system  
- Generic bilinear null system  

**Metrics Evaluated:**  
- Rank stability  
- Top-k partner stability  
- Interaction entropy  

**Observed Results:**  
- Rank stability: identical for NCFT and null  
- Top-k partner stability: comparable (null slightly higher)  
- Mean interaction entropy: comparable (NCFT slightly higher)  

**Outcome:**  
No discriminative structural advantage observed for NCFT under symmetric dynamics.

---

## ncft_constraint_violation_stress_toy.py

**Purpose:**  
Test whether NCFT axioms exclude unstable or ill-posed dynamics permitted by
unconstrained bilinear systems.

**Stressors Applied:**  
- Non-normalized updates  
- Noise injection  
- Frequency dispersion  
- Illegal triadic interactions  

**Observed Results:**  

NCFT system:
- Max norm ≈ 1.0  
- Max coupling ≤ 1.0  
- No numerical overflow  
- No NaNs  

Null system:
- Norm divergence → ∞  
- Coupling overflow → ∞  
- Numerical instability detected  

**Outcome:**  
NCFT-enforced dynamics remain bounded under adversarial stress, while the null
system becomes ill-posed.

---
