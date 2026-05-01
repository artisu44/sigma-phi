# Paper N1: Observation Theory — Number-Theoretic Edition

**Subtitle**: S15 Trichotomy, Arrow Structure, T-AAS, and Internal NT Triangulation

**Version**: v0.7 (N5 backward link + NT 5-paper closure, 2026-04-27)
**Status**: DRAFT — NT-only reformulation derived from Paper D (multi-domain v0.9.2)
**Prerequisites (L0)**: `observation_canon.md`, `finite_observation.md`, `identity_asymmetry.md`
**Prerequisites (L1)**: `c_phase_complex.md §4`, `c_theorems_master.md` (S12-S17), `c_arrow_framework.md`, `c_arrow_obstruction.md §10-§11`, `c_arrow_bridge_constants.md`, `c_filtration_obstruction.md`, `c_observation_optimal_gauge.md`
**Prerequisites (L1 NT)**: `nt_conductor.md`, `nt_dedekind_artin_zeta.md`, `nt_frobenius_schur.md`, `nt_genus_class_fields.md`, `nt_relative_units.md`, `nt_root_numbers.md`
**Sequel papers**: N2 (Paper 2 structural analysis) / N3 (Path 2 number-theoretic universality) / N4 (Hasse-Weil L × Stark) / N5 (Brauer obstruction theory + Origination)

---

## §0 Abstract

Number-theoretic observables are exclusively and exhaustively classified into the domain-agnostic three-layer structure **S15 Observable Trichotomy** (Scan / Structural / Information). The commutativity of the three Arrows connecting these layers guarantees translation between the ζ-family, Galois representations, and class-group systems. The Arrow 1 kernel decomposes via **T-AAS** into ker_gauge ⊕ ker_topo, and the conductor splits as f_torsion + f_rational.

This paper is a number-theoretic reformulation of Paper D (multi-domain v0.9.2). Multi-domain triangulation has been stripped, and the structure is rebuilt via **Arrow-level triangulation** using **three NT-internal instances** (Paper C three-layer decomposition / Stark projection / Brauer closure).

**Six main results**:

1. **S15 NT-only restatement** — Enumeration of three layers (Scan, Structural, Information with 7 / 13 / 9 instances respectively) plus exhaustive coverage by the six L1 NT entries → exhaustivity closure within NT.
2. **NT-internal verification of Arrow structure** — Three Arrows close within NT instances alone; commutativity at extreme limits is verified by three NT instances (β → 0, s → ∞, s = 1 pole).
3. **T-AAS decomposition: 3 NT instances + 1 open** — 12/12 NT-relevant fitness via Stark / Brauer / OQ-P2-3; Hodge remains the NT-adjacent open frontier.
4. **NT-internal Arrow-level triangulation** — Three NT instances each cover **a different primary Arrow** (Brauer = Arrow 1 kernel / Stark = Arrows 2-3 / Paper C = three Arrows simultaneously).
5. **Six-step protocol for new NT domains** — Verified across five number fields; standard procedure for new L-function families and new Galois representation classes.
6. **Observation-optimal gauge theorem (NT-internal 2-instance contrast)** — Paper C (coincide) vs. Paper 2 (split) is contrasted in this paper at the statement level; structural analysis is deferred to N2.

**Thesis**: Number-theoretic observables independently support the entire framework of observation theory (axioms / S15 / Arrow / T-AAS / triangulation) without requiring any out-of-domain instance. This paper functions as the theoretical foundation for N2-N5.

**Forward / dictionary impact**: Frames the N2-N5 NT-internal sequence; dictionary write-back across L0 / L1 / Meta layers (annexes implemented during N2-N5 drafting, see §8.4).

---

## §1 Introduction

### 1.1 Why "number-theoretic observation theory"?

The classical NT object π(x) − li(x) is described as an "oscillation spectrum" through the non-trivial zeros of ζ(s). The ΣΦ dictionary frames this as "a quantity visible under τ-scan" and has accumulated evidence that NT observables reside in the common **observation trichotomy S15** (`bidirectional_duality_v0.md`).

The chain S12 (exponential scan family) → S13 (ln 2 fixed point) → S14 (π / ln 2 asymmetric duality) → S15 (Observable Trichotomy) yields the conclusion:

> **NT observables are different projections of an additive ⇔ multiplicative duality, and these projections are exclusively and exhaustively classified into three layers.**

While Paper D (multi-domain) established the universality of observation theory through triangulation across FX / image AI / DNA / crystallography / quantum, this paper focuses on **NT-internal self-closure** and is intended as the theoretical foundation for N2-N5.

### 1.2 Scope of this paper

**Structure**: §2 axioms / §3 S15 / §4 Arrows / §5 T-AAS / §6 triangulation / §7 protocol / §8 consequences.

**Out of scope** (deferred): multi-domain triangulation (→ Paper D) / Origination matrix 8-gauge (→ N5) / quantum observation theory's independent aspects (→ Q1) / core theorems of Paper 2 structural analysis (→ N2) / Path 2 universality (→ N3) / Hasse-Weil L (→ N4) / Brauer failure-mode details (→ N5).

### 1.3 Terminology and "gauge" disambiguation

**Basic terms**: Observable / Scanner = external parameter accompanying Scan (s, β, τ, t) / **§4 dual** = pair (ι_L: additive ℤ → S¹, χ: multiplicative character) / Arrow = map connecting the three S15 layers / T-AAS = Arrow 1 kernel decomposition theorem / Triangulation = elimination of coincidence via three independent instances / **Residence** = which dictionary entry a given result, theorem, or observable is filed under (e.g. "this theorem resides in `c_arrow_framework.md §4`"); used throughout the paper to describe placement within the ΣΦ dictionary.

**Three uses of "gauge"** (avoiding confusion):

| Symbol | Name | Meaning | Scope in this paper |
|---|---|---|---|
| **gauge¹** | §4 dual gauge | choice of ι_L / χ = structural root of observation | §2-§4 throughout |
| **gauge²** | Origination 8-gauge | family of 8 origination fields for constants | §6.2 Stark 6-gauge + §8.2 N5 forward only |
| **gauge³** | Arrow 3 base-of-log gauge | choice of log base (b > 0, b ≠ 1) | §4.5 S17 base-invariance only |

The "ker_gauge" of T-AAS refers to the **gauge¹** family. gauge² appears only in §6.2 and §8.2 forward references and does not enter the main structure of this paper.

### 1.4 Direction-axis position (NT-framework = A-primary native)

Under the A/B observation direction axis of `user_observation_direction_axis` (ESTABLISHED 2026-05-01), the NT framework of this paper occupies the **A-direction primary native** position (distinct from Q1 = B-primary, I1 = A+B co-resident; this paper provides the A-side anchor).

| Side | Direction | Observation mode | NT-side instance |
|---|---|---|---|
| **additive / discrete / NT** | **A (finite → infinite)** | **finite observation → outer extrapolation toward infinity** | **primary domain of this paper** |
| multiplicative / continuous / quantum | B (infinite → finite) | infinite ontology → inner projection onto finite | (out of scope; handled by Q1 framework) |

**A-direction-native instances on the NT side**:
- **PNT / prime density** (§3.2 Scan layer): finite count of primes up to $N$ → asymptotic extrapolation $\pi(N) \sim N/\log N$
- **Class number formula bridge** (§4.1): in the rank 0 case, $h_K = \lim_{s\to 1}(s-1)L(s, \chi)$ provides an **explicit B-direction lift via a lim operator** = the canonical bridge that projects A-native ($h_K$, finite class number) through B-native L
- **Hasse-Weil L predictive content** (§3.3 / N4 §7): weight-2 Hasse-Weil L is **B-native** (Galois rep + Euler product); within this N1 framework it is the B-side bridge instance, and in N4 it functions as a genuine BSD analytic-rank detector
- **Dirichlet L** (N3 §4): weight-1 Dirichlet L is **A-native** (finite character on a finite group); the framework's predictive content here degrades to "structural fit only" — exactly the direction-tag native scope

