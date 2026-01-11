# NCFT Toy Model Suite — Summary and Results

This repository contains a sequence of executable **computational toy models** used to
stress-test, falsify, and delimit the scope of **NCFT-core** (Non-Local Consciousness Field Theory).

Each toy targets a specific structural assumption or potential failure mode.
All claims reported here are restricted strictly to behaviors that persist across
systematic parameter sweeps and adversarial constructions.

---

## Design Philosophy

The toy suite is **not** intended to demonstrate desired behavior.
Instead, it is explicitly constructed to answer the question:

> *“Under what minimal conditions does NCFT-core remain well-posed, bounded, and coherent?”*

Negative results are retained and reported as first-class outcomes.

---

## Toy Index and Results

### **Toy 021 — Projection Enforcement**
**File:** `toy_021_ncft_projection_enforcement.py`

**Purpose**  
Test whether NCFT dynamics remain bounded without exact state normalization.

**Tested Variants**
- Hard projection (normalize every step)
- Delayed projection
- Soft penalty normalization

**Result**
- Hard projection: stable, bounded, convergent
- All relaxed variants: numerical divergence (norm blow-up)

**Conclusion**
Projection is not optional. NCFT dynamics are ill-posed off the unit-norm manifold.

---

### **Toy 022 — Coherence Threshold Sweep**
**File:** `toy_022_ncft_coherence_threshold.py`

**Purpose**  
Determine whether frequency coherence affects NCFT dynamics when frequencies are static.

**Test**
- Sweep of σ/ω from 0.0 to 0.5

**Result**
- Full alignment and saturation in all cases
- No qualitative change across threshold

**Conclusion**
Frequency coherence does not dynamically influence ψ-alignment when ω is external.

---

### **Toy 023 — Frequency Mismatch Suppression**
**File:** `toy_023_ncft_frequency_mismatch_suppression.py`

**Purpose**  
Test whether suppressing coupling between frequency-mismatched agents alters outcomes.

**Mechanism**
- Weighted coupling:
  Cᵢⱼ → exp(−β(Δω/ω̄)²) · Cᵢⱼ

**Result**
- Saturation ratio = 1.0 for all β and σ/ω
- Alignment always reached

**Conclusion**
Static frequency-dependent suppression slows convergence but does not change attractors.

---

### **Toy 024 — Frequency Backreaction**
**File:** `toy_024_ncft_frequency_backreaction.py`

**Purpose**  
Make frequency coherence dynamical by allowing ω to evolve via coupling backreaction.

**Observations**
- ω statistics change (σ increases or remains incoherent)
- ψ states still globally align
- Saturation remains maximal

**Conclusion**
Frequency coherence becomes a **diagnostic**, not a stabilizing or destabilizing mechanism.

---

### **Toy 025 — Cluster Fragmentation**
**File:** `toy_025_ncft_cluster_fragmentation.py`

**Purpose**  
Test whether incoherence produces persistent sub-clusters instead of global alignment.

**Method**
- Graph clustering on Cᵢⱼ threshold
- Measure cluster count, size, modularity

**Result**
- Single cluster in all regimes
- No fragmentation observed
- Full saturation maintained

**Conclusion**
NCFT-core has a single global attractor; incoherence does not generate structure.

---

### **Toy 026 — Projection Softening / Manifold Escape**
**File:** `toy_026_ncft_projection_softening.py`

**Purpose**  
Test whether NCFT admits a continuous extension off the projective manifold.

**Variants**
- Partial projection
- Delayed projection
- Stochastic projection

**Result**
- All softened variants diverge rapidly
- Only hard projection remains well-posed

**Conclusion**
NCFT-core exists *only* as a projected flow.
There is no soft continuation.

---

## Summary Table

| Toy | Pressure Point | Outcome |
|----|---------------|--------|
| 021 | Projection necessity | Required |
| 022 | Coherence threshold | Non-dynamical |
| 023 | Frequency suppression | Ineffective |
| 024 | Frequency backreaction | Diagnostic only |
| 025 | Cluster formation | Absent |
| 026 | Projection relaxation | Ill-posed |

---

## Overall Finding

Across all tested regimes, **NCFT-core**:
- Is bounded and deterministic
- Has a single global attractor
- Exhibits no criticality or emergent structure
- Requires strict projection enforcement
- Does not support clustering or phase transitions

These results fully characterize the NCFT-core universality class.
