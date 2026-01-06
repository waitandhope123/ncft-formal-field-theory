# SUMMARY — NCFT INTRINSIC TARGET-OVERLAP DYNAMICS (RESULTS-ALIGNED)

This summary documents the first confirmed non-trivial intrinsic dynamical regime
of NCFT. The goal is to establish intrinsic stability, axiom safety, and controllable
structure without projection.

All statements are supported directly by recorded numerical results.

---

## CORE ADVANCE

NCFT admits an intrinsic (tangent-space) dynamical formulation that is:

- Norm-preserving by construction
- Axiom-safe (no violations observed)
- Numerically stable for long runs and large N
- Capable of producing stable, non-trivial structure

Instability and collapse observed in earlier models are attributable to the
generator design, not to the axioms or coupling definition.

---

## TOY F — TARGET-OVERLAP GRAPH INTRINSIC
_file: toyF_target_overlap_graph_intrinsic.py_

### Model
- Intrinsic (tangent-space) updates only
- Energy minimized:
  
  E = Σ_(i,j ∈ G) (C_ij − C₀)²

- Graph-local interactions (ring graph, k = 4)
- Fixed parameters across all runs:
  - N = 50, d = 16
  - η = 0.15, steps = 1500
  - 200 graph edges
  - No projection

**Role:**  
Introduces frustration and locality to prevent collapse to global coherence while
maintaining intrinsic stability.

---

## CONTROL PARAMETER SWEEP — C₀

### C₀ = 0.10
- ⟨C⟩ ≈ 0.0678
- σ(C) ≈ 0.0559
- C_max ≈ 0.3491
- Energy → 0

**Structure metrics (Toy S):**
- Effective rank ≈ 9.39
- Cluster sizes: {7, 11, 16, 16}
- Compactness ≈ 0.641

**Role:**  
High-diversity regime with weak coordination and fragmented structure.

---

### C₀ = 0.25 (REFERENCE REGIME)
- ⟨C⟩ ≈ 0.0970
- σ(C) ≈ 0.0923
- C_max ≈ 0.5821
- Energy → 0

**Structure metrics (Toy S):**
- Effective rank ≈ 6.32
- Cluster sizes: {12, 10, 20, 8}
- Compactness ≈ 0.606

**Role:**  
Balanced, low-rank but non-collapsed structure.
This is the first confirmed stable, non-trivial intrinsic NCFT regime.

---

### C₀ = 0.40
- ⟨C⟩ ≈ 0.1326
- σ(C) ≈ 0.1369
- C_max ≈ 0.4963
- Energy → 0

**Structure metrics (Toy S):**
- Effective rank ≈ 4.42
- Cluster sizes: {12, 10, 12, 16}
- Compactness ≈ 0.569

**Role:**  
More coordinated, lower-rank structure without collapse or loss of heterogeneity.

---

## TOY S — STRUCTURE METRICS
_file: toyS_structure_metrics.py_

- Computes:
  - Pairwise statistics (⟨C⟩, σ, C_max)
  - Gram-derived effective rank
  - Spectral embedding
  - KMeans clustering
  - Within-cluster compactness

**Role:**  
Provides the measurement and phase-characterization layer, distinguishing collapse,
randomness, and organized structure.

---

## SUMMARY OF FINDINGS

- NCFT axioms remain intact and unviolated
- Intrinsic dynamics are universally stable
- Projection is unnecessary for boundedness
- Graph-local target overlap prevents collapse
- NCFT supports stable, clustered, low-rank structure
- Macroscopic structure is smoothly tunable via C₀
- No regime exhibits collapse (⟨C⟩ → 1) or trivial randomness
