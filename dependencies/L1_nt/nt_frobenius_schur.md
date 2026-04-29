---
axis: A
position: algebra_group
static_dynamic: static
connected_to:
  - A.algebra_group
  - A.algebra_constraint
  - L.number_theory
arrow_status:
  upstream: done
  downstream: pending
updated: 2026-04-10
runtime_summary:
  what: Frobenius-Schur indicator nu(rho), the real/complex/quaternionic classification of irreducible representations, and the pairing-type obstruction behind Tier sqrt Stark closure failure.
  when: Tier sqrt bookkeeping defense / Q_8 obstruction analysis / pairing type classification / R/C/H endomorphism algebra classification / Stark unit log-embedding symmetry arguments.
  provides: [frobenius_schur_indicator, orthogonal_type, symplectic_type, complex_type, pairing_type, endomorphism_algebra, schur_index, indicator_formula, real_character_criterion, q8_tier_sqrt_numerical_witness]
  consumes: [nt_relative_units.md §4, nt_conductor.md §6]
  axis: [A]
  residual_types: [R-gauge]
  key_theorems:
    - {id: FS_indicator_formula, statement: "nu(rho) = (1/|G|) sum_{g in G} chi_rho(g^2) in {+1, 0, -1}", derived_in: "§1.2", status: established}
    - {id: FS_trichotomy, statement: "nu=+1 gives real/orthogonal, nu=0 gives complex, nu=-1 gives quaternionic/symplectic", derived_in: "§1.3", status: established}
    - {id: pairing_obstruction, statement: "Tier sqrt occurs when nu(rho)=-1 and the intrinsically orthogonal unit lattice cannot supply the symplectic orientation needed by rho", derived_in: "§3.2", status: established}
  cost: small
  status: established
  one_screen: |
    §1 FS indicator: nu(rho) = (1/|G|) sum_g chi_rho(g^2). +1 = real/orthogonal, 0 = complex, -1 = quaternionic/symplectic.
    §2 Endomorphism algebra: End_G,R(rho) = R, C, H according to nu = +1, 0, -1.
    §3 Stark closure: log-embedded unit lattices are intrinsically orthogonal; quaternionic rho requires symplectic orientation, so Tier sqrt cannot be repaired by unit bookkeeping.
    §4 Small groups: S_3 all real, A_4 mixed but 3-dim real, D_4 all real, Q_8 has a 2-dim irrep with nu=-1.
    §4.4 Q_8 numerical witness: nu(rho)=-1 gives L(0,rho)^2=16 but L(0,rho)=±4; the sign is root-number data, not unit-regulator data.
---

# Frobenius-Schur Indicator and Representation Reality Type

**Level**: L1 (pure mathematics, domain-independent)  
**Dependencies**: `nt_conductor.md` §6 (Artin L-functions), `nt_relative_units.md` §4 (isotypic decomposition)  
**Downstream**: `research/brauer_closure_failure_taxonomy_v0.md` (Tier sqrt defense), OQ-NT-8

---

## §1 Frobenius-Schur Indicator

### §1.1 Motivation

For a finite group $G$ and an irreducible complex representation $\rho : G \to GL(V)$, the Frobenius-Schur indicator decides whether $\rho$ is realizable over the reals and what kind of invariant bilinear form it carries.

This matters for Stark closure because regulator and unit-lattice data are orthogonal objects. If the relevant Artin representation is quaternionic, the unit lattice can determine a square, but not the signed or oriented quantity itself.

### §1.2 Definition

For character $\chi_\rho(g)=\mathrm{tr}(\rho(g))$,

$$
\nu(\rho) := \frac{1}{|G|}\sum_{g\in G}\chi_\rho(g^2).
$$

Equivalently, using conjugacy classes $C$,

$$
\nu(\rho) = \frac{1}{|G|}\sum_C |C|\cdot \chi_\rho(C^{(2)}),
$$

where $C^{(2)}$ is the conjugacy class reached by squaring elements of $C$. Thus the indicator depends on the character table plus the power map.

### §1.3 Trichotomy

