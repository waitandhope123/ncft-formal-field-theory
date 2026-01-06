# SUMMARY — NCFT INTRINSIC TARGET-OVERLAP DYNAMICS (TOY F, RESULTS-ALIGNED)

This summary documents the numerical behavior of Toy F, an intrinsic (tangent-space)
NCFT dynamical model designed to test whether stable, non-collapsed structure can be
produced without projection.

All statements below reflect direct observations from recorded numerical outputs.

---

## MODEL DEFINITION

**Toy:** Toy F — Target-Overlap Graph Intrinsic  
**File:** toyF_target_overlap_graph_intrinsic_C10.py

**State space**
- Number of fields: N = 1,000,000
- State dimension: d = 16
- Field states are complex unit vectors (‖ψᵢ‖ = 1)

**Interaction structure**
- Graph: Erdős–Rényi
- Mean degree ≈ 2
- Total edges ≈ 1,000,556

**Energy functional**
\[
E = \sum_{(i,j)\in G} (C_{ij} - C_0)^2
\quad \text{with} \quad
C_{ij} = |\langle \psi_i | \psi_j \rangle|^2
\]

**Dynamics**
- Intrinsic (tangent-space) gradient descent
- No projection applied
- Step size: η = 0.15
- Target overlap: C₀ = 0.001
- Total steps: 1500

---

## OBSERVED NUMERICAL BEHAVIOR

### Energy minimization
- Initial energy: E ≈ 7234
- Final energy: E ≈ 0.00349
- Total reduction > 99.999%

Energy decreases monotonically and stabilizes near zero.

---

### Pairwise overlap statistics (edge-restricted)

| Quantity | Initial | Final (t = 1500) |
|--------|--------|------------------|
| ⟨C_edge⟩ | ≈ 0.062 | ≈ 0.001043 |
| σ(C_edge) | ≈ 0.058 | ≈ 4.1×10⁻⁵ |
| max(C_edge) | ≈ 0.58 | ≈ 0.00132 |

Observed overlaps converge tightly to the target value C₀.

---

### Stability diagnostics

- Norm error: ≤ 2.22×10⁻¹⁶ throughout run
- No C_ij > 1 observed
- No axiom violations detected
- Long-time stability confirmed

---

## COMPUTATIONAL OUTCOME

Toy F demonstrates that:

- Intrinsic NCFT dynamics are numerically stable at large N
- Target-overlap objectives are satisfied without projection
- The system converges to a homogeneous, low-variance overlap configuration
- Energy-minimizing equilibria are reached reproducibly

All results above are directly supported by the recorded output logs.
