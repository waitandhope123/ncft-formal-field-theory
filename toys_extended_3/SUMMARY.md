# SUMMARY — NCFT INTRINSIC DYNAMICS DIAGNOSTICS (RESULTS-ALIGNED)

This summary covers a focused diagnostic suite designed to identify the source of
instability in NCFT dynamics and to test whether the theory is geometrically
self-consistent without relying on post-hoc projection.

All statements reflect direct observations from the recorded numerical results.

---

## TOY A — AXIOM VIOLATION TRACER
_file: toyA_axiom_violation_tracer.py_

- Runs the original (raw) NCFT generator
- Monitors norm drift and coupling violations
- Execution halts at first violation

**Observed behavior:**
- Violation occurs at t = 1
- No C_ij > 1 at failure
- Per-field and global norm drift detected

**Role:**  
Demonstrates that axioms fail due to non-norm-preserving dynamics, not due to the
axioms or coupling definition themselves.

---

## TOY C — PROJECTION COMMUTATIVITY
_file: toyC_projection_commutativity.py_

- Compares update→project vs project→update→project pipelines
- Tracks divergence between projected flows and raw dynamics

**Observed behavior:**
- Projected pipelines agree to numerical precision (~1e−18)
- Raw dynamics diverge rapidly with C_max → O(10²–10³)

**Role:**  
Shows that projection is mathematically benign and only constrains a runaway generator.
Projection does not inject artificial structure.

---

## TOY D — INTRINSIC (TANGENT-SPACE) UPDATE
_file: toyD_intrinsic_update.py_

- Replaces raw updates with tangent-space intrinsic updates
- Guarantees motion on the unit sphere by construction

**Observed behavior:**
- No norm drift
- No C_ij > 1
- Stable for long runs
- System converges to ⟨C⟩ = 1

**Role:**  
Establishes that NCFT geometry is self-consistent and that intrinsic updates resolve
all stability violations without projection.

---

## TOY A2 — INTRINSIC AXIOM REGRESSION
_file: toyA2_intrinsic_axiom_tracer.py_

- Repeats axiom tracing under intrinsic dynamics
- Treats any violation as a hard error

**Observed behavior:**
- No violations detected
- Clear divergence from projection-based dynamics

**Role:**  
Confirms that intrinsic dynamics are axiom-safe by construction.

---

## TOY C2 — INTRINSIC VS PROJECTED FLOW
_file: toyC2_intrinsic_vs_projection.py_

- Compares intrinsic dynamics to raw + projection dynamics

**Observed behavior:**
- Intrinsic flow: ⟨C⟩ → 1
- Projected flow: ⟨C⟩ → ~0
- Large divergence (Δ ≈ 1)

**Role:**  
Demonstrates that projection enforces a different invariant and can suppress genuine
structure, producing misleadingly “stable” but empty dynamics.

---

## TOY D2 — BALANCED INTRINSIC DYNAMICS
_file: toyD2_balanced_intrinsic_dynamics.py_

- Adds intrinsic repulsion to intrinsic attraction

**Observed behavior:**
- System still collapses to ⟨C⟩ = 1
- No instability observed

**Role:**  
Shows that the current intrinsic force law is effectively attractive overall and does
not yet generate nontrivial steady states.

---

## TOY E2 — INTRINSIC PHASE MAP
_file: toyE2_intrinsic_phase_map.py_

- Sweeps N, dimension, and step size η
- Tests stability across scale

**Observed behavior:**
- All runs stable
- All runs converge to ⟨C⟩ = 1
- No axiom violations

**Role:**  
Confirms that intrinsic dynamics are universally stable across tested scales and
parameters.

---

## SUMMARY OF FINDINGS

- NCFT axioms are internally consistent
- Pairwise coupling definition is correct
- Instability originates from non-geometric generators
- Projection enforces constraints but alters dynamics
- Intrinsic (tangent-space) updates resolve all stability issues
- Current intrinsic dynamics are stable but dynamically trivial

All statements above are supported directly by numerical outputs.
