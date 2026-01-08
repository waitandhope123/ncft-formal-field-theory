# NCFT EXTENDED TOY SUITE — SUMMARY (Toys 11–16)

## Toy 11 — Relaxation Spectrum and Spectral Gap

**Filename:**  
`toy11_relaxation_spectral_gap.py`

**What it does:**  
Computes the finite-difference Jacobian of the projected NCFT update map
around a late-time coherent state and analyzes the eigenvalue spectrum
of the one-step dynamics.

**Why it matters:**  
Spectral gaps and relaxation modes are fundamental physical diagnostics.
Their presence distinguishes structured collective dynamics from generic
gradient descent or unconstrained relaxation.

**Results:**  
The Jacobian spectrum exhibits clear band separation with a finite
spectral gap. A small number of slow collective modes are well separated
from a bulk of fast-relaxing modes. All eigenvalues lie strictly within
the unit circle, confirming linear stability of the coherent attractor.
This establishes characteristic timescales and nontrivial mode structure
in NCFT dynamics.

---

## Toy 12 — Fluctuation / Linear Response Probe

**Filename:**  
`toy12_fluctuation_response.py`

**What it does:**  
Applies a localized perturbation to a single field in a late-time
coherent NCFT state and tracks the decay of induced changes in the
pairwise coupling matrix over time.

**Why it matters:**  
Linear response behavior and perturbation damping are hallmarks of
physically meaningful attractors. Persistent or spreading responses
would indicate marginal stability or criticality.

**Results:**  
Perturbations decay rapidly to the numerical noise floor with no
evidence of long-lived tails or revival. The coherent NCFT attractor
is linearly stable and strongly damped, exhibiting clean, bounded
response behavior.

---

## Toy 13 — Noise-Driven Decoherence Scaling

**Filename:**  
`toy13_noise_temperature_scaling.py`

**What it does:**  
Injects controlled stochastic noise into NCFT dynamics and measures
steady-state purity and mean coupling as a function of noise amplitude.

**Why it matters:**  
Noise amplitude acts as an effective control parameter analogous to
temperature. The manner in which coherence degrades under noise
characterizes phase robustness and stability.

**Results:**  
Purity decreases smoothly and monotonically with increasing noise.
No abrupt transitions or numerical instabilities are observed within
the tested regime. Coherent NCFT dynamics are robust to moderate noise
and exhibit continuous decoherence behavior.

---

## Toy 14 — Mean-Field / Continuum Limit Approximation

**Filename:**  
`toy14_meanfield_continuum_limit.py`

**What it does:**  
Compares full micro-level NCFT dynamics at large N with an approximate
mean-field evolution of the empirical density matrix, tracking their
divergence over time.

**Why it matters:**  
The existence (or failure) of a controlled continuum approximation
determines whether NCFT can be interpreted as an effective field theory
rather than a purely discrete construction.

**Results:**  
Micro–macro deviation grows initially but rapidly saturates to a
bounded plateau. Errors do not accumulate over time. Mean-field
dynamics provide an approximate but controlled description, consistent
with effective (not exact) field-theoretic behavior.

---

## Toy 15 — Non-Equilibrium Drive–Dissipation Balance

**Filename:**  
`toy15_nonequilibrium_drive_dissipation.py`

**What it does:**  
Introduces continuous external driving and linear dissipation into
NCFT dynamics and tracks long-time energy behavior.

**Why it matters:**  
The ability to support non-equilibrium steady states is a defining
feature of physical dynamical systems beyond equilibrium.

**Results:**  
After a short transient, the system settles into a stable non-equilibrium
steady state with bounded energy. No runaway behavior or oscillatory
instability is observed, demonstrating that NCFT dynamics can balance
drive and dissipation while maintaining coherence.

---

## Toy 16 — Dimensionless Scaling and Universality Test

**Filename:**  
`toy16_dimensionless_groups_scaling_collapse.py`

**What it does:**  
Tests whether steady-state observables collapse under a candidate
dimensionless parameter g = η(N−1) across system sizes.

**Why it matters:**  
Scaling collapse would indicate simple universality. Failure to collapse
constrains the universality class and clarifies scale dependence.

**Results:**  
No single-parameter scaling collapse is observed. Curves remain ordered
by system size with parallel but distinct behavior. This demonstrates
that NCFT exhibits controlled but nontrivial scale dependence and does
not reduce to a naive one-parameter universality.
