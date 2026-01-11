# Mathematical Core of NCFT-core v5.2a5

## Field Primitives and State Space

Let $N \in \mathbb{N}$ denote the number of active interaction fields.
Each field $f_i$ is associated with:
(i) a unique identity label $\mathrm{id}_i \in \mathcal{I}$,
(ii) an activity flag $a_i \in \{0,1\}$,
(iii) an optional frequency parameter $\omega_i \in \mathbb{R}$, and
(iv) a complex state vector $\psi_i \in \mathbb{C}^d$.

**Dimension.**  
The state-space dimension satisfies $d \ge 2$. Toy models commonly use
low-dimensional realizations (e.g. $d=2,4,8$), but the formal theory does not fix
$d$.

**Identity Space.**  
The identity space is finite:

$$
\mathcal{I} := \{1,2,\dots,M\}, \qquad M \gg N,
$$

ensuring universal exclusion without identity exhaustion.

**Admissible State Space.**  
The NCFT-core state space is the unit-norm manifold:

$$
\mathcal{S}_N := \prod_{i=1}^N \left(\mathbb{S}^{2d-1} \times \mathbb{R} \times \{0,1\} \times \mathcal{I}\right),
$$

where $\mathbb{S}^{2d-1} \subset \mathbb{C}^d$ denotes the unit sphere.

---

## Projection Operator (Constitutive)

Define the projection operator

$$
\mathcal{P}(\psi) := \frac{\psi}{\|\psi\|}.
$$

For all admissible states:

$$
\|\mathcal{P}(\psi)\| = 1.
$$

Projection is **constitutive**: NCFT-core dynamics are defined only on the
projective unit-norm manifold. Unprojected or partially projected dynamics are
ill-posed and do not constitute NCFT-core dynamics.

States are projectively equivalent:

$$
\lvert \psi_i \rangle \sim e^{i\alpha} \lvert \psi_i \rangle.
$$

---

## Axioms

### Axiom 1: Universal Exclusion

Interaction is defined only between distinct active identities:

$$
\mathrm{Interact}(i,j) \iff (a_i=a_j=1)\ \land\ (\mathrm{id}_i \neq \mathrm{id}_j).
$$

Self-interaction is excluded:

$$
C_{ii} := 0.
$$

---

### Axiom 2: Projected Bilinear Coupling

For any interacting pair $(i,j)$, define the coupling:

$$
C_{ij} := \left|\left\langle \mathcal{P}(\psi_i)\middle|\mathcal{P}(\psi_j)\right\rangle\right|^2.
$$

Then:

$$
0 \le C_{ij} \le 1.
$$

Coupling depends only on projected state geometry and is invariant under local
phase transformations and global unitary rotations.

---

### Closure Condition: Pure Pairwise Interaction

Define the total interaction strength:

$$
\mathcal{C}(\{f_i\}) := \sum_{\substack{i < j \\ i,j\in\mathcal{A}}} C_{ij}, \qquad \mathcal{A} := \{i : a_i=1\}.
$$

No higher-order interaction terms appear at the fundamental level.

---

## Diagnostic Parameters (Non-Axiomatic)

Field-associated frequencies $\omega_i$ may be assigned for diagnostic or
classificatory purposes. Frequency dispersion does **not** affect stability,
alignment, or attractor structure and therefore does not define validity
conditions for NCFT-core dynamics.

---

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

Define numerical purity error:

$$
\varepsilon_{\mathrm{pur}} := \left| \mathrm{Tr}(\rho^2) - \frac{|\mathcal{A}| + 2\sum_{i < j} C_{ij}}{|\mathcal{A}|^2} \right|.
$$

---

## Dynamics (Validated Realizations)

NCFT-core constrains admissible interaction states but does not require a unique
microscopic update law. Validated realizations take the projected-flow form:

$$
\psi_i^{(t+1)} := \mathcal{P}\!\left( \psi_i^{(t)} - \eta\,\nabla_{\psi_i}\mathcal{E}(\{\psi_k^{(t)}\}) \right),
$$

with step size $\eta>0$ and energy functional:

\[
\mathcal{E}(\{\psi_k\}) := -\sum_{i<j} \left|\langle \psi_i \mid \psi_j \rangle\right|^2.
\]

Step-size bounds (e.g. $\eta<1$) are sufficient conditions used for analytical
clarity; numerical validation does not depend on sharp tuning of $\eta$.

---

## Attractor Structure and Stability (Empirical Characterization)

Extensive computational validation establishes that, under all admissible
constructions:

- NCFT-core dynamics are bounded and deterministic,
- the projected update map is dynamically gapped,
- perturbations decay on finite timescales,
- all valid flows converge to a **single global attractor**,
- no clustering, metastability, marginal modes, chaos, or critical behavior
  are observed.

These properties are derived consequences of the axioms and constitutive
projection and do not constitute additional assumptions.

---

## Theoretical Closure

Under projected dynamics, the evolution of $\mathcal{C}$ depends only on the
pairwise couplings $\{C_{ij}\}$. No emergent higher-order interaction terms
appear.

NCFT-core is therefore a closed, projection-enforced interaction theory. Any
extension beyond this structure—through additional state variables, alternative
manifolds, or modified interaction laws—constitutes a new theory rather than a
refinement of NCFT-core.

---

## Validation Addendum

All identities and bounds above are confirmed computationally across
$N=2,\dots,50$ with numerical tolerance $\sim10^{-8}$. Executable reference
implementations are provided in the GitHub toy suite.
