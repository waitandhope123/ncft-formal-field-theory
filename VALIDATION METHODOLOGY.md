# VALIDATION METHODOLOGY

Validation of NCFT-core was conducted through an extensive suite of executable
computational toy models designed not to demonstrate isolated behaviors, but to
systematically probe boundaries, invariant structures, and failure modes of
the theory. Numerical simulations are treated as falsification-oriented tools
rather than confirmatory demonstrations.

Each toy targets a specific theoretical question and includes null baselines,
adversarial variants, and intentionally ill-posed constructions. Failed or
divergent dynamics are retained as negative controls and are considered part
of the validation record.

---

## 1. Stability, Attractor Structure, and Spectral Diagnostics

Core dynamics were tested across wide ranges of system size, state dimension,
update scale, interaction topology, and projection enforcement. Linear response
analysis was performed by computing finite-difference Jacobians of the
projected update map around late-time states.

Eigenvalue spectra were examined to identify relaxation timescales, spectral
gaps, and stability margins. Baseline-corrected perturbation analysis was used
to distinguish genuine dynamical response from stochastic noise floors,
ensuring that apparent slowing-down effects were not misinterpreted as
marginal stability.

These tests establish that NCFT-core dynamics are dynamically gapped and
converge to a single global attractor under all valid constructions.

---

## 2. Topological and Kernel Robustness

Interaction graphs and coupling kernels were varied across dense, sparse,
random, small-world, and locally structured topologies. Graph-local observables
were used to quantify perturbation propagation and extract correlation lengths
under explicit locality constraints.

These tests assess sensitivity to network structure and determine whether
NCFT-core admits clustering, long-range order, or critical behavior under
restricted interaction geometry.

---

## 3. Noise Sensitivity and Controlled Non-Equilibrium Testing

Dynamics were evaluated under controlled perturbations, including additive
noise, temporary dropout, reinsertion, and bounded external driving. These
tests characterize sensitivity to non-idealized conditions without assuming
arbitrary openness or unbounded energy injection.

Power spectral density analysis was used to distinguish strongly damped steady
states from oscillatory or critical regimes in noisy or driven conditions.

---

## 4. Inverse Identifiability and Epistemic Limits

Inverse problems were constructed to determine which aspects of underlying
interaction structure can and cannot be reconstructed from partial or noisy
observations. These tests explicitly delimit epistemic limits and prevent
overinterpretation of observable data.

Non-identifiability results are treated as intrinsic properties of the theory
rather than deficiencies of inference procedures.

---

## 5. Coarse-Graining and Scale Dependence

Micro-level dynamics were aggregated and compared against independently evolved
macro-level systems to test closure under coarse-graining. Deviations were
tracked over time to assess whether errors accumulate or remain bounded,
distinguishing effective interaction behavior from exact renormalization
closure.

---

## 6. Statistical Detectability and Model Discrimination

Detection power, false-positive rates, and sample-size requirements were
quantified for NCFT-core signatures under varying noise and observability
conditions. Comparative model discrimination was performed to identify which
observables distinguish NCFT-core dynamics from competing normalized
interaction models.

---

## Methodological Scope

Across all categories, validation claims are restricted strictly to
projection-enforced NCFT-core dynamics. Frequency coherence is treated as a
classificatory descriptor and does not define validity or stability conditions.

Toys that violate axioms, relax projection, or exit the admissible state space
are retained as negative controls. Validation is therefore oriented toward
boundary discovery, falsification, and scope delimitation rather than selective
confirmation.

Any behavior not explicitly probed by this methodology lies outside the
validated scope of NCFT-core.
