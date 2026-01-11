## Axiomatic Structure of NCFT-Core

NCFT-core is defined by a minimal axiomatic structure together with a primitive
and a closure condition. These elements jointly define a closed interaction
framework on a restricted state space. All axioms are structural and apply
independently of interpretation.

---

### Primitive: Field States

Each field \( f_i \) has a unique identity \( \mathrm{id}_i \in \mathcal{I} \) and
a unit-normalized state:

$$
\lvert \psi_i \rangle \in \mathbb{C}^d, \quad
\langle \psi_i \mid \psi_i \rangle = 1, \quad d \ge 2.
$$

The admissible state space of NCFT-core is the unit-norm manifold. Projection is
constitutive and defines the theory:

$$
\mathcal{P}(\psi) = \psi / \|\psi\|.
$$

States are projectively equivalent:

$$
\lvert \psi_i \rangle \sim e^{i\alpha} \lvert \psi_i \rangle.
$$

Dynamics are defined only on this projective manifold. Unprojected or partially
projected states are ill-posed and do not constitute NCFT-core dynamics.

---

### Axiom 1: Universal Exclusion

Interaction occurs only between distinct active fields:

$$
\mathrm{Interact}(i,j) \iff
(\mathrm{id}_i \neq \mathrm{id}_j) \land (a_i = a_j = 1).
$$

No field self-interacts:

$$
C_{ii} = 0.
$$

---

### Axiom 2: Projected Bilinear Coupling

Pairwise coupling between interacting fields is defined as:

$$
C_{ij} =
\big| \langle \mathcal{P}(\psi_i) \mid \mathcal{P}(\psi_j) \rangle \big|^2,
\quad 0 \le C_{ij} \le 1.
$$

Coupling depends only on projected state geometry and is invariant under local
phase transformations and global unitary rotations.

---

### Closure: Pure Pairwise Summation

Total interaction strength is defined by pure pairwise aggregation:

$$
F(\{\psi_k\}) = \sum_{i < j} C_{ij}.
$$

No higher-order interaction terms appear at the fundamental level.

---

### Regime Classification (Non-Axiomatic)

Field-associated frequencies \( \omega_i \) may be introduced for diagnostic or
classificatory purposes. Frequency dispersion does not affect stability,
alignment, or attractor structure and therefore does not define validity
conditions for NCFT-core dynamics.

---

### Dynamics (Validation Scope)

Executable toy models implement projected gradient-flow dynamics consistent
with the axioms:

$$
\frac{d}{dt}\lvert \psi_i \rangle
= -\Pi_i\!\left(\frac{\partial E}{\partial \langle \psi_i \rvert}\right),
\quad
E = -F.
$$

Alternative update rules or unconstrained evolutions are permitted as stress
tests or adversarial constructions but lie outside NCFT-core.

---

### Axiomatic Scope

The primitive, two axioms, and closure condition fully specify NCFT-core as a
closed effective interaction theory. Within this axiomatic scope, dynamics are
bounded, deterministic, dynamically gapped, and converge to a single global
attractor.

NCFT-core asserts no physical substrate, measurement apparatus, or empirical
interpretation. Such interpretations constitute separate modeling layers and
are not part of the axiomatic structure.