**Cross-direction bridge instances (§4-§6)**:
- **S14 = π / ln 2** (`c_arrow_bridge_constants §4` + this paper §4.5): **canonical bridge** between Arrow 1 (π involution, A-side) and Arrow 2 (ln 2 involution, B-side) under involution × involution role-match; the ratio that links the N1 (A-primary) and Q1 (B-primary) framework headers
- **S_0 = 2π/e** (`c_arrow_bridge_constants §13` ESTABLISHED): bridge ratio between Arrow 1 (2π period, A) and Arrow 3 (e argmax, B); pins framework universality at both A-side and B-side anchors
- **κ(2) = √3/4 candidate** (`c_recursive_floor_principle §6.7`): A-native (2D JP iteration) ↔ B-native (closed-form algebra) **cross-direction near-coincidence without bridge** = a direction-tag screening rule G1 REJECT prediction instance, with forward-actionable promotion path = bridge-operator-construction OQ
- **N4 weight-class transfer pattern** (N4 §7.2.1): the explanation of weight-class-dependent transfer (weight-2 Hasse-Weil B↔B genuine BSD vs weight-1 Dirichlet A↔B "structural fit only") at the direction-tag level = `feedback_cross_direction_identity_screen` 6/6 forward test reference instance #2

**Screening rule application**: when making identity claims within this paper, every relevant quantity must first be tagged (A-native / B-native / bridge / transition); for cross-direction pairs without an explicit bridge operator (lim / projection / Hecke / regulator etc.), strict identity is rerouted to near-coincidence + bridge candidate (`feedback_cross_direction_identity_screen` 5-step operational order). Position parallel to Q1 §1.4 / I1 §1.4.

**N1 / Q1 / I1 framework header parallel** (cross-paper):

| Header | Native primary | Prominent bridge instance |
|---|---|---|
| **N1 (NT)** | **A-primary** | π (S14 numerator), class number formula bridge $h = \lim(s-1)L$ (rank-0) |
| Q1 (Quantum) | B-primary | σ\* (S4), Born rule projection |
| I1 (Information) | A + B co-resident (Hartley A / Shannon B 1+4 split) | S_0 = 2π/e, S13 ln 2, σ\* |

The direction-axis triangulation of these three headers verifies framework universality at A-side / B-side / co-resident anchors — a 3-instance verification — with the I framework supporting the NT-Quantum bridge as an operational language layer.

**Audit reference**: `project_graveyard_audit_complete_2026_05_01` (Tier 1-4 audit completion); `feedback_cross_direction_identity_screen` (5-step operational order).

---

## §2 Axioms of Observation Theory

### 2.1 Observation triple (S, W, m) — NT instances

| Symbol | Meaning | NT example |
|---|---|---|
| **S** | infinite structure | prime distribution, number field K, Galois rep ρ, L-function L(s, χ) |
| **W** | finite window | gauge L = XY, conductor f_χ, embeddings (r₁, r₂), k_max truncation |
| **m** | measurement | Dirichlet series evaluation, carry rate, h_K computation, numerical L'(0, χ) |

The observed value `m(S|_W)` depends on both S and W. The quantity `m(S) − m(S|_W)` is the **finite observation error**, whose structure this paper analyses.

### 2.2 Axioms A0-A7 (NT instance examples)

| ID | Name | NT instance |
|---|---|---|
| **A0** | Finite observation | gauge M = XY, k_max = 30 (Paper C §3.6) |
| **A1** | Structured error | D_floor decomposition: arithmetic residue ∼26%, projection ∼60-70%, noise ∼5-10% |
| **A2** | Convergence as observable | π(N) → li(N) with α = 1/2 (GRH); D_floor ∼ N^{−2/3} (Paper C §3.3) |
| **A3** | Gauge invariance/dependence | \|c_χ(M)\|² gauge-invariant, κ_g (gap density) M-invariant |
| **A4** | Non-commutative limits | lim_{N} lim_{L} ≠ lim_{L} lim_{N} yields different prime statistics |
| **A5** | Saturation | conductor → ∞ gives amp/A → 1; class number formula is the saturation limit |
| **A6** | Path dependence | rank-1 Stark log\|σ(ε_χ)\| depends on choice of embedding |
| **A7** | Scanner hierarchy | ζ(s) scanner = s; F_{g,k}(s) scanner = s with internal scan τ(p); Z(β) scanner = β |

Details: `finite_observation.md §1-§7`.

### 2.3 §4 dual = NT-internal root

**Claim 2.1** (root status): The ι_L / χ dual of `c_phase_complex.md §4` is the unique source of all upper structures (S12-S17, T-AAS) in the dictionary.

**NT instance**: ι_L = additive Dirichlet character / χ = multiplicative Dirichlet character / **ℂ = S¹ × ℝ_{>0}** polar decomposition separates observation into the additive axis (arg z) and multiplicative axis (\|z\|).

NT-internal projection chain of the §4 dual (`bidirectional_duality_v0.md §3.4`): L0 (arg / \|·\| separation) → L1 (nt_conductor / nt_dedekind_artin_zeta / nt_frobenius_schur) → L2 (number_theory_dictionary v1 all K-cases). The axiom system of this paper takes the §4 dual as root, and all derivations close within NT.

### 2.4 L0 v2 — 2-axis (Fi/I × D/C) lens

L0 v1 (finite observation axioms) is reformulated under the orthogonal 2-axis framework **Finite/Infinite (axis-2)** × **Discrete/Continuous (axis-1)** (`finite_observation.md §8`):

