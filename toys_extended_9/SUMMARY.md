# NCFT EXTENDED FRONTIER TOY SUITE — SUMMARY (Toys 17–20)

## Toy 17 — Baseline-Corrected Relaxation and Stability

**Filenames:**  
`toy17_critical_slowing_scan.py`  
`toy17_critical_slowing_scan_v2.py`

**What it does:**  
Probes linear response stability by measuring relaxation time τ of a
localized perturbation. The v2 implementation uses paired trajectories
with identical noise realizations to isolate excess response above the
stochastic baseline.

**Why it matters:**  
Apparent slowing-down under noise can be dominated by noise floors.
Baseline correction is required to distinguish genuine marginal dynamics
from strongly damped, stable regimes.

**Results:**  
After baseline correction, relaxation times remain O(1–3) steps across
the explored noise range. τ varies smoothly with noise strength and shows
only mild crossover behavior. No divergence, critical slowing-down, or
marginal stability is observed in the tested parameter regime. NCFT
coherent states are dynamically gapped and strongly stable.

---

## Toy 18 — Graph-Local Correlation Length and Spatial Structure

**Filenames:**  
`toy18_graph_correlation_length_v2.py`  
`toy18_graph_correlation_length_v3.py`  
`toy18_graph_topology_comparison_v4.py`

**What it does:**  
Restricts NCFT interactions to explicit graphs and measures perturbation
propagation using graph-local (edge-based) observables. Extracts a
correlation length ξ via exponential fits and examines its dependence
on coupling strength and graph topology.

**Why it matters:**  
Spatial structure and locality are essential physical features.
Correlation length determines whether a system supports short-range,
long-range, or critical transport once global coupling is removed.

**Results:**  
Perturbation response decays approximately exponentially with graph
distance for all tested parameters, defining a finite correlation length.
ξ increases smoothly with coupling strength η but saturates well below
system size, showing no divergence. Topology strongly influences ξ:
locally structured graphs (ring, random regular) support larger ξ than
small-world graphs, where shortcut-induced mixing enhances damping and
suppresses coherent persistence.

---

## Toy 19 — Coherence Under Frequency Detuning

**Filename:**  
`toy19_frequency_detuning_phase.py`

**What it does:**  
Introduces intrinsic frequency dispersion and a detuning-dependent
interaction kernel to test robustness of coherent NCFT dynamics under
heterogeneous local frequencies.

**Why it matters:**  
Detuning provides an operational probe of the coherence axiom, testing
whether collective alignment persists or degrades under intrinsic
mismatch among degrees of freedom.

**Results:**  
For the explored parameter range, NCFT dynamics robustly condense into
highly coherent states with purity near unity across detuning strengths.
Detuning alone does not destabilize coherence in the absence of strong
competing noise or dissipation, indicating a strongly coherence-seeking
dynamical bias in the model.

---

## Toy 20 — Fluctuation Spectra in Driven and Noisy Regimes

**Filename:**  
`toy20_power_spectra_psd.py`

**What it does:**  
Computes power spectral densities (PSD) of macroscopic observables
(energy, purity, mean coupling) in driven, dissipative, and noisy
non-equilibrium steady states.

**Why it matters:**  
Spectral structure distinguishes simple damped dynamics from oscillatory,
multi-timescale, or critical behavior. Frequency-domain analysis provides
a complementary diagnostic to time-domain relaxation.

**Results:**  
Observed spectra are broadband and largely featureless, with no dominant
peaks or scale-free structure. Purity fluctuations are strongly suppressed,
consistent with saturation near coherent fixed points. Driven NCFT steady
states exhibit stable, noise-dominated fluctuations rather than coherent
oscillatory modes.
