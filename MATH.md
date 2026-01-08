# Mathematical Core of NCFT-core v1.2

## Field Primitives and State Space

Let $N \in \mathbb{N}$ denote the number of active interaction fields.
Each field $f_i$ is associated with:
(i) a unique identity label $\mathrm{id}_i \in \mathcal{I}$,
(ii) an activity flag $a_i \in \{0,1\}$,
(iii) a frequency parameter $\omega_i \in \mathbb{R}$, and
(iv) a complex state vector $\psi_i \in \mathbb{C}^d$.

**Dimension.**  
The state-space dimension satisfies $d \in \mathbb{N}$ with $d \ge 2$.
Toy models commonly use low-dimensional realizations (e.g. $d=2,4,8$),
but the formal theory does not fix $d$.

**Identity Space.**  
The identity space is finite:

$$
\mathcal{I} := \{1,2,\dots,M\}, \qquad M \gg N,
$$

ensuring universal exclusion without identity exhaustion.

**State Space.**  
The NCFT state space is:

$$
\mathcal{S}_N := \prod_{i=1}^N \left(\mathbb{C}^d \times \mathbb{R} \times \{0,1\} \times \mathcal{I}\right).
$$

## Projection Operator

**Projection / Normalization.**  
Define $\mathcal{P}:\mathbb{C}^d\setminus\{0\}\to\mathbb{C}^d$ by:

$$
\mathcal{P}(\psi) := \frac{\psi}{\|\psi\|}, \qquad \|\psi\| := \sqrt{\langle\psi|\psi\rangle}.
$$

**Exact Norm Preservation.**  
For any $\psi \neq 0$:

$$
\|\mathcal{P}(\psi)\| = 1.
$$

## Axioms

### Axiom 1: Universal Exclusion

Interaction is defined only between distinct active identities:

$$
\mathrm{Interact}(i,j) \iff (a_i=a_j=1)\ \land\ (\mathrm{id}_i \neq \mathrm{id}_j).
$$

### Axiom 2: Projected Bilinear Coupling

For any interacting pair $(i,j)$, define:

$$
C_{ij} := C(f_i,f_j) := \left|\left\langle \mathcal{P}(\psi_i)\middle|\mathcal{P}(\psi_j)\right\rangle\right|^2.
$$

Then:

$$
0 \le C_{ij} \le 1, \qquad C_{ii} := 0.
$$

The coupling depends only on the projected states $\psi_i,\psi_j$ and on no other metadata.

### Axiom 3: Frequency Consistency (Coherent Regime)

Let $\mathcal{A} := \{i : a_i = 1\}$.
Define the active-frequency mean:

$$
\bar{\omega} := \frac{1}{|\mathcal{A}|}\sum_{i\in\mathcal{A}} \omega_i,
$$

and dispersion:

$$
\sigma_\omega := \sigma\!\left(\{\omega_i : i \in \mathcal{A}\}\right).
$$

The coherent regime is defined by:

$$
\sigma_\omega < \delta_\omega, \qquad \delta_\omega := 0.1\,\bar{\omega}.
$$

### Closure Condition: Pure Pairwise Interaction

Define the total interaction strength:

$$
\mathcal{C}(\{f_i\}) := \sum_{\substack{i < j \\ i,j\in\mathcal{A}}} C_{ij}.
$$

No higher-order interaction terms are included.

## Derived Quantities and Invariants

### Density Matrix and Purity

Define the empirical density matrix:

$$
\rho := \frac{1}{|\mathcal{A}|} \sum_{i\in\mathcal{A}} |\psi_i\rangle\langle\psi_i|.
$$

Its purity is:

$$
\gamma := \mathrm{Tr}(\rho^2).
$$

**Purity Identity.**  
For unit-normalized states:

$$
\gamma = \frac{|\mathcal{A}| + 2\sum_{i < j} C_{ij}}{|\mathcal{A}|^2}.
$$

Define the numerical purity error:

$$
\varepsilon_{\mathrm{pur}} := \left| \mathrm{Tr}(\rho^2) - \frac{|\mathcal{A}| + 2\sum_{i < j} C_{ij}}{|\mathcal{A}|^2} \right|.
$$

## Dynamics (Validated Realizations)

