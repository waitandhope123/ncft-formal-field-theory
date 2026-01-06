# SUMMARY — TOY01–TOY10 (RESULTS-ALIGNED)

This summary provides a concise overview of the Toy01–Toy10 suite.
Each toy isolates a specific statistical, geometric, or dynamical property of
ensembles of normalized complex state vectors with pairwise overlaps

    C_ij = |⟨ψ_i | ψ_j⟩|²

All statements below reflect direct observations from the recorded numerical
results and CSV outputs.

---

## TOY01 — NULL ENSEMBLE BASELINE
_file: toy01_null_ensemble.py_

- Samples random ensembles of normalized complex vectors
- Establishes baseline distributions for:
  - mean overlap ⟨C⟩
  - standard deviation σ(C)
  - total coupling ΣC_ij
  - maximum overlap C_max
- Results match Haar-random expectations across 500 trials

**Role:**  
Defines the statistical reference distribution used by all subsequent toys.

---

## TOY02 — DIMENSIONALITY SCALING
_file: toy02_dimensionality_sweep.py_

- Measures ⟨C⟩ across increasing Hilbert space dimension
- Observed scaling: ⟨C⟩ ≈ 1 / dim

**Role:**  
Confirms the geometric meaning of overlap magnitude in high-dimensional spaces.

---

## TOY03 — INVARIANCE AUDIT
_file: toy03_invariance_audit.py_

- Applies permutations and global unitary transformations
- Measures induced changes in coupling structure
- All differences are zero up to numerical precision

**Role:**  
Verifies that the overlap structure is invariant and coordinate-free.

---

## TOY04 — STATIC FREQUENCY SYNCHRONIZATION
_file: toy04_frequency_sync.py_

- Runs Kuramoto-style oscillators with fixed pairwise couplings
- No sustained synchronization observed

**Role:**  
Demonstrates that static pairwise structure alone does not induce collective
dynamics.

---

## TOY04 v2 — FEEDBACK SYNCHRONIZATION
_file: toy04_v2_feedback_sync.py_

- Allows couplings to adapt based on phase alignment
- Includes relaxation toward baseline NCFT structure
- Robust synchronization emerges with bounded coupling evolution

**Role:**  
Shows that coherence arises when structure and dynamics are coupled via feedback.

---

## TOY05 — LYAPUNOV / ENERGY TEST
_file: toy05_conservation_or_lyapunov.py_

- Defines a coherence functional and projected gradient flow
- Energy E = −F is non-increasing
- Norm preserved to machine precision

**Role:**  
Establishes the existence of stable, well-behaved flows on the normalized state
manifold.

---

## TOY06 — COMPETITIVE EXCLUSION
_file: toy06_competitive_exclusion.py_

- Introduces repulsive dynamics between similar states
- System evolves toward clustered configurations
- Maximum overlap approaches 1

**Role:**  
Reveals clustering as a natural outcome of pairwise repulsion.

---

## TOY06 v2 — ENTROPY REPULSION
_file: toy06_v2_entropy_repulsion.py_

- Penalizes large overlaps more strongly via squared terms
- Clustering persists despite stronger repulsion

**Role:**  
Demonstrates a geometric limitation of pairwise-only diversity enforcement.

---

## TOY07 — GRAPH MEDIATION
_file: toy07_graph_mediation.py_

- Embeds states on different graph topologies
- Measures indirect vs direct coupling strength
- Results vary systematically by graph type

**Role:**  
Shows that network topology mediates interaction structure independently of state
geometry.

---

## TOY08 — NOISE PHASE DIAGRAM
_file: toy08_noise_phase_diagram.py_

- Sweeps noise levels in synchronization dynamics
- Single-run results show apparent non-monotonic behavior

**Role:**  
Illustrates the limitations of single-run noise analysis.

---

## TOY08 v2 — NOISE ENSEMBLE
_file: toy08_v2_noise_ensemble.py_

- Repeats noise sweeps across multiple random seeds
- Average synchronization remains largely flat within uncertainty

**Role:**  
Demonstrates the necessity of ensemble averaging for robust noise conclusions.

---

## TOY09 — IDENTIFIABILITY
_file: toy09_identifiability.py_

- Attempts to reconstruct underlying states ψ from C_ij alone
- Optimization fails to converge

**Role:**  
Shows that pairwise overlaps are insufficient for state reconstruction.

---

## TOY09 v2 — IDENTIFIABILITY WITH PURITY
_file: toy09_v2_identifiability.py_

- Adds global purity as an auxiliary constraint
- Reconstruction remains non-unique and unstable

**Role:**  
Confirms a fundamental identifiability limitation, not a numerical issue.

---

## TOY10 — DENSITY BRIDGE
_file: toy10_density_bridge.py_

- Constructs ensemble density matrix ρ
- Verifies exact identity:
  Tr(ρ²) = (N + 2 Σ C_ij) / N²

**Role:**  
Establishes an exact bridge between pairwise overlaps and global purity.

---

## TOY10 v2 — DYNAMIC DENSITY BRIDGE
_file: toy10_v2_density_bridge_dynamic.py_

- Tracks purity and entropy under:
  - static
  - coherence-enhancing
  - repulsive dynamics
- Identity holds exactly in all modes

**Role:**  
Unifies observations from Toy04 and Toy06 within a density-matrix framework.

---

## SUMMARY OF THE SUITE

Toy01–Toy10 collectively demonstrate:

- Statistical grounding of pairwise overlaps
- Exact invariance under relabeling and unitaries
- Clear separation between structure and dynamics
- Stable projected flows
- Geometric limits of pairwise repulsion
- Fundamental non-identifiability from overlaps alone
- An exact mapping between pairwise and global observables

All statements above are directly supported by numerical results and CSV outputs.