| $\nu(\rho)$ | Type | Meaning |
|---|---|---|
| $+1$ | real / orthogonal | $\rho$ has a real form and a $G$-invariant symmetric bilinear form. |
| $0$ | complex | $\rho \not\cong \bar\rho$; no real self-conjugate form. |
| $-1$ | quaternionic / symplectic | $\rho \cong \bar\rho$, but no real form of the same dimension; it carries a $G$-invariant alternating form. |

Important subtlety: a real-valued character does not imply $\nu=+1$. The 2-dimensional irreducible representation of $Q_8$ has real character values but $\nu=-1$.

### §1.4 Equivalent Criteria

- $\nu(\rho)=+1$ iff $\chi_\rho$ is real-valued and the real Schur index is $1$.
- $\nu(\rho)=0$ iff $\rho$ is not self-conjugate.
- $\nu(\rho)=-1$ iff $\chi_\rho$ is real-valued and the real Schur index is $2$.

---

## §2 Endomorphism Algebra

For the realification of $\rho$,

$$
\mathrm{End}_{G,\mathbb{R}}(\rho) \cong
\begin{cases}
\mathbb{R} & \nu(\rho)=+1,\\
\mathbb{C} & \nu(\rho)=0,\\
\mathbb{H} & \nu(\rho)=-1.
\end{cases}
$$

The $\mathbb{R}/\mathbb{C}/\mathbb{H}$ split is the representation-theoretic source of the orthogonal / complex / symplectic distinction.

| $\nu$ | Real Schur index | Real dimension of realization |
|---|---|---|
| $+1$ | 1 | $\dim \rho$ |
| $0$ | 1 | $2\dim \rho$ |
| $-1$ | 2 | $2\dim \rho$ |

---

## §3 Stark Closure Relevance

### §3.1 Unit Lattices Are Orthogonal

The logarithmic embedding

$$
\lambda : O_K^\times \to \mathbb{R}^{r_1+r_2}
$$

lands in the product-formula hyperplane. Galois acts on embeddings by permutation and conjugation, so the induced action on the real log space is orthogonal.

Consequently, all unit-group-derived objects, including relative unit subquotients, inherit symmetric regulator pairings.

### §3.2 Pairing-Type Obstruction

| $\nu(\rho)$ | Representation form | Unit-lattice form | Compatibility | Tier |
|---|---|---|---|---|
| $+1$ | symmetric / orthogonal | symmetric / orthogonal | compatible | Tier 1 or Tier 2 |
| $0$ | no real self-form | symmetric / orthogonal | partial | Tier 3+ or phase-sensitive |
| $-1$ | alternating / symplectic | symmetric / orthogonal | incompatible | Tier sqrt |

For $\nu=-1$, the obstruction is not a notation problem. A quaternionic representation requires symplectic orientation data, while the regulator side supplies orthogonal data. This mismatch is exactly what OQ-NT-8 calls the Tier sqrt obstruction.

### §3.3 Why This Is Not Bookkeeping

The obstruction is stable under changing the chosen unit residence:

1. The Frobenius-Schur indicator is a discrete character-theoretic invariant.
2. Pairing type is detected inside $\rho\otimes\rho$: orthogonal type has the trivial representation in $\mathrm{Sym}^2\rho$, while symplectic type has it in $\wedge^2\rho$.
3. The log embedding makes unit lattices intrinsically orthogonal.
4. Passing to relative units, subquotients, or larger unit groups preserves the symmetric regulator origin.
5. The endomorphism algebra $\mathbb{H}$ is not equivalent to the orthogonal $\mathbb{R}$ case.

---

## §4 Small Groups

### §4.1 Stark-Relevant FS Table

| $G$ | $|G|$ | Irrep dimensions | FS indicators | Stark tier prediction |
|---|---:|---|---|---|
| $S_3$ | 6 | 1, 1, 2 | +1, +1, **+1** | Tier 1 |
| $A_4$ | 12 | 1, 1, 1, 3 | +1, 0, 0, **+1** | Tier 1 for the 3-dim rep |
| $D_4$ | 8 | 1, 1, 1, 1, 2 | +1, +1, +1, +1, **+1** | Tier 2 |
| $Q_8$ | 8 | 1, 1, 1, 1, 2 | +1, +1, +1, +1, **-1** | Tier sqrt |
| $S_4$ | 24 | 1, 1, 2, 3, 3 | all +1 | Tier depends on $N$ and induction behavior |
| $A_5$ | 60 | 1, 3, 3, 4, 5 | all +1 | out of scope for this abelian-normal-subgroup framework |