> **(a')** The observer **lives on the Fi side of axis-2**. There is no Arrow in the Fi → I direction; the Fi/I boundary is unbridgeable.
> **(b')** When any Arrow crosses the axis-2 Fi/I boundary, a kernel (obstruction) appears on the boundary. Observation = unidirectional **I → Fi traversal**.
> **(c')** Kernel splits into three: Fi-side artifact (ker_gauge, contributes to f_torsion) / I-side residue (ker_topo, contributes to f_rational) / Fi → Fi internal irreversibility (ker_backaction).
> **(d')** Observation theory = **taxonomy of axis-2 Fi/I boundary**.

L0 v1 ⊂ L0 v2 (conservative extension).

**NT instance**: analytic continuation of ζ(s) (s > 1 = Fi side → all of ℂ = I-side idealisation) / prime distribution (primes ≤ N = Fi, all primes = I) / ζ-zeros γ_n (height ≤ T = Fi, RH = I-side claim).

**Status**: ESTABLISHED (`oq_l0_refinement_finite_infinite_2axis_v0.md`).

---

## §3 S15 Observable Trichotomy — NT-internal description

### 3.1 Main theorem

**Theorem 3.1 (S15, NT-only restatement)** — An NT observable O belongs to one of the following **exclusive and exhaustive** partitions:

| Class | Definition form | Feature |
|---|---|---|
| **(A) Scan** | O(scanner) = Σ_{d ∈ D} f(d) · exp(a(scanner)·b(d)) | parametric family with scanner variable |
| **(B) Structural** | O = parameter-free integer/topological invariant | no scanner; discrete skeleton |
| **(C) Information** | O = −Σ p log p type | log-inverse of S12 family |

**Status**: ESTABLISHED 2026-04-11 (`c_theorems_master.md` row S15). NT-internal exhaustivity closure is given in §3.5.

### 3.2 Scan layer (NT subset of the S12 family)

Two-fold classification: additive scan (imaginary axis, S¹ rotation) and multiplicative scan (real axis, exponential decay).

| Instance | Scanner | Kernel | Add./Mult. |
|---|---|---|---|
| ζ(s) | s | Σ n^{−s} | multiplicative |
| L(s, χ) | s | Σ χ(n) n^{−s} | multiplicative |
| L(s, ρ, K/k) | s | Artin L | multiplicative |
| ζ_K(s) | s | Σ_𝔞 N𝔞^{−s} | multiplicative |
| Z(β) | β | Σ e^{−β E_n} | multiplicative |
| G_k(s) | s | Σ_p e^{2πik τ(p)} · p^{−s} | mixed add./mult. |
| F_{g,k}(s) | s | Σ_{p:p+g prime} e^{2πik τ(p)} · p^{−s} | mixed add./mult. |

**Feature**: scanner s is a complex variable (Re(s) = multiplicative axis, Im(s) = additive axis with γ₁ = 14.135, etc.). gauge L = XY is the input spec; k_max truncation determines the Nyquist resolution.

### 3.3 Structural layer

| Observable | Definition | Residence |
|---|---|---|
| h_K | class number \|Cl(O_K)\| | `c_spectral.md §8` |
| R_K | regulator | `nt_relative_units.md` |
| w_K | order of μ(K) | `c_spectral.md §8.5` |
| d_K | absolute discriminant | `nt_conductor.md §6.4` |
| ω(X) | number of prime factors (carry conductor) | `oq_p2_1_carry_closed_form.md §2.4` |
| f_p(ρ) | local Artin conductor | `nt_conductor.md §6.2` |
| f_χ | Dirichlet conductor | `nt_conductor.md §6.1` |
| codim(s) | codimension of zone | `nt_conductor.md §5, T6` |
| b₁(G) = K − M + 1 | first Betti number | `nt_conductor.md` T5 |
| Cl(O_K), O_K^×, r₁, r₂ | class group / unit group / embedding counts | Dirichlet's unit theorem |

**Relation to §4 dual**: Structural is the **discrete skeleton** of the Scan kernel's domain — the shape of the "container" of the exp kernel.

### 3.4 Information layer (log-exp dual)

| Observable | Definition | Residence |
|---|---|---|
| H(X) = −Σ p log p | Shannon entropy | `c_information_theory.md` |
| Λ(n) | von Mangoldt (= coefficient of −ζ'/ζ) | `c_spectral.md` |
| log h_K, log R_K, log w_K | factors of class number formula 6-gauge | `nt_relative_units.md` |
| D_KL, H_α | KL / Rényi | `c_information_theory.md` |
| ε_{g,k}(N) | Paper C arithmetic residual | Paper C §4 |

**Relation to §4 dual**: Information is the **log-inverse** of the exp kernel. The standard chain Z(β) → F = −kT log Z → S = −∂F/∂T applies. S13 ln 2 is the parity fixed point of this layer.

### 3.5 Exclusivity / exhaustivity (NT-internal closure)

NT-internal verification closes in three steps:

**(i') Existence of observables in each layer** (lower bound for exhaustivity): Scan 7 / Structural 13 / Information 9 instances enumerated in §3.2-§3.4. All three layers non-empty. (Counting convention: Scan = 7 distinct rows of the §3.2 table; Structural = 13, counting Cl(O_K), O_K^×, r₁, r₂ separately within the final row of §3.3; Information = 9, counting log h_K, log R_K, log w_K and D_KL, H_α individually within the §3.4 table.)

**(ii') L1 NT 6-entry enumeration** (upper bound for exhaustivity):

| L1 NT entry | Main observables | S15 layer |
|---|---|---|
| **nt_conductor** | f_χ, f_p(ρ), Artin conductor, codim hierarchy | Structural |
| **nt_dedekind_artin_zeta** | ζ_K(s), Artin factorisation, permutation character | Scan; ratio → Information |
| **nt_frobenius_schur** | ν(ρ) FS indicator (∈ {0, ±1}) | Structural |
| **nt_genus_class_fields** | H_K, K^gen, Galois group | Structural |
| **nt_relative_units** | $O_{F_1}^\times / O_{F_2}^\times$, R_rel | Structural (lattice + co-volume) |
| **nt_root_numbers** | W(ρ) Artin root number, ε-factor | Structural (finite order) |

All observables in the six L1 NT entries fall into Structural or Scan. Information arises as the log-derivative derived from (Scan, Structural) and resides in `c_spectral.md` / `c_information_theory.md`. **Absence of counter-example**: across 6 entries × all observables exhaustively, no NT observable falling outside the three layers is known as of v0.2.

**(iii') S12/S13/S14 consistency**: S12 ⊂ Scan (trivial) / S13 = ζ functional eq at s = 1/2 (D_floor minimum, detailed in N2) / S14 asymmetry = π (S¹ torsion algebra) vs. ln 2 (`-log` operator analysis) — closes within NT.

All three steps closed → S15 trichotomy is **CLOSED on all 3 conditions** within NT.

---

## §4 Arrow Structure — Three connections

### 4.1 Arrow 1: Scan → Structural (domain structure)

**Principle**: In O(scanner) = Σ_{d ∈ D} f(d) · exp(a·b), D (the data space) and f encode Structural.

| Scan | D | Encoded Structural |
|---|---|---|
| ζ(s) | n ∈ ℤ_{>0} | h_K, f_p(ρ), w_K, d_K |
| L(s, χ) | n with χ-weight | f_χ |
| L(s, ρ, K/k) | prime ideals 𝔭 | f(ρ, K/k), ν(ρ), W(ρ) |
| ζ_K(s) | ideals 𝔞 of O_K | h_K · R_K · w_K · d_K (class number formula) |
| F_{g,k}(s) | prime pairs (p, p+g) | κ_g, ω(X) |

**Formalisation**: the operation of "reading" D and f in Scan(scanner; D, f) returns Structural. Structural = **input specification** of Scan.

#### 4.1.1 Observable-choice dependence

The Structural extracted by Arrow 1 is **not unique**. When several candidates coexist within the same NT domain, observable-specific verdicts are required (`c_arrow_framework.md §3`):

| Candidate | Definition | Balance locus | Gauge verdict |
|---|---|---|---|
| **D_floor minimum** (Paper C) | minimiser of D_floor in s | s = 1/2 | coincide via functional-eq enforcement |
| **carry rate c(g, X)** (Paper 2) | digit-overflow probability of u(n) | X = 2g (15 gaps tested) | split with no enforcement (X = 6) |
| **ω(X) conductor** (OQ-P2-1) | number of prime factors of X | parameter | observable selector |

**Principles**: (1) Alignment (consistency with the natural arithmetic of the domain), (2) Observable-specific verdict, (3) explicit propagation to the verdict form. Arrow 1 acts not as an injection but as an **observable selector**.

### 4.2 Arrow 2: Scan → Information (log-exp duality)

**Principle**: thermodynamic chain
```
G(scanner) = Σ_d f(d)·exp(a·b)   ← Scan
F(scanner) = −log G(scanner)      ← log bridge
I = −∂F/∂(scanner)|_{natural}    ← Information
```

| Scan | G | F | Information |
|---|---|---|---|
| ζ(s) | Σ n^{−s} | −log ζ(s) | Λ(n) via −ζ'/ζ |
| L(s, χ) | Σ χ(n) n^{−s} | −log L(s, χ) | Λ_χ(n) |
| Z(β) | Σ e^{−βE} | −kT log Z | S = −Tr(ρ log ρ) |
| G_k(s) | Σ_p e^{2πik τ(p)} p^{−s} | −log G_k(s) | rate function |

**S13 fixed point**: the self-fixed locus s = 1/2 of ζ(s) = ζ(1−s) is the half-value fixed point on Arrow 2 (parity-fixed ln 2). Details: §4.5.

### 4.3 Arrow 3: Structural → Information (combinatorial counting)

**Principle**: Hartley entropy $H_0(D) = \log |D|$ — log of the cardinality of Structural.

| Structural | \|D\| | H_0 = log\|D\| | Meaning |
|---|---|---|---|
| Cl(O_K) | h_K | log h_K | class-group information capacity |
| μ(K) | w_K | log w_K | torsion-unit information capacity |
| Galois orbit | [K:k] | log [K:k] | Galois-group information capacity |
| primes ≤ N | π(N) | log π(N) ∼ log(N/log N) | prime counting |
| residues mod L | φ(L) | log φ(L) | character-group information capacity |

**S17 fixed point**: the info density d(n) = (log n)/n attains its extremum at n = e (the **derivative-fixed extremum on Arrow 3**, gauge³-invariant). Details: §4.5.

### 4.4 Commutativity of the three Arrows

```
              log
Scan ─────────────────→ Information
  │                          ↑
  │ input spec               │ log
  ↓                          │
Structural ──────────────────┘
```

**Theorem 4.1 (commutativity of three Arrows)**: at extreme limits scanner → 0 (or ∞), the three Arrows commute. Three NT instances:

| Instance | Limit | Mechanism |
|---|---|---|
| **β → 0** | Z(β→0) = Σ_n 1 = \|states\|, S = log\|states\| = H_0 | log Z = Hartley; in NT context, the partition by prime-place splitting |
| **s → ∞** | ζ(s→∞) → 1 (only n=1), Scan = 1-point measure → Structural = {1} → Info = 0 | trivial commutativity (all zero) |
| **s = 1 pole** | Class number formula: $\mathrm{Res}_{s=1} \zeta_K(s) = (2^{r_1}\cdot(2\pi)^{r_2}\cdot h_K\cdot R_K)/(w_K\cdot \sqrt{\|d_K\|})$ | Arrow 1 encodes the Structural skeleton, Arrow 2 sends −log ζ_K → Λ_K, Arrow 3 yields log h_K + log R_K + …; three paths simultaneously yield finite residue ⇒ **strongest NT instance** |

Three instances verify commutativity at both extreme limits and at the singularity.

#### 4.4.1 Arrow commutativity = axis-2 Fi/I commutation

Under the L0 v2 lens of §2.4, Theorem 4.1 is reread as **commutation of axis-2 Fi/I operations**.

**Axis-2 traversal of each Arrow**:

| Arrow | Axis-1 | Axis-2 | Traversal type |
|---|---|---|---|
| **Arrow 1** | C → D (collapse) | I → Fi (observation-standard) | one-directional I → Fi component present |
| **Arrow 2** | C → C (preserved) | Fi↔Fi / I↔I (preserved) | pure axis-1 bridge |
| **Arrow 3** | D → C (lift) | Fi → Fi (typically) | axis-1 primary, axis-2 secondary |

**Theorem 4.1′ (Fi/I commutation)**: at extreme limits the three Arrows degenerate their axis-2 I component and close as pure Fi-side operators:
$$[T_i, T_j]|_{\text{Fi-only}} = 0 \quad (i, j \in \{1, 2, 3\})$$

Outside the extreme limit the commutator is generally non-zero — this is the source of the coincide/split dichotomy in §4.5.1.

**Status**: ESTABLISHED (`c_arrow_framework.md §5`).

### 4.5 S13 / S14 / S17 residence — NT context

Residence of S13 (e^{−x} = 1/2 ⟹ x = ln 2) / S14 (π vs. ln 2 asymmetry) / **S17 (Arrow 3 e-extremum, ESTABLISHED 2026-04-23)**:

| Constant | Residence | Mechanism (NT context) | Stationary form |
|---|---|---|---|
| π | inside Scan (additive axis) | S¹ torsion ι_2(1) = e^{iπ} = −1, generator of additive Dirichlet character → **algebraic** | S14 parity (additive) |
| ln 2 | on Arrow 2 | half-value condition + log bridge, ζ functional eq at s = 1/2 → **analytic** | **value-fixed** (S13) |
| **e** | **on Arrow 3** | info density d(n) = (log n)/n max at n = e, gauge³-invariant → extremum principle. NT: winning size for Hardy-Littlewood prime gaps / log p weighting | **derivative-fixed** (S17) |

(Note on gauge³: the choice of base for log only rescales d(n) by a constant factor and therefore does not move the location of its extremum at n = e. This is the precise meaning of "gauge³-invariant" in this row.)

S14 asymmetry (algebraic vs. analytic) = difference in S15 residence (intra-layer vs. inter-layer).

**S13 vs. S17 format shift**: distinct stationary forms but absorbed into the same unified principle ("stationary point of a scalar functional on an Arrow"). S13 = level-set crossing, S17 = derivative extremum; both are equivalent as **mathematical mechanisms identifying canonical constants**.

**Bidirectional duality 3/3 completion** (`c_arrow_bridge_constants.md §2`): Arrow 1 → π / Arrow 2 → ln 2 / **Arrow 3 → e**. A canonical constant resides on each of the three Arrows, completing the constant-level picture. NT-internal verification: continuous argmax ≈ e, codebook integer argmax = 3 (5/5 gate PASS, `oq_omega_obs_3_info_density_check.py`).

#### 4.5.1 Observation-optimal gauge theorem — NT-internal contrast

(Note: the term "**Path 2**" used in this §4.5.1 and below refers to the gauge-forced coincidence path classified by Theorem 4.1a / Corollary 4.1b — the path along which Information-layer balance and Structural-layer balance coincide under the same gauge through a domain-internal structural enforcement. The full definition of the Path 2 class as a Z/2 involution-fixed-point class is given in N3 §1.1.)

**Theorem 4.1a** [v0.6 ESTABLISHED, `c_observation_optimal_gauge.md §2`]: the gauge structure under which Arrow 1⁻¹ most precisely recovers a Structural target separates into two layers:

- **Information layer** (D_floor minimum, etc.): optimised at the **S13 half-value fixed point (ln 2 / α̅ = 0.5 / s = 1/2)** on Arrow 2.
- **Structural layer** (carry rate, χ median, etc.): balance determined by domain-specific arithmetic on Arrow 1.
- **Coincidence of the two-layer balances** depends on **enforcement by a functional equation** (functional-equation-style structural enforcement).

**Corollary 4.1b**: the two layers coincide only when functional-equation-style enforcement exists.

**NT-internal 2-instance contrast** (this paper: contrast only; structural analysis in N2):

| Domain | Gauge | Information balance | Structural balance | Match | Cause |
|---|---|---|---|---|---|
| **NT (Paper C)** | s | s = 1/2 (D_floor min) | s = 1/2 (RH zeros) | **coincide** | ζ functional eq |
| **NT carry bridge** | X (conductor) | X = 6 (g=2 min) | X = 2g (15 gaps locus) | **split** | enforcement absent |

**Status**: ESTABLISHED 2026-04-22. 3/3 Path 1-4 achievement via NT 2-instance + multi-domain 1-instance. **N2 forward**: structural analysis (each factor of D_floor parabolic formula, Euler product of carry rate, structural prohibition of residue exclusivity) is deferred to N2.

### 4.6 Inverse Arrows and obstruction class

Each Arrow has a partial inverse (section, right inverse modulo kernel) — the **inverse Arrow**. Composition coincides with the operation called "generation" (`c_arrow_obstruction.md §11`).

**Claim 4.2 (generation invertibility theorem)**: the three S15 layers are exhaustive. "Generation" is not a fourth layer but a composition of inverse Arrows. Each kernel is fully described by T-AAS spanning.

| Inverse Arrow | Domain → Codomain | Source of obstruction | NT instance |
|---|---|---|---|
| Arrow 1⁻¹ | Structural → Scan | ker_gauge ⊕ ker_topo (T-AAS) | (h_K, R_K, w_K, d_K) → ζ_K(s) reconstruction; existence problem of Stark unit ε_χ |
| Arrow 2⁻¹ | Information → Scan | non-invertibility of log | Λ(n) → ζ(s) lift; analytic-continuation obstruction |
| Arrow 3⁻¹ | Information → Structural | Jensen's inequality | log h_K → h_K cardinality lift |

**Corollary 4.3**: ker_topo ≠ 0 holds in general (Hodge candidate = NT-adjacent open) → perfect generation is impossible in principle.

**Obstruction class — NT taxonomy**: in this paper's NT scope only the two classical classes are retained (the multi-domain Attractor / Noise-residue / Stochastic basin of Paper D are excluded as non-NT in origin):

| Class | NT instance | T-AAS position |
|---|---|---|
| **ker_gauge classical** | Stark torsion (root-of-unity), Dirichlet character sign | f_torsion |
| **ker_topo classical** | Brauer Tier ∞, Hodge filtration (NT-adjacent open) | f_rational |

---

## §5 T-AAS — Algebra-Analysis Surjectivity Template (NT instances)

### 5.1 Main theorem

**Theorem 5.1 (T-AAS, ESTABLISHED 2026-04-12, 15/15 fitness)** — when Arrow 1 (φ: Structural → Scan) has non-trivial kernel:

- **(i)** ker(φ) = ker_gauge ⊕ ker_topo (direct sum)
- **(ii)** ker_gauge is generated by a discrete (torsion-valued) invariant δ ∈ Finite_Group, removable by gauge transformation (irreversible information loss)
- **(iii)** ker_topo is a multi-step filtration obstruction, irremovable in any gauge
- **(iv)** conductor splits: $f(\varphi) = f_{\text{torsion}} + f_{\text{rational}}$, $f_{\text{torsion}}(\varphi) = \dim\{\ker_{\text{gauge}}\}$, $f_{\text{rational}}(\varphi) = \dim\{\ker_{\text{topo}}^{\text{non-surj}} \cap \text{target}\}$

### 5.2 NT instance verification (3 + 1 open)

**NT scope of this paper**: Stark / Brauer / OQ-P2-3. Crystal in the multi-domain Paper D version is excluded; Hodge is the open frontier.

| Instance | ker_gauge | ker_topo | f_torsion | f_rational | Status |
|---|---|---|---|---|---|
| **Stark rank 0/1** | ν(ρ) sign, w_K root-of-unity | multi-field L-ratio impossibility | f_sign, w_K | f_field (Tier 1/2/3+) | rank 0 ESTABLISHED, rank 1 abelian 3 cases verified |
| **Brauer 5-tier** | Galois rep dim torsion (FS ν(ρ)) | C1-C4 closure failure | Tier-specific | Tier-specific | failure taxonomy v0.2 (Q_8 numerical witness) |
| **OQ-P2-3 Dirichlet** | χ₁ Legendre structural zero | χ₀ principal indicator | 0 | ≥1 (χ₀ class 0 = 6\|g) | CLOSED NEGATIVE (Paper C §4) |
| **Hodge (NT-adjacent open)** | Sq³, H³_nr torsion | Griffiths transversality | f_torsion(X, p) | f_rational(X, p) | **OPEN**, §5.4 |

3 NT instances + 1 open frontier → reconfirms **12/12 NT-relevant fitness** out of the 15/15 fitness of the multi-domain Paper D version.

#### Fitness witness summary (full development in §6)

Each instance's numerical / group-theoretic witness in 1-2 lines, so §5 stands self-sufficient as a fitness-verification section (full development and Arrow-primary interpretation are in §6 triangulation):

- **Stark rank 0/1** — Class number formula verified numerically across 5 number fields (ℚ, ℚ(i), ℚ(√2), ℚ(√5), ℚ(√−5)) (`number_theory_dictionary v1 §5`). Rank 1 abelian Stark fully expressed in Atlas grammar across 3 cases (ℚ(√5) χ_5 real, ℚ(√2) χ_8 real, ℚ(√−23) cubic class character non-real, S_3 setup, h=3) with Δ_residual = 0 exact. f_torsion = 0, f_rational ∈ ℤ_{>0} (Tier 1 strict).

- **Brauer 5-tier** — Q_8 Tier √ numerical witness (LMFDB 8.0.12230590464.1): $L(0, \rho)^2 = 16$ (rational), $L(0, \rho) = \pm 4$ (sign obstruction). 2-dim irreducible ρ is **quaternionic** (FS ν(ρ) = −1) and the sign leaks outside the square root. Conjecture v0: a rank-1 abelian Stark setup of G falls into **exactly one** of {Tier 1, 2, 3+, √, ∞} (fully parameterised by representation-theoretic invariants).

- **OQ-P2-3 Dirichlet** — Permutation test (N = 30M, k_max = 150, 19 gaps): χ₁ Legendre projection **p = 0.87 (z = −1.05)** with no signal (structurally forbidden by residue mirror symmetry); χ₀ principal-indicator projection **p = 0.014 (z = +2.62)** with class 0 (6\|g) D_floor at roughly half of class 1, 2 (floor ≈ 0.0049 vs. 0.0100). Clean instance with f_torsion = 0, f_rational = 1 (CLOSED NEGATIVE 2026-04-22, Paper C §4).

The three instances each carry a different fitness modality: Stark = **gauge product perfectness** (Δ_residual = 0 exact, 3 cases ESTABLISHED), Brauer = **group-theoretic parameterisation** (5-tier conjecture + Q_8 numerical witness), OQ-P2-3 = **structural prohibition** (binary separation of permutation null + indicator signal). The independence of the three modalities is the closure ground of the §6 Arrow-level triangulation (§6.4 obstruction level).

### 5.3 Gauge-wall structure

**(HC-1e, 2026-04-12)**: all known obstructions sit not between gauge wall 1 (ℤ → ℚ) and gauge wall 2 (ℚ → ℝ); they all belong to **f_torsion** (vanish under Q-gauge).

- Tier √ = R-gauge obstruction = f_torsion > 0, f_rational = 0 (vanishes at Patterson)
- Tier 2 = R-topo-surj obstruction = f_torsion = 0, f_rational > 0 (gauge invariant)

**ΣΦ translation of Hodge conjecture** (§5.4): f_rational(X, p) = 0 for all smooth projective X and all p. A ℚ-rational counter-example is equivalent to discovery of a "third wall" in T-AAS.

### 5.4 Hodge conjecture — NT-adjacent open frontier

The Hodge conjecture (algebraic geometry) is strictly speaking not number theory, but as **the existence problem of f_rational > 0 among the four T-AAS instances** it is NT-adjacent open. In this paper:

- **f_rational > 0 candidate**: ker_topo (Griffiths transversality) may fail to vanish for some smooth projective X and p. The Hodge conjecture is equivalent to "f_rational(X, p) = 0 for all (X, p)".
- **Out of scope**: explicit Hodge cycle constructions, p-adic Hodge, motivic framework details.
- **Role in this paper**: anchor showing that §5 T-AAS is a **framework with an open frontier**.

The structure "T-AAS with **12/12 fitness verified across 3 NT instances** + **Hodge candidate open**" guarantees the predictive power of the framework (Hodge ESTABLISHED → empirical f_rational > 0 / refute → suggestion of universal closure).

---

## §6 NT-internal triangulation — Arrow-level triangulation

Three NT instances cover the **three Arrows of S15 with different primary responsibilities**, triangulating universality. Whereas the multi-domain Paper D performs "domain-level triangulation" (NT vs. FX vs. constants), this paper adopts "**Arrow-level triangulation**" (Arrow 1 kernel vs. Arrows 2-3 vs. three-Arrows-simultaneous).

### 6.1 Paper C: three-layer decomposition = S15 isomorphism

Correspondence in Paper C §5:

| Paper C three-layer | Mathematical content | S15 layer | Arrow |
|---|---|---|---|
| κ_g · G_k(s) · W_k(ω) | PNT main term × gauge window | **Scan** | 1 (input spec) |
| a_g · Δ_k(s) | ζ-zero oscillation component | **Structural** | 2 (zero geometry) |
| ε_{g,k}(N) | mod-6 arithmetic residual | **Information** | 3 (Hartley type) |

**gauge-invariance**: κ_g is fully independent of M ∈ {13, 1979, 1981, 49999} ⇒ Arrow 2 invariant.
```
κ_2(s = 1, k = 0) = 0.299512 (fully M-independent)
```
Numerically consistent with the Hardy-Littlewood twin constant C₂ = 1.3203… via $\kappa_2 \approx 2C_2/\int_2^N dt/\log^2 t \cdot 1/\pi(N)$.

**D_floor spectrum** (Paper C §3.1-3.4): the parabolic formula D_floor(s, N) ∼ N^{−2/3} · exp(0.216·(log N)²·Δs²) provides **quantitative control** of the Arrow 1 kernel along the Scan axis. The minimum at s = 1/2 directly exposes the **internal structure of Arrow 1 kernel (ker_topo)** via dip-locking onto the ζ-zero γ₁.

**Primary Arrow**: **all three Arrows** (S15 isomorphism in a single object F_{g,k}(s)). Details: N2.

### 6.2 Stark projection: 6-gauge decomposition

Class number formula (rank 0):
```
Res_{s=1} ζ_K(s) = (2^{r₁} · (2π)^{r₂} · h_K · R_K) / (w_K · √|d_K|)
```

The 6 factors correspond 1:1 to all gauge² signatures in Paper Ω (`stark_projection_v0.md §2.1`):

| Factor | Identity | gauge² signature |
|---|---|---|
| (2π)^{r₂} | archimedean volume of complex places | {cont, geom} (π) |
| 2^{r₁} | archimedean volume of real places | {addZ} (parity minimum) |
| √\|d_K\| | Minkowski co-volume of O_K | {mult, anal} |
| h_K | order of ideal class group | {mult} |
| R_K | co-volume of log-unit lattice | {cont, char} |
| w_K | number of roots of unity in K | {char} |

**The class number formula collects the origination structure into a single equation** — a **product-decomposition theorem** of gauge².

**Atlas grammar representation** (rank 1 Stark):
```yaml
stark_rank1_entry:
  f_n:           log |σ(ε_χ)|          # amplitude (axis A)
  phi_phase:     χ(σ⁻¹)                 # gauge-rotation (axis E)
  N_X:           1/e_χ                   # torsion normalisation
  comp_X:        Σ_{σ ∈ G}              # Galois orbit sum
  observable:    L'(0, χ)                # analytic linear response
  primary_axis:  E
  residual_type: [R-gauge, R-info]
```

The rank-1 Stark conjecture = **complete representation theorem of R-gauge residual**. L'(0, χ) coincides with a character-mode projection on the log-unit lattice with **zero residual** (Δ_residual = 0 exact) — in stark contrast to nearly all dictionary entries (Δ > 0).

**Primary Arrow**: **Arrows 2/3** (analytic scan ζ_K(s=1) → algebraic gauge product). **N4 forward**: coupling with Brauer 5-tier, connection with Hasse-Weil, rank ≥ 2 regulator are deferred to N4. This paper restricts to **Stark as a vertex of triangulation**.

### 6.3 Brauer closure: 5-tier failure taxonomy

5-tier of `brauer_closure_failure_taxonomy_v0.md` v0.2:

| Tier | Form | Examples | Stark formula |
|---|---|---|---|
| **Tier 1** | $L = \zeta_F/\zeta_\mathbb{Q}$ | $S_3$, $A_4/V_4$ | single reg $h_F R_F$ |
| **Tier 2** | $L = \zeta_{F_1}/\zeta_{F_2}$ | $D_4$ | reg ratio |
| **Tier 3+** | $L = \prod \zeta_{F_i}^{n_i}$ | $S_4/V_4$ ? | multi-reg rational |
| **Tier √** | $L^{2k} = \text{rational}$, $L \notin$ | $Q_8$ | square-root of rational |
| **Tier ∞** | no power works | (genuinely unknown) | direct Hecke L only |

**Q_8 Tier √ numerical witness** (LMFDB 8.0.12230590464.1): $L(0, \rho)^2 = 16$, $L(0, \rho) = \pm 4$ (sign obstruction); 2-dim irreducible ρ is **quaternionic** (FS ν = −1) — the sign leaks outside the square root.

**4 failure axes**: classification by where the C1-C4 closure conditions of OQ-NT-7 break (A: real irrep / B: induction irreducible / C: zeta ratio reduction / D: unit lattice closure).

**Conjecture (v0)**: a rank-1 abelian Stark setup of a finite Galois group G must fall into **exactly one** of {Tier 1, 2, 3, …, √, ∞}. The tier is determined entirely by representation-theoretic structure of G (irrep dimensions, FS indicators, subgroup lattice, character inner products). This is a strong claim that the T-AAS Arrow 1 kernel decomposition is **fully parameterised by group-theoretic invariants**.

**Primary Arrow**: **Arrow 1 kernel** (group-theoretic indexing of T-AAS decomposition). **N5 forward**: alternative Stark methods for failure modes, numerical verification of Tier √ examples beyond Q_8, negative cases (OQ-NT-8) are deferred to N5.

### 6.4 Closure of Arrow-level triangulation

The three NT instances cover the three S15 layers and three Arrows with **mutually distinct primary responsibility**:

| Instance | Scan | Structural | Information | Arrow focus |
|---|---|---|---|---|
| **6.1 Paper C** | F_{g,k}, G_k | a_g·Δ_k (ζ-zero oscillation) | ε_{g,k} (mod-6 residual) | **all three Arrows** (S15 isomorphism in single object) |
| **6.2 Stark** | ζ_K(s=1 pole) | h_K, R_K, d_K, w_K, r₁, r₂ | log h_K, log R_K | **Arrows 2/3** (analytic → algebraic) |
| **6.3 Brauer** | L(s, ρ) (rank-1 abelian) | Tier classification (Galois rep) | f_torsion vs. f_rational kernel dim | **Arrow 1 kernel** (T-AAS decomposition) |

**Closure claims**:
- **Layer level**: each layer covered by ≥ 2 instances → coincidence by a single instance excluded.
- **Arrow level**: three instances have different primary Arrows → the entire S15 Arrow structure is independently verified (Arrow 1 kernel ⇐ Brauer / Arrows 2-3 ⇐ Stark / three-Arrows-simultaneous ⇐ Paper C).
- **Obstruction level**: Paper C analytic residual (D_floor parabolic = quantitative control of ker_topo) / Stark gauge-product perfectness (Δ_residual = 0 = special case rank 0/1 abelian where both ker vanish) / Brauer kernel (Tier classification = ker_topo group-theoretic parameterisation).

**Perspective shift (domain-level → Arrow-level)**: same triangulation discipline (3 vertices required, each independent, common meta-structure exposed) is preserved while changing the basis of vertex independence from Paper D's "domain independence" to this paper's "Arrow independence". The two are essentially equivalent, but this paper has the advantage of **NT-internal self-closure**, providing N1-N5 framework header with a triangulation that requires no out-of-domain instance.

None of the three NT instances presupposes the other two for exposing S15 — this independence is the evidence of NT-internal universality.

---

## §7 Six-step protocol for new NT domains

Procedure for new NT domains (new number field K, new Galois representation class, new L-function family) (`meta/new_domain_protocol.md`):

| Step | Content |
|---|---|
| **0** | Identify §4 dual projection — additive (periodicity / lattice / group addition), multiplicative (product / decomposition / exponential decay), Bridge (ℂ as receiver) |
| **1** | Identify Scan observable — can an exp kernel be written? additive/multiplicative scan? S12 6+1 member correspondence? |
| **2** | Identify Structural observable — parameter-free integer/topological invariants; dimension, order, rank of D |
| **3** | Identify Information observable — log-derivative chain (−L'/L → Λ_χ), Hartley log\|D\| |
| **4** | Verify three Arrows — Arrow 1 (does (D, f) encode Structural?), Arrow 2 (is −∂_s log Scan = Info?), Arrow 3 (does Scan degenerate to log\|D\| at extreme limit?) |
| **5** | Confirm T-AAS decomposition — ker_gauge ⊕ ker_topo? conductor f_torsion + f_rational? Stark/Brauer/OQ-P2-3 fitness? |
| **6** | Determine dictionary residence — residence within the six L1 NT entries, propose a new entry if needed, append to L2 case log |

**Verified applications**: numerical class number formula across 5 fields (ℚ, ℚ(i), ℚ(√2), ℚ(√5), ℚ(√−5)) in number_theory_dictionary v1 §5; rank-1 abelian Stark in Atlas grammar for 3 cases (ℚ(√5), ℚ(√2), ℚ(√−23)) completed.

**5 next candidates**: ℚ(ζ_5), ℚ(ζ_7), ℚ(√−23) extensions, ℚ(√−163), 9 Bianchi cases.

---

## §8 Consequences and open frontier

### 8.1 Established (NT-only restatement)

Recorded as ESTABLISHED within NT in this paper:

1. **S15 Observable Trichotomy** — exhaustivity closed in three steps (instance existence / L1 NT 6-entry enumeration / S12-S14 consistency) (§3.5)
2. **Arrow structure (3) and commutativity** — commutativity verified at three NT instances (β→0, s→∞, s=1 pole) (§4.4)
3. **T-AAS decomposition (3 NT instances + 1 open)** — 12/12 NT-relevant fitness via Stark/Brauer/OQ-P2-3, Hodge open (§5.2)
4. **NT-internal Arrow-level triangulation** — three instances with different primary Arrows; no out-of-domain instance required (§6.4)
5. **NT-internal residence of S13/S17** — π/ln 2/e as canonical constants on three Arrows; complete on the three-Arrow base (§4.5)
6. **Observation-optimal gauge theorem (NT 2-instance contrast)** — Paper C coincide vs. Paper 2 split as statement-only here; structural analysis in N2 (§4.5.1)

### 8.2 N2-N5 forward bridges

| Sequel | Topic | Forward from this paper | Status |
|---|---|---|---|
| **N2** | Paper 2 structural analysis (Carry / D_floor / Dirichlet) | §4.5.1 **structural analysis** of Paper C coincide / Paper 2 split (each factor of D_floor parabolic formula, Euler product of carry rate, structural prohibition of residue exclusivity); §6.1 numerical extension of Paper C three-layer decomposition | **v0.2 drafted 2026-04-26** (`papers/publication/nt/N2_paper2_structural_ja.md`) |
| **N3** | Path 2 number-theoretic universality | §3.2 Dirichlet-L extension of Scan family (Schumann path 2, 5+ instances); §5.2 Dirichlet-L instances of Brauer 5-tier | **v0.2 drafted 2026-04-26** (`papers/publication/nt/N3_path2_dirichlet_universality_ja.md`) |
| **N4** | Hasse-Weil L × Stark structure | §5.2.1 Galois-rep-side structure of Stark rank 0/1; §6.2 extension of Stark 6-gauge to Hasse-Weil conductor universality; coupling with Brauer 5-tier | **v0.2 drafted 2026-04-26** (`papers/publication/nt/N4_hasseweil_stark_ja.md`) — **K_E(t)·t² → r BSD analytic-rank detection (genuine framework predictive content) confirmed**; weight-class-dependent transfer pattern established by contrast against N3 Dirichlet L "structural fit only" |
| **N5** | Brauer obstruction theory + Origination matrix (8-gauge) | §5.2.2 detailed Brauer 5-tier failure modes + alternative Stark methods; §6.2 generalisation of 6-gauge decomposition to **Origination matrix 8-gauge** (gauge²) | **v0.2 drafted 2026-04-27** (`papers/publication/nt/N5_brauer_origination_ja.md`) — **NT-series 5-paper final closure achieved**: Brauer 5-tier failure-mode group-theoretic conjecture + Tier-dependent Stark methods + 8-gauge generalisation + cross-connection (Tier ↔ T-AAS / 8-gauge ↔ Type α/β/γ) + 4-vertex triangulation proposal_v2 + Q1-Q3 forward |

**8-gauge forward (N5)**: this paper makes gauge² explicit in §1.3 and minimally references §6.2 Stark 6-gauge as the **constants origination axis-1 D/C subdivision**. The full structure of the Origination matrix 8-gauge family (axis-1 D 5-family + axis-1 C 3-family) and the **8-constant (π, e, ζ, γ, τ, i_add, i_mult, Φ) origination-field analysis** are deferred to N5.

### 8.3 Open frontier

| Open question | Status | Related paper |
|---|---|---|
| **Hodge conjecture** (T-AAS f_rational > 0 candidate) | OPEN (= the conjecture itself) | §5.4, N5 |
| **p-adic Stark / Gross-Stark** | out of scope (p-adic vocabulary outside dictionary) | OQ-Ω11 candidate |
| **Higher rank Stark (≥ 2)** | out of scope (transcendence-theoretic territory) | N4 future |
| **Artin's conjecture** (non-abelian L holomorphy) | OPEN (since 1924) | N4 future |
| **OQ-NT-7/8 dual pair** (Brauer 5-tier completeness) | candidate_v1 | §6.3, N5 |
| **OQ-P2-2f** (canonical k_max identification) | OPEN | N2 |
| **OQ-Ω-Schumann** (countably-infinite Path 2) | candidate (5+ instances) | N3 |
| **Hasse-Weil L conductor universality** | candidate_v2 | N4 |

### 8.4 Dictionary residence map

Residence of major framework pieces (reflecting NT-only specialisation + N2 backward link, v0.4 update):

| Piece in this paper | Residence | Status (N1) | N2 backward |
|---|---|---|---|
| §2.1 Axiom 1 (Dual receptacle) | `c_phase_complex.md §4` | existing reuse | — |
| §2.2 Axioms A0-A7 | `finite_observation.md §1-§7` + `observation_canon.md §2` | existing reuse | — |
| §2.4 L0 v1 + L0 v2 | `finite_observation.md §8` + `observation_canon.md §3` | ESTABLISHED 2026-04-23 | — |
| §3 S15 + NT enumeration closure | `c_theorems_master.md` row S15 + NT-only annex of this §3.5 | **annex implemented 2026-04-26** | — |
| §3.2 Scan family (ζ, L(s, χ), modular L series) | `c_theorems_master.md` "Path 2 countably-infinite family" annex (NEW) + `nt_dedekind_artin_zeta.md §7` (modular L countably-infinite annex) | ζ-only existing / extension required | **N3 §3 establishes countably-infinite → annex implemented (2026-04-26)** |
| §3.3 Structural ω(X) entry | `nt_conductor.md §6.10` (NT carry conductor) | existing reuse | **§6.10 NT carry conductor implemented (N2 §2 transfer, 2026-04-26)** |
| §4 three-Arrow framework | `c_arrow_framework.md` | new L1 entry 2026-04-23 | — |
| §4.4 Arrow commutativity (3 NT instances) | `c_arrow_framework.md §4.2.1` + this §4.4 | **§4.2.1 NT instance implemented 2026-04-26** | — |
| §4.5 / §4.5.0 S13/S14/S17 residence | `c_arrow_bridge_constants.md §5-§6` + **§11 Fi-origin vs. I-origin annex** (NEW) | existing (S17 ESTABLISHED 2026-04-23) | **§11 Fi-origin vs. I-origin canonical scalar dichotomy implemented (N3 §5.3 transfer, 2026-04-26)** |
| §4.5.1 Observation-optimal gauge | `c_observation_optimal_gauge.md §2-§5` + §5.5 expansion | existing (v0.6 ESTABLISHED) | **§5.5 Path 3 arithmetic mod-n clause expansion implemented (N2 §6.3 transfer, 2026-04-26)** |
| §4.6 inverse Arrows + obstruction (NT-restricted) | `c_arrow_obstruction.md §11` (NT subset) | existing + this paper's NT-scope filter | — |
| §5 T-AAS (NT instances) | `c_arrow_obstruction.md §10` (NT subset) | existing | — |
| §5.2 OQ-P2-3 instance | `c_filtration_obstruction.md` (T-AAS f_rational instance) + this §5.2 | existing | structural analysis expanded in N2 §4 |
| §5.4 Hodge (NT-adjacent open) | `c_filtration_obstruction.md` | existing (open) | — |
| §6 NT-internal triangulation (Arrow-level) | **NEW** `meta/triangulation_methodology.md §9` NT-internal annex | **§9 implemented 2026-04-26** | "three Arrows simultaneous in single object" deep dive in N2 §5.4 |
| §7 6-step protocol (NT specialisation) | `meta/new_domain_protocol.md §8` NT specialisation annex | **§8 implemented 2026-04-26** | — |
| (from N3, Path 2 family) | **NEW** `c_theorems_master.md` "Path 2 countably-infinite family" annex + "Dirichlet L extension scope" annex | — | **N3 §3 + §4 transfer implemented (2026-04-26)** |
| (from N3, D_floor multi-gap fragment) | `c_recursive_floor_principle.md §6.8.1` (Dirichlet L gap-class universality (12/12 PASS) fragment) | existing §6.8 D_floor ζ-family core | **§6.8.1 Dirichlet L extension implemented (N3 §4.6 transfer, 2026-04-26)** |
| (from N3, OQ issues) | `meta/open_questions_master.md` "Path 2 NT universality OQ" section (NEW) | — | **5 OQ issued (Schumann-v1.5 / HeckeArtin-Ext / HasseWeil-Ext / IOriginFormal / DfloorLProperAnalog), 2026-04-26** |
| (from N4, Hasse-Weil L extension) | **NEW** `c_theorems_master.md` "Hasse-Weil L extension scope" annex + `c_recursive_floor_principle.md §6.8.2` Hasse-Weil L extension (BSD K·t²→r) | — | **N4 §3 transfer implemented (2026-04-26)** |
| (from N4, 4-vertex triangulation) | `meta/triangulation_methodology.md §10` 4-vertex proposal annex | existing §9 reuse + extension | **N4 §6.3 transfer implemented (2026-04-26, proposal_v1)** |
| (from N4, OQ updates) | `meta/open_questions_master.md` Path 2 OQ section update | — | **OQ-Schumann-HasseWeil-Ext PARTIAL_RESOLVED + 3 spawn (OQ-BSD-HigherRank / OQ-433a1-Outlier / OQ-4VertexClosure), 2026-04-26** |

**N2 backward link legend**:
- "structural analysis expanded in N2 §x": location where Paper N2 fully expands the statement-only part of this paper
- "**§x implemented (N2 §y transfer)**": annex where the N2 result was written back directly to the dictionary
- "—": unrelated to N2 directly (handled in N3/N4/N5 or already self-contained in existing content)

**N2 v0.2 (2026-04-26) backward statistics**: N2 implements 4 forward expansions; **2 of them written back as new dictionary annexes** (`nt_conductor.md §6.10` + `c_observation_optimal_gauge.md §5.5`). The remaining 2 (`§4.5.1 structural analysis expansion` + `§6.1 single-object three-Arrow simultaneous`) are self-contained in N2's structural analysis and require no additional dictionary annex.

**N4 v0.2 (2026-04-26) backward statistics**: N4 drafting produced **4 dictionary write-backs**:
- `c_theorems_master.md` "Hasse-Weil L extension scope" annex (BSD K·t²→r 9/10 + Path 2 weight-2 family member)
- `c_recursive_floor_principle.md §6.8.2` Hasse-Weil L extension annex (weight-class-dependent transfer pattern over the 5 components of the D_floor formula)
- `meta/triangulation_methodology.md §10` 4-vertex proposal annex (Hasse-Weil 4th-vertex extension, proposal_v1)
- `meta/open_questions_master.md` OQ-Schumann-HasseWeil-Ext **PARTIAL_RESOLVED** + 3 spawn-off OQ (OQ-BSD-HigherRank / OQ-433a1-Outlier / OQ-4VertexClosure)

Feature of N4 backward: **the positive result that Hasse-Weil L transfers genuine framework predictive content** caused a shock wave across the dictionary, recording the **weight-class-dependent transfer pattern** as a dictionary-wide annex by contrast with §6.8.1 Dirichlet L "structural fit only".

**N3 v0.2 (2026-04-26) backward statistics**: N3 implements 5 forward expansions, **all 5 written back as new dictionary annexes / OQ sections**:
- `c_theorems_master.md` "Path 2 countably-infinite family" annex (Schumann v1 5-instance + Type α/β/γ + axis-2 invariance)
- `c_theorems_master.md` "Dirichlet L extension scope" annex (T-Ω5e-v15-* rows summary + SC4 + scope partition)
- `nt_dedekind_artin_zeta.md §7` (modular L countably-infinite Path 2 annex)
- `c_recursive_floor_principle.md §6.8.1` (Dirichlet L gap-class universality (12/12 PASS) fragment)
- `c_arrow_bridge_constants.md §11` (Fi-origin vs. I-origin canonical scalar dichotomy)
- `meta/open_questions_master.md` "Path 2 NT universality OQ" section (5 OQ issued)

Unlike N2, N3 backward is **all-write-back** (the Path 2 family has touchpoints across all L1 / meta layers).

**Consequence**: this paper is positioned as the **NT-internal framework header** of the dictionary; theorems / definitions formally reside in L0 / L1 / meta entries. Drafting N2 + N3 completes and extends the **3-layer link**: framework header → result paper → dictionary backward. N4-N5 presuppose this residence map + N2/N3 backward pattern.

---

## Change log

- **v0.7 (2026-04-27)**: N5 backward link + reflection of **NT-series 5-paper completion**. N5 v0.2 drafted (2026-04-27) reflected as "NT-series 5-paper final closure achieved" in the §8.2 forward bridge table status column. N5-derived dictionary updates: `meta/triangulation_methodology.md §10` proposal_v1 → proposal_v2 (formal attempt at Hasse-Weil 4-vertex closure) + `meta/open_questions_master.md` "NT-series final closure OQ" section newly created (OQ-NT-6 + OQ-Tier3-Plus-Search + OQ-Tier-Sqrt-Resolution). NT framework total reaches complete closure with touchpoints across all L0/L1/L2/Meta layers.
- **v0.6 (2026-04-26)**: N4 backward link added. N4 v0.2 drafted (2026-04-26) reflected as "K_E·t²→r BSD analytic-rank detection genuine framework content confirmed" in the §8.2 forward bridge status column. 3 N4-derived annex rows added to §8.4 residence map (`c_theorems_master.md` Hasse-Weil L extension scope + `c_recursive_floor_principle.md §6.8.2` + `meta/triangulation_methodology.md §10`) + OQ updates (Schumann-HasseWeil-Ext PARTIAL_RESOLVED + 3 spawn). Feature of N4 backward: weight-class-dependent transfer pattern recorded dictionary-wide as shock wave (Dirichlet L "structural fit only" vs. Hasse-Weil L "genuine BSD").
- **v0.5 (2026-04-26)**: N3 backward link added. N3 v0.2 drafted (2026-04-26) reflected in §8.2 forward bridge status column. 5 N3-derived annex rows added to §8.4 residence map (`c_theorems_master.md` Path 2 + Dirichlet L extension scope / `nt_dedekind_artin_zeta.md §7` modular L / `c_recursive_floor_principle.md §6.8.1` gap universality / `c_arrow_bridge_constants.md §11` Fi-origin vs. I-origin / `meta/open_questions_master.md` 5 OQ issues). N3 backward is **all-write-back**, a different pattern from N2 (Path 2 family has touchpoints across all L1 / meta layers).
- **v0.4 (2026-04-26)**: N2 backward link added. N2 v0.2 drafted (2026-04-26) reflected in §8.2 forward bridge status column. N2 backward column added to §8.4 residence map, making explicit the 2 annexes N2 wrote back to the dictionary (`nt_conductor.md §6.10` NT carry conductor / `c_observation_optimal_gauge.md §5.5` Path 3 arithmetic mod-n expansion). Completed the 3-layer link: framework header → result paper → dictionary backward.
- **v0.3 (2026-04-26)**: §5 fitness witness added. After v0.2 compressed §5.2 to a table only, §5 alone looked thin; remedy by appending 1-2 line numerical / group-theoretic witnesses for each of 3 instances after the §5.2 table. Division of labour between §5 (= fitness verification) and §6 (= triangulation vertex) preserved while making §5 self-sufficient.
- **v0.2 (2026-04-26)**: compact version. Reduced redundancy from v0.1 (965 lines) — Abstract compressed, "feature" sub-sections of each §3 layer removed, §4.4 NT instances tabularised, §4.5/§4.5.0 consolidated, §4.6.1 obstruction taxonomy compressed, §5.2 instances reduced to a table only with detail removed (functionally redundant with §6), §6.4 three sub-sections merged. Structure as N1-N5 framework header preserved.
- **v0.1 (2026-04-26)**: initial NT-only draft. NT specialisation derived from Paper D v0.9.2 (multi-domain frozen-internal). Rebuilt via Arrow-level triangulation by 3 NT instances (Paper C / Stark / Brauer).

---

## References (internal)

**Paper D series (predecessor)**: `papers/Paper_D_Observation_Theory_ja.md` (v0.9.2 frozen-internal, 2026-04-25, multi-domain)

**Sources of results developed in this paper**:
- `papers/Paper_C_NT_Quantum_ja.md` (v0.2) — §6.1 Paper C three-layer decomposition
- `research/paper2_twin_dictionary_bridge_v1.md` — Paper 2 carry bridge (§4.5.1 split instance)
- `research/oq_p2_1_carry_closed_form.md` — OQ-P2-1 RESOLVED
- `research/oq_p2_2_sstar_asymptotic.md` — OQ-P2-2 4th iteration
- `research/stark_projection_v0.md` — §6.2 Stark
- `research/brauer_closure_failure_taxonomy_v0.md` (v0.2) — §6.3 Brauer 5-tier
- `research/brauer_closure_galois_classification_v0.md` — OQ-NT-7
- `research/oq_l0_refinement_finite_infinite_2axis_v0.md` — §2.4 L0 v2
- `research/bidirectional_duality_v0.md` — §2.3 §4 dual root

**L0 / L1 / meta dependencies**: `dictionaries/L0_canon/{observation_canon, finite_observation, identity_asymmetry}.md` / `L1_mathematical/core/{c_phase_complex §4, c_theorems_master, c_arrow_framework, c_arrow_obstruction §10-§11, c_arrow_bridge_constants, c_filtration_obstruction, c_observation_optimal_gauge, c_spectral §8}.md` / `L1_mathematical/number_theory/{nt_conductor, nt_dedekind_artin_zeta, nt_frobenius_schur, nt_genus_class_fields, nt_relative_units, nt_root_numbers}.md` / `L2_domain/number_theory_dictionary_v1.md` / `meta/{triangulation_methodology, new_domain_protocol}.md`

**Sequel papers**: N2 (Paper 2 structural analysis) / N3 (Path 2 NT universality) / N4 (Hasse-Weil L × Stark) / N5 (Brauer obstruction theory + Origination matrix) — drafting planned
