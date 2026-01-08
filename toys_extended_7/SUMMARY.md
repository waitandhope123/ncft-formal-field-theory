# NCFT TOY SUITE — CONSOLIDATED SUMMARY (Toys 1–10)

This block documents the *actual computational evidence* behind NCFT.
Each toy is listed with: filename, purpose (what it probes), why it matters,
and the concrete result it established.

---

## Toy 1 — Phase / Scale Atlas

**Filename:**  
`toy_phase_scale_atlas.py`

**What it does:**  
Sweeps N (system size), d (state dimension), eta (learning rate),
and projection on/off to map stability, boundedness, and phase structure.

**Why it matters:**  
Establishes whether NCFT dynamics are well-posed or numerically fragile,
and whether projection is structurally necessary.

**Key results:**
- Projected dynamics are stable across wide N, d, eta ranges.
- Unprojected dynamics frequently overflow or diverge.
- Confirms existence of coherent, critical, and decoherent regimes.
- Projection is necessary for bounded bilinear coupling.

---

## Toy 2 — Topology & Kernel Stress Test

**Filename:**  
`toy_topology_kernel_stress.py`

**What it does:**  
Runs NCFT on different interaction graphs:
complete, Erdős–Rényi, ring, small-world,
across sizes and dimensions.

**Why it matters:**  
Tests whether NCFT behavior is an artifact of full connectivity
or survives realistic sparse / structured interactions.

**Key results:**
- NCFT signatures persist across graph topologies.
- Quantitative behavior shifts, but qualitative structure remains.
- Confirms topology-independence of core axioms.

---

## Toy 3 — Noise & Open-System Robustness

**Filename:**  
`toy_noise_open_system_robustness.py`

**What it does:**  
Injects:
- additive noise
- dropout (field removal)
- return (field reinsertion)
- external drive  
under many parameter combinations.

**Why it matters:**  
Tests whether NCFT survives realistic perturbations
or collapses outside closed, noiseless systems.

**Key results:**
- Projected NCFT remains stable under moderate noise.
- Decoherence increases smoothly, not catastrophically.
- Identifies clear noise thresholds beyond which coherence fails.
- Confirms NCFT as a robust open-system theory.

---

## Toy 4 — Inverse Identifiability Limits

**Filename:**  
`toy_inverse_identifiability.py`

**What it does:**  
Attempts to reconstruct underlying structure
from partial, noisy observations of C.

**Why it matters:**  
Establishes epistemic limits:
what *cannot* be inferred even if NCFT is correct.

**Key results:**
- Full reconstruction impossible under partial observability.
- Distinguishable clustered vs null structure at sufficient signal.
- Defines hard identifiability boundaries.
- Prevents overclaiming of inference power.

---

## Toy 6 — Energy Landscape & Basin Geometry

**Filename:**  
`toy_energy_landscape_transitions.py`  
(plus basin and run CSVs)

**What it does:**  
Maps NCFT energy landscape:
- basins
- transitions
- convergence behavior  
across many initial conditions.

**Why it matters:**  
Determines whether NCFT has:
- unique attractors
- metastable states
- glassy behavior.

**Key results:**
- NCFT exhibits a dominant attractor basin.
- No evidence of chaotic wandering.
- Energy descent is Lyapunov-like.
- Confirms deterministic basin structure.

---

## Toy 7 — Coarse-Graining & Renormalization

**Filename:**  
`toy_renormalization_coarse_grain.py`

**What it does:**  
Compares:
- aggregated micro dynamics
- independently evolved macro dynamics  
under coarse-graining.

**Why it matters:**  
Tests whether NCFT is closed under scale changes
(renormalization behavior).

**Key results:**
- Macro tracks aggregated micro approximately.
- Errors are bounded and non-growing.
- Exact invariance fails (expected).
- NCFT is a controlled, scale-dependent effective theory.

---

## Toy 8 — Statistical Detectability & Falsification

**Filename:**  
`toy8_statistical_detectability.py`

**What it does:**  
Constructs ROC curves, power curves, and detection thresholds
for NCFT vs null under noise and partial observability.

**Why it matters:**  
Turns NCFT into a statistically testable and falsifiable hypothesis.

**Key results:**
- NCFT signatures are detectable above noise thresholds.
- Explicit regimes where detection is impossible are identified.
- Defines required event counts for target power.
- Prevents unfalsifiable claims.

---

## Toy 9 — Signature Mining & Model Discrimination

**Filename:**  
`toy9_signature_miner_model_discriminator.py`

**What it does:**  
Compares NCFT against competing dynamical models
and automatically discovers which observables best distinguish them.

**Why it matters:**  
Identifies *what is essential* to NCFT versus incidental.

**Key results:**
- NCFT uniquely identified by:
  - purity identity preservation
  - higher-order C-structure (tails, kurtosis)
  - constrained spectral geometry
- Mean energy or simple coherence is insufficient.
- Confirms NCFT is not reducible to Kuramoto or Hebbian dynamics.

---

## Toy 10 — Universality & Basin-of-Attraction Atlas

**Filename:**  
`toy10_universality_basin_atlas.py`

**What it does:**  
Explores a *family of dynamical laws* near NCFT
to determine which flow into the same late-time signature region.

**Why it matters:**  
Determines whether NCFT is:
- a fine-tuned mechanism
- or a universality class.

**Key results:**
- NCFT has a finite basin in law-space.
- Certain deformations converge to NCFT behavior.
- Others remain distinct.
- NCFT is a restricted universality class:
  neither fragile nor generic.

---

## OVERALL OUTCOME

Together, these toys establish NCFT as:

- internally consistent
- robust to noise and openness
- epistemically honest
- scale-aware (effective, not invariant)
- statistically falsifiable
- uniquely identifiable
- structurally universal (within a defined class)

This suite goes far beyond single-result simulations:
it maps the *behavioral, epistemic, statistical, and structural space*
of the theory.

---

**END OF SUMMARY**
