# NCFT Toy Models

This repository contains a suite of toy models designed to explore, validate, and stress-test
formal properties of NCFT-style systems defined by ensembles of normalized complex state vectors
and their pairwise overlaps:

C_ij = |⟨ψ_i | ψ_j⟩|²


Each toy isolates a specific structural, statistical, or dynamical question.  
All outputs are written to CSV files in the `outputs/` directory for downstream analysis.

The toys are intentionally minimal and are **not** intended to model physical systems directly.
They serve as controlled experiments on the geometry and dynamics of normalized vector ensembles.

---

## `toy01_null_ensemble.py`

**Purpose:** Establish a null baseline for pairwise couplings.

**What it does:**
- Samples many ensembles of random, normalized complex vectors.
- Computes distributions of:
  - mean coupling ⟨C⟩
  - standard deviation σ(C)
  - total coupling ΣC_ij
  - maximum coupling C_max

**Key result:**
- Baseline statistics match Haar-random expectations.

**Interpretation:**  
Defines the reference distribution for “structureless” ensembles.  
All subsequent toys should be compared against this null baseline.

---

## `toy02_dimensionality_sweep.py`

**Purpose:** Verify scaling of overlaps with Hilbert space dimension.

**What it does:**
- Repeats the null ensemble experiment across multiple dimensions.
- Measures ⟨C⟩ as a function of dimension.

**Key result:**
- ⟨C⟩ ≈ 1 / dim.

**Interpretation:**  
Confirms the statistical meaning of C_ij for random normalized vectors.

---

## `toy03_invariance_audit.py`

**Purpose:** Test invariance properties of the coupling structure.

**What it does:**
- Applies permutations of labels and global unitary transformations.
- Measures changes in coupling statistics.

**Key result:**
- Differences are zero up to numerical precision.

**Interpretation:**  
The coupling structure is invariant under relabeling and global basis changes.  
There are no hidden coordinate artifacts.

---

## `toy04_frequency_sync.py`

**Purpose:** Test whether static NCFT couplings induce synchronization.

**What it does:**
- Runs Kuramoto-style phase oscillators weighted by fixed C_ij.

**Key result:**
- No sustained synchronization observed.

**Interpretation:**  
Static pairwise structure alone does not generate collective dynamics.

---

## `toy04_v2_feedback_sync.py`

**Purpose:** Test synchronization with adaptive, NCFT-anchored couplings.

**What it does:**
- Allows couplings C_ij(t) to evolve based on phase alignment.
- Includes relaxation toward baseline NCFT couplings.

**Key result:**
- Robust synchronization emerges while couplings remain bounded.

**Interpretation:**  
NCFT structure acts as a scaffold.  
Coherence emerges only when structural similarity feeds back into dynamics.

---

## `toy05_conservation_or_lyapunov.py`

**Purpose:** Test existence of Lyapunov-like behavior.

**What it does:**
- Defines a coherence functional F.
- Evolves states via projected gradient ascent.
- Tracks E = −F.

**Key result:**
- E is monotone non-increasing.
- Norm preservation holds to machine precision.

**Interpretation:**  
Well-defined, stable flows exist on the normalized state manifold.

---

## `toy06_competitive_exclusion.py`

**Purpose:** Explore repulsive / competitive dynamics.

**What it does:**
- Pushes states away from similarity.
- Tracks coupling statistics and spectral structure.

**Key result:**
- The system collapses into clusters with C_max → 1.

**Interpretation:**  
Pairwise repulsion alone does not maintain uniform diversity.  
Clustering is a natural geometric attractor.

---

## `toy06_v2_entropy_repulsion.py`

**Purpose:** Test stronger repulsion using squared-overlap penalties.

**What it does:**
- Minimizes J = Σ C_ij² via projected gradient descent.

**Key result:**
- Clustering still occurs.
- Large overlaps dominate despite stronger penalties.

**Interpretation:**  
This reveals a genuine geometric limitation:  
pairwise overlap penalties alone cannot enforce stable diversity.  
Higher-order or ensemble-level constraints are required.

---

## `toy07_graph_mediation.py`

**Purpose:** Study indirect coupling via network topology.

**What it does:**
- Embeds states on different graphs.
- Measures indirect vs direct coupling strength.

**Key result:**
- Indirect coupling depends on graph type.

**Interpretation:**  
Topology mediates interaction structure even when underlying states are random.

---

## `toy08_noise_phase_diagram.py`

**Purpose:** Study robustness of synchronization under noise.

**What it does:**
- Sweeps noise levels.
- Measures average synchronization.

**Key result:**
- Apparent non-monotonic effects observed in single runs.

**Interpretation:**  
Initial indication of noise sensitivity, requiring ensemble averaging.

---

## `toy08_v2_noise_ensemble.py`

**Purpose:** Resolve noise effects using multi-seed averaging.

**What it does:**
- Repeats Toy08 across many seeds per noise level.

**Key result:**
- Noise dependence is weak and largely flat within uncertainty.

**Interpretation:**  
The apparent resonance in v1 was sampling noise.  
Synchronization is not strongly noise-tuned in this regime.

---

## `toy09_identifiability.py`

**Purpose:** Test whether states can be reconstructed from C_ij.

**What it does:**
- Attempts gradient-based reconstruction of ψ from a target C matrix.

**Key result:**
- Optimization does not converge to zero loss.

**Interpretation:**  
Pairwise overlaps are insufficient to uniquely identify states.

---

## `toy09_v2_identifiability.py`

**Purpose:** Test identifiability with added global constraints.

**What it does:**
- Adds purity as an auxiliary observable.

**Key result:**
- Reconstruction still fails.

**Interpretation:**  
Even with purity, the inverse problem remains non-identifiable.  
This is a fundamental limitation, not a numerical issue.

---

## `toy10_density_bridge.py`

**Purpose:** Connect pairwise couplings to global density-matrix observables.

**What it does:**
- Constructs the ensemble density matrix ρ.
- Computes purity and entropy.
- Verifies:

Tr(ρ²) = (N + 2 Σ C_ij) / N²


**Key result:**
- Identity holds exactly.

**Interpretation:**  
Pairwise overlaps fully determine ensemble purity.

---

## `toy10_v2_density_bridge_dynamic.py`

**Purpose:** Track density-matrix observables under different flows.

**What it does:**
- Evolves ensembles under three modes:
  - `mode="none"`   : static control
  - `mode="cohere"` : coherence-maximizing flow
  - `mode="repel"`  : repulsive, structure-forming flow
- Tracks ⟨C⟩, purity, entropy, and identity error.

**Key results:**
- Static mode: observables remain constant.
- Cohere mode: purity → 1, entropy → 0 (rank-1 collapse).
- Repel mode: purity increases and entropy decreases due to clustering.
- The purity identity holds exactly in all cases.

**Interpretation:**  
Repulsive pairwise dynamics do not maximize entropy.  
Instead, they induce low-rank clustered structure.  
Toy10 v2 explains and unifies the behavior observed in Toy06.

---

## Summary

This toy suite demonstrates:

- Statistical grounding of pairwise overlaps
- Invariance and internal consistency
- Clear separation between structure and dynamics
- Geometric limits of repulsion-only dynamics
- Fundamental non-identifiability of states from overlaps
- An exact bridge between pairwise structure and global observables

All claims are supported by explicit numerical experiments and CSV outputs.
