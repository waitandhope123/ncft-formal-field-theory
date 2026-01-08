## Axiomatic Structure of NCFT-Core

NCFT-core is defined by a minimal axiomatic structure plus a primitive and a closure condition. These apply strictly within the projection-enforced, coherent regime and remain independent of interpretation.

### Primitive: Field States

Each field \( f_i \) has a unique identity \( \mathrm{id}_i \in \mathcal{I} \) and a unit-normalized state:

\[
\lvert \psi_i \rangle \in \mathbb{C}^d, \quad \langle \psi_i \mid \psi_i \rangle = 1, \quad d \ge 2.
\]

Projection operator:
\[
\mathcal{P}(\psi) = \psi / \|\psi\|.
\]

States are projectively equivalent:
\[
\lvert \psi_i \rangle \sim e^{i\alpha} \lvert \psi_i \rangle.
\]

---

### Axiom 1: Universal Exclusion

Interaction occurs only between distinct active fields:

\[
\mathrm{Interact}(i,j) \iff (\mathrm{id}_i \neq \mathrm{id}_j) \land (a_i = a_j = 1).
\]

No self-interaction:
\[
C_{ii} = 0.
\]

---

### Axiom 2: Bounded Bilinear Coupling

Pairwise coupling between interacting fields:

\[
C_{ij} = \big| \langle \mathcal{P}(\psi_i) \mid \mathcal{P}(\psi_j) \rangle \big|^2,
\quad 0 \le C_{ij} \le 1.
\]

Invariant under local phase transformations and global unitaries; depends only on projected state geometry.

---

### Axiom 3: Coherent Regime

Active fields maintain frequency coherence:

\[
\sigma(\{\omega_i : a_i = 1\}) < 0.1 \cdot \bar{\omega}.
\]

This defines the coherent phase where stable NCFT dynamics exist. Decohered regimes are permitted but excluded from predictions.

---

### Closure: Pure Pairwise Summation

Total interaction strength:

\[
F(\{\psi_k\}) = \sum_{i<j} C_{ij}.
\]

No higher-order terms appear at the fundamental level.

---

### Dynamics (Validation Scope)

Validated toy models use projected gradient flow preserving Axiom 1:

\[
\frac{d}{dt}\lvert \psi_i \rangle
= -\Pi_i\!\left(\frac{\partial E}{\partial \langle \psi_i \rvert}\right),
\quad E = -F.
\]

Unconstrained dynamics are permitted as stress tests but excluded from NCFT-core.

---

### Axiomatic Scope

These elements (primitive + three axioms + closure) fully specify NCFT-core as a closed effective field model within coherent regimes. They assert no physical substrate or measurement apparatus. Interpretations constitute separate modeling layers.