NCFT-core constrains valid interaction states but does not require
a unique microscopic update law.
Validated dynamics take the projected-flow form:

$$
\psi_i^{(t+1)} = \mathcal{P}\left( \psi_i^{(t)} - \eta\,\nabla_{\psi_i}\mathcal{E}(\{\psi_k^{(t)}\}) \right),
$$

where $\eta>0$ is a step size and:

$$
\mathcal{E}(\{\psi_k\}) := -\sum_{i<j}|\langle\psi_i|\psi_j\rangle|^2.
$$

The bounds on step size ($\eta < 1$) and coherence threshold
($\delta_\omega = 0.1\,\bar{\omega}$) are sufficient conditions derived
for analytical clarity. Numerical validation in this work explores
subsets of this regime and does not attempt to identify sharp stability
or coherence boundaries.

**Step Size Bound.**  
The projected flow is stable for:

$$
\eta < 1,
$$

since $\mathrm{Lip}(\nabla_{\psi_i}\mathcal{E}) \le 2$.

**Coherent Basin Entry.**  
If:

$$
\sigma_\omega^{(0)} < 1.5\,\delta_\omega,
$$

the system enters the coherent regime under projected flow.

The flow preserves the projected bilinear coupling, coherence condition,
and pure pairwise closure by construction.
Universal exclusion is enforced structurally.

## Predictions and Scaling Laws

Within the coherent regime:

- $\mathbb{E}[\varepsilon_{\mathrm{pur}}] < 10^{-10}$ under double-precision numerics.
- $\mathrm{Var}(\mu_C) = O(|\mathcal{A}|^{-2})$ as $|\mathcal{A}|\to\infty$.
- $\gamma \ge 1/|\mathcal{A}|$, with equality iff all $C_{ij}=0$.
- $\sup \mathcal{C} = \binom{|\mathcal{A}|}{2}$, attained under perfect alignment.

## Theoretical Closure

**Pure Pairwise Closure.**  
Under projected flow, no emergent higher-order interaction terms arise.
The time evolution of $\mathcal{C}$ depends only on $\{C_{ij}\}$,
and the evolution of $\sigma_\omega$ depends only on $\{\omega_i\}$.

**Proof sketch.**  
$\dot{\mathcal{C}}$ is bilinear in $\{\dot{\psi}_i\}$, which depend only on
pairwise Gram matrix derivatives $\partial_{\psi_i}\langle\psi_i|\psi_j\rangle$.
No higher-order dependencies appear.

## Validation Addendum

All bounds above are confirmed computationally across
$N=2,\dots,50$ with numerical tolerance $\sim10^{-8}$.
Validated Python baselines are provided in the GitHub toy suite.

## Empirical Dynamical Properties (Validated)

The axiomatic and mathematical structure of NCFT-core does not assume specific
dynamical spectral properties beyond those implied by projection enforcement
and pure pairwise closure. However, extensive computational validation
establishes several empirically robust properties of the projected dynamics
within the coherent regime. These properties are reported here for completeness and do not constitute additional axioms or assumptions.

**Spectral Gap and Linear Stability.**  
For late-time coherent states evolved under projected flow, the finite-difference
Jacobian of the one-step update map exhibits eigenvalues strictly within the unit
circle. The spectrum separates into a small number of slow collective modes and
a bulk of rapidly damped modes, with a finite spectral gap. This implies linear
stability of coherent attractors and finite relaxation timescales. No marginal
eigenvalues or critical slowing-down are observed within the validated regime.

**Short-Range Correlation Under Locality.**  
When interactions are restricted to explicit graphs, perturbation influence
decays approximately exponentially with graph distance. This defines a finite
correlation length $\xi$ that increases smoothly with coupling strength but
saturates well below system size. No divergence of $\xi$ or emergence of
scale-free spatial structure is observed.

**Effective, Not Critical, Dynamics.**  
The presence of both a spectral gap and a finite correlation length implies that
coherent NCFT dynamics do not approach criticality under parameter variation
within the validated regime. NCFT therefore behaves as a strongly damped,
non-critical effective interaction theory rather than a marginal or
scale-invariant one.

These properties are derived consequences of the axioms under projection-enforced
dynamics and are included solely to characterize the empirical dynamical regime
validated in this work.