### §4.2 $D_4$ vs $Q_8$

$D_4$ and $Q_8$ have the same irreducible dimensions and similar character tables, but different power maps:

- $D_4$: the 2-dimensional irrep has $\nu=+1$.
- $Q_8$: the 2-dimensional irrep has $\nu=-1$.

This is why the classifier must use character table plus power map, not just irreducible dimensions.

### §4.3 Sum Rule

The indicators satisfy

$$
\sum_{\rho\in\mathrm{Irr}(G)} \nu(\rho)\dim(\rho)
= |\{g\in G : g^2=e\}|.
$$

Examples:

- $S_3$: $1+1+2=4$, matching $e$ plus three transpositions.
- $Q_8$: $1+1+1+1-2=2$, matching $\{1,-1\}$.

### §4.4 Numerical Witness: $Q_8$ Tier Sqrt

The canonical $Q_8$ Stark failure example now has a numerical witness in `number_theory_dictionary_v0.md` §5.5.

For LMFDB `8.0.12230590464.1`, with $\mathrm{Gal}(H/\mathbb{Q})\cong Q_8$, the unique 2-dimensional irreducible representation $\rho$ has

$$
\nu(\rho)=-1.
$$

The field-data computation gives

$$
L(0,\rho)^2
= \frac{h_H R_H/w_H}{R_{\sqrt2}R_{\sqrt3}R_{\sqrt6}/2}
= 16,
$$

hence

$$
L(0,\rho)=\pm 4.
$$

This is the numerical form of the pairing obstruction:

- Orthogonal unit/regulator data determine the square.
- Quaternionic/symplectic orientation data determine the sign.
- Therefore the sign is external to unit-group bookkeeping and belongs to functional-equation/root-number data.

This upgrades the $Q_8$ line from a categorical Tier sqrt prediction to a numerically witnessed Tier sqrt obstruction.

---

## §5 Scope

### §5.1 This Entry Provides

- Definition and computation of the Frobenius-Schur indicator.
- The real / complex / quaternionic trichotomy.
- The $\mathbb{R}/\mathbb{C}/\mathbb{H}$ endomorphism-algebra split.
- The pairing-type obstruction for Stark closure.
- Small-group FS table for $S_3, A_4, D_4, Q_8, S_4, A_5$.
- The $Q_8$ Tier sqrt numerical witness $L(0,\rho)^2=16$, $L(0,\rho)=\pm4$.

### §5.2 This Entry Does Not Provide

- Full Brauer group theory.
- Modular representation theory in positive characteristic.
- Higher $K$-theory or Selmer-pairing replacements for the symplectic datum.
- A root-number calculation resolving the sign of the $Q_8$ example. (Root number structural residence now in `nt_root_numbers.md`; actual sign computation remains open.)

### §5.3 Current Connections

| Connection | Role | Direction |
|---|---|---|
| `nt_relative_units.md` §4 | isotypic decomposition and regulator pairing | upstream |
| `nt_conductor.md` §6 | Artin L-function dependence on $\rho$ | upstream |
| `number_theory_dictionary_v0.md` §5.5 | $Q_8$ Tier sqrt numerical witness | downstream |
| `research/brauer_closure_failure_taxonomy_v0.md` §14 | Tier sqrt non-bookkeeping defense | downstream |
| `nt_root_numbers.md` §3-5 | sign residence for Tier √ obstruction | downstream |
| `nt_dedekind_artin_zeta.md` §4 | functional equation sign constraints | downstream |
| `research/brauer_closure_galois_classification_v0.md` §10 | classifier input | downstream |

---

*Created: 2026-04-10*  
*Updated: 2026-04-10, after Q_8 Tier sqrt numerical witness.*
