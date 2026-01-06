# CONCLUSIONS — TOY01–TOY10 (RESULTS-ALIGNED)

This document summarizes conclusions supported directly by the numerical outputs of
Toy01–Toy10. All statements are constrained to demonstrated behavior in the recorded
results. Interpretive scope is explicitly limited.

---

## STATISTICAL FOUNDATIONS

- **Null ensemble baseline established**  
  _toy01_null_ensemble.py_  

  Random ensembles of normalized complex vectors produce stable baseline distributions
  for ⟨C⟩, σ(C), ΣC, and C_max across 500 trials.  
  These statistics serve as the reference distribution for all subsequent toys.

- **Dimensional scaling verified**  
  _toy02_dimensionality_sweep.py_  

  Mean pairwise overlap satisfies ⟨C⟩ ≈ 1 / dim across dim = 1 → 64, consistent with
  Haar-random expectations.

**Conclusion:**  
Pairwise overlap C_ij has a well-defined statistical meaning grounded in random
high-dimensional geometry.

---

## INVARIANCE AND CONSISTENCY

- **Permutation and unitary invariance**  
  _toy03_invariance_audit.py_  

  Coupling statistics are invariant under relabeling and global unitary transformations
  up to numerical precision.

**Conclusion:**  
The coupling structure contains no coordinate, basis, or labeling artifacts.

---

## STRUCTURE VS DYNAMICS

- **Static couplings do not synchronize dynamics**  
  _toy04_frequency_sync.py_  

  Kuramoto-style oscillators weighted by fixed C_ij do not exhibit sustained
  synchronization.

- **Adaptive feedback enables coherence**  
  _toy04_v2_feedback_sync.py_  

  When couplings evolve in response to phase alignment while relaxing toward the NCFT
  baseline, robust synchronization emerges with bounded couplings.

**Conclusion:**  
Pairwise structure alone is insufficient to generate collective dynamics.  
Coherence requires feedback between structure and dynamics.

---

## STABILITY AND FLOW PROPERTIES

- **Lyapunov-like behavior confirmed**  
  _toy05_conservation_or_lyapunov.py_  

  The defined energy functional E = −F is monotone non-increasing under projected
  gradient flow, with norm preserved to machine precision.

**Conclusion:**  
Stable, well-behaved flows exist on the manifold of normalized state ensembles.

---

## LIMITS OF PAIRWISE REPULSION

- **Competitive exclusion leads to clustering**  
  _toy06_competitive_exclusion.py_  

  Repulsive dynamics increase spectral gaps but drive C_max → 1, producing clustered
  states.

- **Entropy-based repulsion does not prevent collapse**  
  _toy06_v2_entropy_repulsion.py_  

  Even with stronger overlap penalties, clustering persists and diversity is not
  maintained.

**Conclusion:**  
Pairwise repulsion alone cannot enforce uniform diversity.  
Clustering is a generic geometric attractor, indicating the need for higher-order or
ensemble-level constraints.

---

## TOPOLOGY AND MEDIATION

- **Indirect coupling depends on graph structure**  
  _toy07_graph_mediation.py_  

  The ratio of indirect to direct coupling varies systematically across ring,
  Erdős–Rényi, and preferential-attachment graphs.

**Conclusion:**  
Network topology mediates interaction structure even when underlying states are random.

---

## NOISE AND ROBUSTNESS

- **Single-run noise effects are misleading**  
  _toy08_noise_phase_diagram.py_  

  Apparent non-monotonic noise effects appear in individual runs.

- **Ensemble averaging resolves noise dependence**  
  _toy08_v2_noise_ensemble.py_  

  Across multiple seeds, synchronization strength is largely flat within uncertainty.

**Conclusion:**  
Noise sensitivity in this regime is weak; ensemble statistics are required for reliable
inference.

---

## IDENTIFIABILITY LIMITS

- **States are not reconstructible from C alone**  
  _toy09_identifiability.py_  

  Gradient-based reconstruction of ψ from C_ij fails to converge.

- **Adding purity does not resolve identifiability**  
  _toy09_v2_identifiability.py_  

  Even with global purity constraints, reconstruction remains non-unique and unstable.

**Conclusion:**  
Pairwise overlaps do not uniquely identify underlying states.  
This is a fundamental informational limitation, not a numerical artifact.

---

## PAIRWISE–GLOBAL BRIDGE

- **Exact purity identity verified**  
  _toy10_density_bridge.py_  

  The identity  
  Tr(ρ²) = (N + 2 Σ C_ij) / N²  
  holds exactly for all tested configurations.

- **Dynamic density behavior unified**  
  _toy10_v2_density_bridge_dynamic.py_  

  - Static mode: observables remain constant  
  - Cohere mode: purity → 1, entropy → 0 (rank-1 collapse)  
  - Repel mode: purity increases and entropy decreases due to clustering  
  - Identity holds exactly in all cases

**Conclusion:**  
Pairwise overlaps fully determine ensemble purity, and density-matrix observables provide
a unifying explanation for behaviors seen in repulsive and coherent dynamics.

---

## OVERALL CONCLUSION

The Toy01–Toy10 suite establishes that:

- Pairwise overlaps are statistically well-defined and invariant
- Structure and dynamics are distinct but can interact via feedback
- Stable flows exist under projection and normalization
- Pairwise-only dynamics are geometrically limited
- Overlaps are insufficient for state reconstruction
- Pairwise structure maps exactly to global density observables

These conclusions are fully supported by explicit numerical experiments and recorded
CSV outputs.

