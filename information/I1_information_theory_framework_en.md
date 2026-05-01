# Paper I1: Observation Theory — Information Edition + Mathematical Information Limit Theorem

**Subtitle**: 0/1/2 scaffold lens, Information-layer internal taxonomy, 5-anchor information limit theorem, I1 ↔ N1 ↔ Q1 triple framework parallel

**Version**: v0.3 (Algorithmic-f_rational ESTABLISHED + Theorem 5.2; Renyi parametric scan ESTABLISHED + Theorem 3.3.1; S17-Codebook docs fix; 2026-04-28)
**Status**: DRAFT — Information-only reformulation of Paper D (multi-domain v0.9.2); parallel 3rd framework header to N1 (NT) / Q1 (quantum)
**Prerequisites (L0)**: `observation_canon.md`, `finite_observation.md` (§1.1 A0, §5.3 A0c, §8 axis-2), `identity_asymmetry.md`
**Prerequisites (L1 core)**: `c_phase_complex.md §4 + §5`, `c_theorems_master.md` (S12-S17), `c_arrow_framework.md`, `c_arrow_obstruction.md §10-§11`, `c_arrow_bridge_constants.md §11 + §12 (5-stage ln 2 chain)`, `c_filtration_obstruction.md §8.5 (4-class quantum lift)`, `c_observation_optimal_gauge.md`, `c_information_theory.md` (main material of this paper, 12 sections)
**Prerequisites (L1 quantum)**: `q_quantum_observation.md §6-§7` (Born / Busch-Gleason / c_s²), `q_open_quantum_systems.md §3` (von Neumann), `q_quantum_statistical_mechanics.md §5` (FDT), `q_quantum_thermodynamics.md §5` (Landauer)
**Prerequisites (transformation_atlas)**: `sheet_A_amplitude/sigma_star.md` (σ\* derivation + EEG entry, ESTABLISHED 2026-04-09)
**Prerequisites (N parallel)**: N1 (`N1_observation_theory_nt_ja.md` v0.7) — NT framework header parallel
**Prerequisites (Q parallel)**: Q1 (`Q1_observation_theory_quantum_ja.md` v0.2) — quantum framework header parallel
**Sequel paper**: I2 (Communication theory: signal theory / quantum communication theory / novel communication theory)

---

## §0 Abstract

Information observables have an **internal taxonomy of the Information layer** within the domain-agnostic three-layer structure **S15 Observable Trichotomy** (Scan / Structural / Information); commutativity of the three Arrows guarantees translation between Shannon / Rényi / von Neumann / Holevo / algorithmic / topological systems. The Arrow 1 kernel decomposes as ker_gauge ⊕ ker_topo via **T-AAS**, with the conductor splitting f_torsion + f_rational.

This paper is the Information-only reformulation of Paper D (multi-domain v0.9.2). Multi-domain triangulation has been stripped, and the structure is rebuilt under the **0/1/2 scaffold lens** — signal theory (0/1 scaffold) ⊂ Shannon (binary 2-domain) ⊂ relational information (3+ structure proper). It has parallel position to N1 (NT, NT-internal Arrow-level 3-vertex) and Q1 (quantum, Arrow 1 kernel narrowness 4-vertex), serving as the **3rd framework header instance** that completes the 3-specialisation coverage of the Paper D 6-domain triangulation.

**Six main results**:

1. **S15 Information layer internal taxonomy** — reconstruct the 12 sections of `c_information_theory.md` (637 lines) (Shannon / mutual info / KL / rate-distortion / IB / Fisher / Bayesian / algorithmic / TDA / L0 translation / Bridges / Open Questions) as sub-taxonomy within the S15 Information layer; the Information layer itself has a 5-strand internal structure (Shannon channel / R-D distortion / IB task / Fisher geometry / Kolmogorov complexity).

2. **Formalisation of 0/1/2 scaffold lens** — load as framework-internal lens the **scaffold-emergence axis** of 0 (pre-observation potential) / 1 (observer-placed reference) / 2 (relational background, signal-theoretic binary 2-domain) / **3+ relational structure proper** (Rényi family / von Neumann / Holevo / 4-class / 5-stage chain). Classical Shannon lies inside 2-domain; quantum Holevo + 4-class refined Hodge initially appear in 3+ structural emergence.

3. **5-anchor mathematical information limit theorem (3-piece structure)** — for any finite observation system (S, W, m), information content jointly satisfies 5 layered constraints: (a) Hartley $H \leq \log d$ (Arrow 3 cardinality bound); (b) S17 info density $H/d \leq 1/e$ (continuous extremum at $d^* = e$, discrete codebook argmax = 3 qutrit); (c) 5-stage ln 2 chain universal natural unit (Born / von Neumann / FDT / Landauer / σ\*); (d) per-class T-AAS 4-class monotone $-\log_2 F_C$ (Theorem 4a.1 unified); (e) σ\* = √(2 ln 2) phase observation gauge threshold. The result is stated in three pieces: **Theorem 6.1 (weak form, ESTABLISHED)** = simultaneous satisfaction of the 5 constraints; **Theorem 6.1′ (independence, ESTABLISHED)** = the 5 constraints are mutually independent (no one is implied by the others); **Conjecture 6.1″ (completeness, OPEN)** = no 6th independent anchor is needed within the current L0 axiomatisation.

4. **Information-internal 3-vertex triangulation (scaffold-emergence axis)** — V₁ Hartley (combinatorial counting **as scanner-free invariant**; Arrow 3 cardinality, S17 e-extremum residence) / V₂ Shannon-Rényi family (analytic continuation **across α-parameter** of an entropy family; Arrow 2 log-exp chain, S13 ln 2 fixed point) / V₃ Resource-theoretic (**resource-stratified beyond a single scalar**; Arrow 1 kernel, T-AAS 4-class refined Hodge): an information-internal **3-vertex triangulation**. Each vertex is independent in structural character (scanner-free vs. parametric-scan vs. stratified), not merely in Arrow assignment. Parallel structure to the N1 NT cross-Arrow 3-vertex, consistent with the 3-vertex floor (3+ relational structure).

5. **I1 ↔ N1 ↔ Q1 triple framework parallel** — independent specialisation of the Paper D 6-domain triangulation by 3 framework headers (NT, quantum, information); achieves **3-domain cross-domain anchor** of framework universal validity. The 0/1/2 scaffold lens is a structural commitment running through all 3 frameworks (signal theory = 0/1 scaffold subset, NT / quantum = 3+ relational structure proper).

6. **Information specialisation of the 6-step protocol for new domains** — implemented as `meta/new_domain_protocol.md §10` (information specialisation, NEW); protocol respecting the Information-layer 5-strand sub-taxonomy + scaffold-emergence axis.

**Thesis**: information observables independently support the entire framework of observation theory (axioms / S15 / Arrow / T-AAS / triangulation) without out-of-domain instances. The **3-domain triple parallel** of the 3 framework headers (N1 NT / Q1 quantum / I1 information) completes the Paper D 6-domain triangulation. This paper functions as the theoretical foundation for I2 (Communication theory: signal theory / quantum communication theory / novel communication theory 5 proposals).

---

## §1 Introduction

### 1.1 Why "information observation theory" + 0/1/2 scaffold lens

The central problem of information theory — what observers with finite resolution can come to know — has been closed since Shannon (1948) with information $H = -\sum p \log p$ as common currency, but the **generative principle** is now in a position to be **motivated by** L0 axiom A0 (finite observation) as its operational origin (`c_information_theory.md §0`); whether full re-derivation is achievable is itself an open question. The ΣΦ dictionary reframes this question as "how does genuine information **emerge** in **3+ relational structure proper**?" and formalises it on the **scaffold-emergence axis**: signal theory (0/1 scaffold base) → Shannon (binary 2-domain) → relational information (3+ proper).

**0/1/2 scaffold framework view (load-bearing structural commitment)**:

| Layer | Phase | Information-theoretic instance |
|---|---|---|
| **0** | pre-observation potential field | $H_0 = 0$ (no info, no signal, no distinction) |
| **1** | observer-placed reference | $H_0(d=1) = \log 1 = 0$ (single reference, vacuous Hartley) |
| **2** | relational background / 2n background field | **signal theory** $H_0(d=2) = \log 2 = 1$ bit (binary distinction baseline, Shannon scaffold) |
| **3+** | relational structure proper | Rényi α-family / von Neumann / Holevo / 4-class refined Hodge / 5-stage ln 2 chain / S17 codebook argmax = 3 |

→ **signal theory lies inside the 0/1/2 scaffold (binary 2-domain), genuine information theory begins at 3+**. S17 codebook integer argmax = 3 (qutrit info-density optimum, `c_arrow_bridge_constants.md §12.1`) is consistent with the **mathematical lower bound of 3+ relational structure proper** (3 = relational structure floor).

**Status**: the 0/1/2 scaffold lens is the user's framework structural commitment, sharing its root with the 3-vertex triangulation discipline (`meta/triangulation_methodology.md §6.1`) (3+ relational structure floor); the load-bearing perspective of this framework header.

### 1.2 N1 / Q1 parallel position + scope

Parallel 3rd framework header position to the NT-series N1 (NT-only restatement) and the quantum-series Q1 (quantum-only restatement):

| Aspect | N1 (NT) | Q1 (quantum) | I1 (information) |
|---|---|---|---|
| Position | NT-internal self-closure | quantum-internal self-closure | information-internal self-closure |
| Organising principle | weight-class (cross-weight 1/2/k) | sparsity (intra-Arrow 1 kernel narrowness) | constraint count (5-anchor independence) |
| Triangulation perspective | Arrow-level 3-vertex (cross-Arrow) | Arrow 1 kernel narrowness 4-vertex (intra-Arrow) | scaffold-emergence axis 3-vertex (Hartley / Shannon-Rényi / Resource-theoretic) |
| 0/1/2 scaffold | NT = 3+ relational (Galois rep / class group / L-functions all d ≥ 3) | quantum = relational structure begins at dim ≥ 2 (qubit minimum); dim=2 itself sits on the scaffold/proper boundary; full proper at dim ≥ 3 | **formal transition between 0/1/2 scaffold ↔ 3+ proper** |
| Framework header role | header of NT specialisation 5-paper series (N1-N5) | header of Quantum specialisation 3-paper series (Q1-Q3) | header of Information specialisation 2-paper series (I1-I2) |
| Forward to | N2-N5 (extension + closure) | Q2-Q3 (extension + closure) | I2 (Communication theory, extension + closure) |

**Structure**: §2 axioms + 0/1/2 scaffold formal / §3 S15 Information layer internal taxonomy / §4 Arrow structure info instances / §5 T-AAS info instances + 4-class lift / §6 5-anchor information limit theorem / §7 protocol info specialisation / §8 consequences + I2 forward + triple parallel.

**In scope**: formal 0/1/2 scaffold lens / S15 Information layer internal taxonomy (12 sub-sections) / 5-anchor information limit theorem (Hartley + S17 + 5-stage ln 2 + 4-class + σ\*) / Information 6-step protocol / I1 ↔ N1 ↔ Q1 triple parallel.

**Out of scope** (deferred): signal theory details + quantum communication theory + novel communication theory 5 proposals (→ I2) / full classical Shannon proofs (`c_information_theory.md §1.2` existing) / Bayesian decision theory details (`c_information_theory.md §7` existing) / TDA / persistent homology details (`c_information_theory.md §9` existing) / algorithmic info theory (Kolmogorov) computational details (`c_information_theory.md §8` existing) / quantum cryptography / QKD protocols (→ I2) / quantum gravity / string theory / category-theoretic information flow.

### 1.3 Terminology

Inherits the 3 uses of "gauge" (gauge¹/gauge²/gauge³) from Q1 §1.3 + Q2 §1.4 + Q3 §1.3. Additional terms specific to this paper:

- **Scaffold-emergence axis**: transition axis from 0/1/2 scaffold (signal-theoretic base) to 3+ relational structure proper (genuine information) (formal load of `user_012_non_integer_scaffold.md`)
- **5-anchor information limit**: information content upper bound quantified by 5 independent constraints (Hartley + S17 + 5-stage ln 2 + 4-class + σ\*)
- **Information-internal triangulation**: V₁ Hartley (Arrow 3) / V₂ Shannon-Rényi (Arrow 2) / V₃ Resource-theoretic (Arrow 1) **3-vertex scaffold-emergence axis** triangulation
- **Resource-theoretic information**: resource-stratified information quantified by the T-AAS 4-class refined Hodge (Q1 §5) (M_F magic / 𝓝 Wigner negativity / Nielsen complexity / Δ_CHSH nonlocal capacity)
- **5-strand info-theory taxonomy** (`c_information_theory.md §0`): internal sub-taxonomy across Shannon channel / Rate-Distortion / Information Bottleneck / Fisher Geometry / Algorithmic complexity 5 strands
- **Triple framework anchor**: I1 ↔ N1 ↔ Q1 = cross-domain validation by the 3 framework headers NT / quantum / information

### 1.4 Direction-axis position (Information framework = A/B native co-residence via Hartley/Shannon split)

Under the A/B observation direction axis of `user_observation_direction_axis` (ESTABLISHED 2026-05-01), this paper's Information framework occupies the special position of **A-native and B-native co-residence** (in contrast to N1 = A-primary, Q1 = B-primary; the I framework anchors both sides).

**Hartley vs Shannon split** (consistent with `feedback_capacity_hartley_vs_shannon` ESTABLISHED):

| Anchor (5-anchor 1-5) | Direction | Observation mode | Native instance |
|---|---|---|---|
| **(a) Hartley $H \leq \log d$** | **A-native** | finite cardinality count → upper-bound extrapolation | finite alphabet $|\mathcal{X}| = d$ Arrow 3 cardinality bound |
| **(b) S17 info density $H/d \leq 1/e$** | **B-native** | continuous extremum at $d^* = e$, infinite distribution → optimum projection | Hartley density continuous regime + qutrit discrete codebook argmax |
| **(c) 5-stage ln 2 chain (Born / vN / FDT / Landauer / σ\*)** | **B-native (Shannon-line)** | continuous ensemble entropy / thermal limit / phase channel = all B-direction native | S13 ln 2 fixed-point chain |
| **(d) T-AAS 4-class $-\log_2 F_C$** | **B-native** | resource-theoretic infinite class → finite per-class monotone projection | 4-class infidelity unified base |
| **(e) σ\* = √(2 ln 2) phase gauge** | **B-native** | continuous ensemble Shannon entropy ½-bit threshold | I2 §4 P1 σ\*-channel |

**Key observation**: among the 5 anchors, **only (a) Hartley is A-native**; (b)-(e) are all B-native. This means the Information framework has an **asymmetric structure: a single A-anchor (Hartley) and four B-anchors that multiply anchor the B-side**. The 3-rule structure of `feedback_capacity_hartley_vs_shannon` ("Hartley ≠ Shannon, dimensional units in log(), make the comparison gauge $S$ explicit") is explained at the **direction-axis upstream rationale** — Hartley and Shannon share the language of "information content" but are ontologically opposite observation modes; conflating them produces direction-mismatch errors in capacity claims.

**Cross-direction bridge instances (latent within §6 5-anchor theorem)**:
- **S_0 = 2π/e** (`c_arrow_bridge_constants §13` ESTABLISHED): **canonical bridge ratio** between Arrow 1 (2π period, A-side) and Arrow 3 (e argmax, B-side); connects anchors (a) and (b) via a single ratio — the bridge between Hartley density's continuous extremum $d^* = e$ (B-side) and Arrow 1 period $2\pi$ is the **internal coherence anchor** of the 5-anchor structure
- **σ_0 = √(2π/e − 1)** (`research/oq_p1_pareto_g1_v0.md`): in I2 §4 §4.4.1 a B-native Pareto boundary; closed-form bridge constants $\{2\pi, e, -1\}$ pin both σ-axis and S-axis duals
- **ln 2 / log_2 base** (anchor c): Arrow 2 involution can be simultaneously instantiated on both A-side (level-fixed half-value count) and B-side (continuous integral $\int dx/x$ at $x=2$); a candidate bridge

**Triple direction-axis position of N1 / Q1 / I1 framework headers**:

| Header | Native primary | Native secondary | Prominent bridge constants |
|---|---|---|---|
| **N1 (NT)** | A | (B via class number formula bridge) | π (S14), ln 2 (S13), $h = \lim(s-1)L$ (rank-0 bridge) |
| **Q1 (Quantum)** | B | (A via observation outcome) | σ\* (S4), Born rule (B-projection) |
| **I1 (Information)** | **A + B co-resident** (Hartley A / Shannon B 1+4 split) | — | **S_0 = 2π/e (anchor a × b bridge)**, S13 ln 2 (anchor c), σ\* (anchor e) |

The co-resident structure of I1 is the basis on which the Information framework functions as the **operational language layer** of the NT-Quantum bridge — connecting with quantum entropies in Shannon (B-line) and with combinatorial / cardinality / NT-side in Hartley (A-line); the 5-anchor theorem unifies both sides into a single inequality.

**Screening rule application**: when making identity claims within §6 5-anchor theorem, always check the direction tag of the relevant anchor (a A / b-e B) and bridge constants such as S_0. The case of confusing Hartley with Shannon to produce an inflated identity claim (the v0 inflation of 2.18 bits/symbol in I2 §4.2 — over-stated by 5.5×; CANDIDATE_RESOLVED_NEGATIVE for OQ-P1-Capacity) is a direction-mismatch instance that serves as the **canonical cautionary example** for operating the `feedback_cross_direction_identity_screen` discipline within this paper's framework.

**Audit reference**: `project_graveyard_audit_complete_2026_05_01`; `feedback_capacity_hartley_vs_shannon` (upstream rationale relationship).

---

## §2 Axioms of observation theory + formal 0/1/2 scaffold

### 2.1 Observation triple (S, W, m) — information instances

| Symbol | Meaning | Information example |
|---|---|---|
| **S** | infinite structure | probability distribution $p(x)$ over alphabet $\mathcal{X}$, channel kernel $W(y|x)$, model family $\{p_\theta\}$, source distribution, codebook |
| **W** | finite window | finite alphabet truncation $|\mathcal{X}| < \infty$, finite block-length $n$, finite ensemble, finite POVM rank, channel uses |
| **m** | measurement | empirical entropy $\hat{H}$, measured mutual info $\hat{I}(X; Y)$, channel capacity estimate $\hat{C}$, Fisher information sample $\hat{I}_F$, ML-decoded message |

The observed value `m(S|_W)` depends on both S and W; `m(S) − m(S|_W)` is the **finite observation error** = rate-distortion gap or finite block-length penalty in information terms.

### 2.2 Axioms A0-A7 (information instance examples)

| ID | Name | Information instance |
|---|---|---|
| **A0** | Finite observation | finite alphabet $|\mathcal{X}| = d < \infty$, finite block-length $n$ (classical case); finite POVM rank ≤ $d^2$ (quantum case, when information theory is taken on quantum effects) |
| **A1** | Structured error | rate-distortion $R(D) > 0$ for $D < D_{\max}$; outside-typical-sequence probability $\sim 2^{-nE(R)}$ at finite block-length $n$ |
| **A2** | Convergence as observable | source coding theorem: $H + o(1)$ bits/symbol asymptotically; channel capacity $C$ achievable in the limit |
| **A3** | Gauge invariance | mutual information $I(X; Y)$ is invariant under separate bijections of $\mathcal{X}$, $\mathcal{Y}$ (Shannon information is reparametrisation-invariant) |
| **A4** | Non-commutative limits | Stein lemma: $\lim_n \lim_\alpha$ vs. $\lim_\alpha \lim_n$ give different error exponents; quantum Holevo $\chi$ vs. classical Shannon limits |
| **A5** | Saturation | Hartley bound $H \leq \log d$ saturates at uniform distribution; capacity $C = \log d$ at noise-free channel |
| **A6** | Path dependence | conditional entropy $H(X|Y) \neq H(Y|X)$ in general (asymmetry); KL divergence $D(p \| q) \neq D(q \| p)$ |
| **A7** | Scanner hierarchy | Rényi parameter $\alpha$ (entropy family scanner), block-length $n$ (asymptotic scanner), distortion level $D$ (R-D scanner), inverse temperature $\beta$ (Boltzmann distribution scanner) |

Details: `finite_observation.md §1-§7`, `c_information_theory.md §0-§3`.

### 2.3 Formal 0/1/2 scaffold — signal theory / Shannon / relational 3-tier

**Claim 2.1** (scaffold-emergence axis as framework-internal structural lens): information theory is composed of two tiers + a transition axis (scaffold-emergence axis) — a 0/1/2 scaffold layer (signal-theoretic base) and a 3+ relational structure proper layer (genuine information).

| Layer | $d = |\mathcal{X}|$ | Main observable | Residence | Primary framework |
|---|---|---|---|---|
| **0 (potential)** | n/a | $H_0 = 0$, $|\mathcal{X}| = 0$ (vacuous) | pre-observation | none |
| **1 (reference)** | $d = 1$ | $H_0(d=1) = \log 1 = 0$ (single state, no distinction) | observer baseline | none |
| **2 (signal scaffold)** | $d = 2$ | $H_0(d=2) = \log 2 = 1$ bit (binary distinction), Shannon channel capacity, c_s² = 1/2 (parity Born expectation) | **signal theory base** | classical Shannon (`c_information_theory.md §1-§3`) |
| **3+ (relational proper)** | $d \geq 3$ | Rényi α-family, von Neumann $S(\rho)$, Holevo $\chi$, 4-class refined Hodge per-class monotone, 5-stage ln 2 chain, S17 codebook argmax = 3 | **genuine information** | Q1 §5 4-class + Q2 §6 chain + this §6 limit theorem |

**Match between S17 codebook argmax = 3 and the 3+ relational structure floor**: by `c_arrow_bridge_constants.md §12.1`, the discrete codebook argmax of info density $\log d / d$ is = 3 (qutrit, ~5.5% Hartley density advantage over qubit). This is consistent with the framework structural commitment that **3 = mathematical lower bound of relational structure proper**.

**Boundary between signal theory (Shannon) and relational info**: $d = 2$ binary scaffold is a **boundary case** — classically self-closing in the Shannon framework, but on the quantum side the qubit (Hilbert dim = 2) is the scaffold/proper boundary; genuine multi-state relational structure begins from $d \geq 3$ qutrit.

**Status**: framework-internal load as structural lens (load-bearing structural commitment, `user_012_non_integer_scaffold.md`).

### 2.4 §4 dual = information-internal root + L0 v2 axis-2 instances

**Claim 2.2** (root status, information lift): the ι_L/χ dual of `c_phase_complex.md §4` is the unique source of all upper structures (S12-S17, T-AAS) in the dictionary. Information instances:

| Commutative (classical §4 dual) | Information lift |
|---|---|
| $\iota_L: \mathbb{Z}/L\mathbb{Z} \to S^1$ | source distribution $p: \mathcal{X} \to [0, 1]$ + Hartley $H_0 = \log |\mathcal{X}|$ |
| character $\chi: G \to S^1$ | type-class characters (via Sanov theorem large-deviation) |
| Pontryagin dual | Fourier-domain channel representation + spectral representation |
| $\mathbb{C} = S^1 \times \mathbb{R}_{>0}$ polar | amplitude (Boltzmann weight) × phase (Fourier mode) decomposition in MaxEnt distributions |

**L0 v2 axis-2 (Fi/I × D/C) information instances**:

| L0 v2 axis | Information instance |
|---|---|
| **axis-2 Fi** (finite observer side) | finite alphabet, finite block-length, finite ensemble, pre-asymptotic finite-N statistics |
| **axis-2 I** (infinite idealisation side) | $|\mathcal{X}| \to \infty$ continuous source, $n \to \infty$ asymptotic Shannon limit, $\beta \to \infty$ ground-state limit |
| **axis-1 D** (discrete) | discrete random variable, finite alphabet, integer Hamming distance, Hartley counting |
| **axis-1 C** (continuous) | continuous random variable (Gaussian channel), differential entropy, Fisher metric |

L0 v1 ⊂ L0 v2 conservative extension. Information-NT-quantum parallel: all 3 framework headers are loaded as classification of **I → Fi traversal** of the axis-2 Fi/I boundary.

**Status**: ESTABLISHED (`oq_l0_refinement_finite_infinite_2axis_v0.md`).

---

## §3 S15 Observable Trichotomy — Information layer internal taxonomy

### 3.1 Main theorem (Information layer internal sub-taxonomy)

**Theorem 3.1 (S15 + Information layer 5-strand sub-taxonomy)**: the S15 Information layer has an **internal sub-taxonomy**. The **5-strand bundle** of `c_information_theory.md §0` (Shannon channel / Rate-Distortion / Information Bottleneck / Fisher / Algorithmic) is internal sub-classification of the Information layer.

| Strand | Core object | L0 question | Scaffold-emergence layer |
|---|---|---|---|
| **Shannon (§1-§3)** | $H, I, D_{KL}$ | How much can the window transmit? | 2-domain (binary scaffold extension) |
| **Rate-Distortion (§4)** | $R(D)$ | How much must the window discard? | 2-domain → 3+ (lossy compression in proper) |
| **Information Bottleneck (§5)** | $I(X; T)$ vs. $I(T; Y)$ | What should the window keep for a task? | 3+ (task-directed info, statistical-mechanics analogue of the Q-series) |
| **Fisher / Geometry (§6)** | $I_F(\theta), g_{ij}$ | How sensitive is the window to parameters? | 3+ (Riemannian geometry on 3+ dim manifold) |
| **Algorithmic (§8)** | $K(x)$ | How complex is the object itself, independent of the window? | 3+ (universal Turing machine, beyond binary scaffold) |

The 5 strands share the L0 axiom A0 (finite observation) as common root but measure different things: Shannon = observer's channel / Fisher = observer's sensitivity / Kolmogorov = object's intrinsic complexity (`c_information_theory.md §0` thesis).

### 3.2 S15 3-layer instances per strand

| Strand | Scan instance | Structural instance | Information instance (this layer) |
|---|---|---|---|
| **Shannon** | source distribution $p$ as scanner over $\mathcal{X}$ | $|\mathcal{X}| = d$ alphabet size | $H(p) = -\sum p \log p$ |
| **Rate-Distortion** | distortion level $D$ as scanner | $|\hat{\mathcal{X}}| = M$ codebook size | $R(D) = \min I(X; \hat{X})$ s.t. $E[d(X, \hat{X})] \leq D$ |
| **IB** | trade-off parameter $\beta$ as scanner | task-relevant variable $Y$ structure | $\mathcal{L}_{\text{IB}} = I(T; Y) - \beta^{-1} I(X; T)$ |
| **Fisher** | parameter $\theta$ as scanner | model family dim | $I_F(\theta) = E[(\partial_\theta \log p)^2]$, Cramér-Rao $\mathrm{Var}(\hat\theta) \geq 1/I_F$ |
| **Algorithmic** | candidate program length scanner (running over the space of all programs $\{p : U(p) = x\}$) | UTM specification (choice of universal Turing machine, additive constant scope) | $K(x) = \min\{|p| : U(p) = x\}$ — the **minimum** program length, distinct from the arbitrary scanner above |

### 3.3 Rényi α-family as scaffold-emergence parametric scan

**Rényi entropy family** (`c_information_theory.md §1.5`):
$$H_\alpha(X) = \frac{1}{1-\alpha} \log \sum_x p(x)^\alpha, \quad \alpha > 0, \alpha \neq 1$$

**Theorem 3.3.1 (Rényi scaffold-emergence parametric scan, ESTABLISHED 2026-04-28)**: $\{H_\alpha\}_{\alpha \in [0, \infty]}$ is a **continuous parametric scan of the scaffold-emergence axis**, with the following 4-anchor structure:

| α | $H_\alpha$ | scaffold-emergence layer | mechanism |
|---|---|---|---|
| **α = 0** | $H_0 = \log\|\mathrm{support}(X)\|$ (Hartley) | **scaffold-base** (0/1/2 base) | pure cardinality counting; independent of distribution shape on the support |
| **α = 1** | $H_1 = -\sum p \log p$ (Shannon) | **2-domain → 3+ transition** | first $\alpha$ to use the full distribution shape (L'Hôpital limit) |
| **α ≥ 2** | $H_\alpha = \frac{1}{1-\alpha}\log\sum p^\alpha$ | **3+ relational proper** | explicit dependence on collision moments $\sum p^k$ ($k \geq 2$) |
| **α = ∞** | $H_\infty = -\log\max_x p(x)$ (min-entropy) | **3+ relational proper, worst-case** | concentrates on the dominant outcome; security limit |

**Proof sketch (4 anchors)**:
- **(i)** $\alpha \to 0^+$: $\sum p(x)^\alpha \to |\{x : p(x) > 0\}|$, so $H_\alpha \to \log|\mathrm{support}|$ = Hartley. Distribution shape on the support contributes nothing (cardinality only).
- **(ii)** $\alpha \to 1$: by L'Hôpital, $\lim_{\alpha \to 1} H_\alpha = -\sum p \log p$ = Shannon. Shannon is the first $\alpha$ that uses full shape.
- **(iii)** $\alpha = 2, 3, \ldots$: $H_\alpha$ depends explicitly on collision moments $\sum p^k$, with higher moments dominating at higher α. Collision entropy ($\alpha = 2$) is the first instance of 3+ relational structure proper.
- **(iv)** $\alpha \to \infty$: $\sum p^\alpha \approx (\max p)^\alpha$ gives $H_\alpha \to -\log\max p$ = min-entropy = log of the worst-case dominant outcome.

**Corollary 3.3.2 (monotone traversal)**: $H_\alpha$ is **monotonically non-increasing in α** (van Erven & Harremoës 2014). Hence scanning α from 0 to ∞ traces Hartley (max-cardinality, scaffold-base) → Shannon (transition) → collision (3+ proper) → min-entropy (worst-case) by **monotone descent**, completely traversing the scaffold-emergence axis once.

**Status**: ESTABLISHED 2026-04-28 (standard Rényi properties (i)-(iv) + scaffold-emergence labelling + monotonicity-driven traversal completeness; natural α-parameterisation of the §2.3 0/1/2 scaffold lens). Information-internal lift of the S12 additive Scan family (`c_theorems_master.md` row S12).

### 3.4 Exclusivity / exhaustivity (information-internal closure)

Information-internal verification closes in 3 steps:

**(i') Existence of information observables in each layer** (lower bound for exhaustivity):
- Scan: source distribution $p$, Rényi parameter $\alpha$, R-D scanner $D$, IB parameter $\beta$, Fisher parameter $\theta$, block-length $n$, channel uses — **7 instances**
- Structural: alphabet size $d$, codebook size $M$, Hamming distance, Galois orbit (cyclic codes), parity-check matrix rank, support cardinality — **6 instances**
- Information: Shannon $H$, Rényi $H_\alpha$, mutual info $I$, KL $D_{KL}$, R-D $R(D)$, IB $\mathcal{L}_{\text{IB}}$, Fisher $I_F$, Kolmogorov $K(x)$, persistent Betti $\beta_p^t$ — **9 instances**

**(ii') c_information_theory.md 12 sections enumeration** (upper bound for exhaustivity):

12 sections (§1 Shannon / §2 Mutual info & capacity / §3 KL & relative entropy / §4 R-D / §5 IB / §6 Fisher / §7 Bayesian / §8 Algorithmic / §9 TDA / §10 L0 translation / §11 Bridges / §12 Open Questions) cover the Information-layer internal sub-classification with completeness. **Absence of counter-example**: across 12 sections × all observables exhaustively, no information observable falling outside the 3 layers is known as of v0.1.

**(iii') S12/S13/S14/S17 information-internal verification**:
- S12 ⊂ Scan: Rényi α-family is an S12 additive #6 instance; $Z_\alpha = \sum p^\alpha$ is partition-function-like generating
- S13 = information version of the quantum instance of ζ functional eq s = 1/2 = $H_0 = \log d$ saturation at uniform distribution; $H = \log 2$ at parity uniform measure (ℤ/2ℤ)
- S14 asymmetry: π (S¹ phase, requires Fourier transform spectral domain) vs. ln 2 (Boltzmann/Shannon natural unit) — difference between intra-layer vs. inter-layer residence
- S17 = info density $\log d / d$ extremum at $d = e$ (continuous) / $d = 3$ (discrete codebook argmax)

**3-domain cross-validation with N1 (NT) + Q1 (quantum)**: the **independent enumeration by 3 framework headers** of N1 NT 6 entries + Q1 quantum 8 entries + I1 information 12 sections independently verifies S15 trichotomy closure in 3 mathematical fields → **domain-independent universality** of the framework verified by 3-domain triple anchor (subset-specialisation perspective of the Paper D 6-domain triangulation).

---

## §4 Arrow structure — three connections (information instances)

### 4.1 Arrow 1: Scan → Structural (information source decomposition)

**Principle**: "read" the structural skeleton (alphabet $\mathcal{X}$, support, type class) of the source distribution $p$ (Scan, parametric over $\mathcal{X}$).

| Scan | Source structure | Encoded Structural |
|---|---|---|
| $p(x)$ source | alphabet $\mathcal{X}$ | $|\mathcal{X}| = d$ |
| Rényi $H_\alpha$ family | $p$ support | support cardinality |
| R-D $R(D)$ | codebook | $M$ codebook size |
| IB $\mathcal{L}_{\text{IB}}$ | bottleneck $T$ | $|\mathcal{T}|$ bottleneck cardinality |
| Fisher $I_F(\theta)$ | parameter family | model dim |
| Kolmogorov $K(x)$ | UTM specification | program structure |

**Formalisation**: extraction of the structural skeleton of source/codebook is Arrow 1 input specification reading.

#### 4.1.1 Observable-choice dependence (information instances)

The Structural extracted by Arrow 1 is **not unique** (same as Q1 §4.1.1):

| Candidate | Definition | Balance locus | Gauge verdict |
|---|---|---|---|
| **alphabet size $d$** | $|\mathcal{X}|$ | $H_0 = \log d$ saturation | universal (Hartley bound) |
| **typical set size** | $\sim 2^{nH}$ | block-length asymptotic | observable selector ($n$-dependent) |
| **support cardinality** | $|\{x : p(x) > 0\}|$ | non-zero probability mass | observable selector |
| **codebook size $M$** | discrete code | rate $R = (\log M)/n$ | application-specific |

**Principles**: (1) alignment (domain natural arithmetic); (2) observable-specific verdict; (3) explicit propagation to verdict form (consistent with Paper D §4.1.1 + N1 §4.1.1 + Q1 §4.1.1).

### 4.2 Arrow 2: Scan → Information (log-exp duality, Shannon-Rényi chain)

**Principle**: information lift of the thermodynamic chain
```
Z_α(p) = Σ p(x)^α                ← Scan (Rényi partition function)
F_α = -log Z_α / (α - 1)         ← Rényi entropy = log bridge
H_1 = -Σ p log p                 ← Shannon (α → 1 limit)
S = -Tr(ρ log ρ)                 ← von Neumann (quantum lift)
```

| Scan | $Z(\alpha)$ | $F(\alpha)$ | Information |
|---|---|---|---|
| $p(x)$ source | $Z_\alpha = \sum p^\alpha$ | $-\log Z_\alpha / (\alpha - 1)$ | $H_\alpha$ Rényi |
| q-state Boltzmann $e^{-\beta E}$ | $Z(\beta)$ | $F = -kT \log Z$ | $S$ thermodynamic entropy |
| quantum Gibbs $e^{-\beta H}$ | $Z = \mathrm{Tr}(e^{-\beta H})$ | $F$ free energy | $S(\rho_\beta)$ von Neumann |

**S13 fixed point (information)**: $H_0 = \log d$ saturation at uniform distribution; $H_1(\text{Bernoulli}(1/2)) = \log 2$ at parity uniform — information instance of the ln 2 fixed point on Arrow 2 (consistent with the quantum instance in `c_arrow_bridge_constants.md §12.1`).

### 4.3 Arrow 3: Structural → Information (combinatorial counting, Hartley)

**Principle**: Hartley entropy $H_0(D) = \log |D|$ — log of Structural cardinality = **base anchor of the information layer**.

| Structural | $|D|$ | $H_0 = \log |D|$ | Meaning |
|---|---|---|---|
| Alphabet | $d$ | $\log d$ | maximum information capacity (uniform-distribution upper bound) |
| Codebook | $M$ | $\log M$ | code rate base |
| Support | $|\mathrm{supp}(p)|$ | $\log |\mathrm{supp}|$ | non-zero prob mass count |
| UTM program | $|p|$ | $\log |\Omega_{\text{prog}}|$ | algorithmic complexity scale |

**S17 fixed point (information)**: info density $d(n) = (\log n)/n$ extremum at $n = e$ (derivative-fixed extremum on Arrow 3, gauge³-invariant). Information instance: $\log d / d$ continuous max at $d^* = e \approx 2.718$ → **discrete codebook integer argmax = 3** (qutrit) (5/5 gate PASS, `oq_omega_obs_3_info_density_check.py`).

**Observation**: S17 codebook argmax = 3 is the **mathematical match with the 0/1/2 scaffold lens "3 = relational structure floor"** — the first integer beyond the scaffold (0/1/2) (= 3) optimises info density; framework structural commitment and mathematical fact converge.

### 4.4 Commutativity of three Arrows (information instances)

**Theorem 4.1 (commutativity of three Arrows, information instances)**: the three Arrows commute at extreme limits scanner → 0 (or ∞). Three information-internal instances:

| Instance | Limit | Mechanism |
|---|---|---|
| **uniform distribution limit** ($p$ → uniform) | $H \to \log d$ saturation, all Rényi $H_\alpha \to \log d$ collapse, info density max | at uniform $H_\alpha = H_0$ for all $\alpha$ — **Rényi family collapses to Hartley** |
| **delta distribution limit** ($p$ → point mass) | $H \to 0$, $H_\alpha \to 0$ for all $\alpha$, info density 0 | trivial (all Arrows 0; degenerate at point mass) |
| **block-length $n \to \infty$** (asymptotic equipartition) | typical set $\sim 2^{nH}$, achievable rate = $H$, channel capacity = $C$, source coding bound saturates | asymptotic regime of Shannon source coding theorem — **Arrow 1 (typical set count), Arrow 2 (entropy rate), Arrow 3 (Hartley typical $\log 2^{nH} = nH$) commute simultaneously** |

3 instances verify commutativity at extreme limits and asymptotic regime. **Status**: ESTABLISHED (`c_arrow_framework.md §4`).

### 4.5 S13 / S14 / S17 residence — information context

| Constant | Residence | Mechanism (information context) | Stationary form |
|---|---|---|---|
| **π** | inside Scan (additive axis) | Fourier-domain channel representation, complex spectral analysis (Gaussian channel capacity $C = \log(1 + S/N)$ via spectrum), characteristic function $E[e^{itX}]$ → **algebraic** | S14 parity (additive) |
| **ln 2** | on Arrow 2 | Boltzmann/Shannon natural unit, $H(\text{Bernoulli}(1/2)) = \log 2$, Landauer $kT \ln 2$ per bit, **5-stage ln 2 chain** (Q3 §4 + `c_arrow_bridge_constants.md §12.2`) → **analytic** | **value-fixed** (S13) |
| **e** | **on Arrow 3** | info density $\log d / d$ max at $d = e$ continuous, codebook argmax = 3 discrete, gauge³-invariant → extremum principle | **derivative-fixed** (S17) |

**Bidirectional duality 3/3 completion** (`c_arrow_bridge_constants.md §2`): Arrow 1 → π / Arrow 2 → ln 2 / Arrow 3 → e; canonical constants reside on the three Arrows; constant level complete. Information-internal verification: $\log d / d$ continuous argmax ≈ e, codebook integer argmax = 3 (5/5 gate PASS).

---

## §5 T-AAS — 4-class refined Hodge (information instances + algorithmic / topological obstruction)

### 5.1 Main theorem (information T-AAS instance)

**Theorem 5.1 (T-AAS, information instance)** — for the non-trivial kernel of Arrow 1 (φ: Structural → Scan), ker(φ) = ker_gauge ⊕ ker_topo direct sum decomposition; conductor f = f_torsion + f_rational splitting (same statement as Q1 §5.1 + N1 §5.1, information instance specialisation).

### 5.2 Information instances — 4-class refined Hodge lift + existing obstructions

**Information-internal T-AAS 4 instances + 2 existing obstructions = 6 instance fitness**:

**Information instance lift of Q1 §5.2 4-class refined Hodge**:

| # | Class C | Information instance | f_rational monotone | Mathematical bound (anchor in this §6) |
|---|---|---|---|---|
| **C₁** | Stabilizer | classical-simulable codes (Calderbank-Shor-Steane, Gottesman-Knill) | $M_F$ magic = non-stabilizer code state distance | classical-simulable code class boundary |
| **C₂** | Gaussian | Gaussian channel + CV codes | Wigner negativity $\mathcal{N}$ | gap between Gaussian capacity Shannon-Hartley $C = \log(1+S/N)$ and non-Gaussian capacity |
| **C₃** | Eff-sim | poly-time encodable codes | Nielsen $C - c_0 n^k$ | BQP-vs-classical encoding boundary (random-circuit codes) |
| **C₄** | Bell-local | LOCC channels (local operations, classical communication) | $\Delta_{\text{CHSH}}$ | nonlocal channel capacity vs. LOCC capacity gap (Bennett-Shor-Smolin entanglement-assisted) |

**2 existing information-internal obstruction instances**:

| Instance | ker_gauge | ker_topo | f_torsion | f_rational | Status |
|---|---|---|---|---|---|
| **Algorithmic complexity** (Kolmogorov) | UTM choice (additive constant, `c_information_theory.md §8.1`) | $K(x)$ uncomputability obstruction | UTM additive constant ($O(1)/\|x\| \to 0$) | $K(x \mid B)$ in bits (Theorem 5.2 below) | **ESTABLISHED 2026-04-28** (Theorem 5.2, 7/7 checks PASS, `research/oq_algorithmic_f_rational_v1`) |
| **Topological persistence** (TDA, `c_information_theory.md §9`) | scale parameter $t$ (filtration index) | persistent Betti $\beta_p^t$ topological obstruction | scale-rescaling | persistent topological structure | ESTABLISHED (stability theorem `c_information_theory.md §9.3`) |

**24/24 information-relevant fitness** in total across 6 instances (4-class × 4 properties + 2 existing × ≥3 properties).

#### 5.2.1 Theorem 5.2 (Algorithmic f_rational unified form, ESTABLISHED 2026-04-28)

**Theorem 5.2 (Algorithmic instance of Theorem 4a.1)**: for an observation $x \in \{0,1\}^*$ with structural background $B$ (known L1/L2 dictionary content / conditioning data), the **algorithmic f_rational** is defined by the conditional Kolmogorov complexity:
$$f_{\mathrm{rational}}^{\mathrm{alg}}(x; B) := K(x \mid B) \quad [\text{bits}]$$

This is the algorithmic instance of the Theorem 4a.1 (`c_filtration_obstruction.md §8.5.3`) unified $M_{\mathrm{unified}}^C$:
$$M_{\mathrm{unified}}^{C^{\mathrm{alg}}_B}(x) = -\log_2 F_{C^{\mathrm{alg}}_B}(\delta_x) \asymp K(x \mid B)$$
where $C^{\mathrm{alg}}_B$ = computably-encodable distributions given $B$, and $F_{C^{\mathrm{alg}}_B}(\delta_x) = \sup_{q \in \overline{C}} q(x) \asymp 2^{-K(x|B)}$ is the Solomonoff prior given $B$ (universal computable distribution, Coding Theorem).

**Conditions check (Theorem 4a.1 hypotheses)**:
- (i) Convex closure: ✓ (mixtures of computable distributions are computable up to $O(\log)$ overhead)
- (ii) Class-preserving operations: ✓ (computable transformations preserve "computably-encodable" closure)

**Properties (matching the L0 A1 axiom `finite_observation.md §5.1`)**:
- **Gauge-asymptotic invariance**: a UTM gauge change shifts $K(x \mid B)$ by $O(1)$, vanishing as a rate $O(1)/|x| \to 0$ as $|x| \to \infty$ (Kolmogorov invariance theorem).
- **Reducible by structural conditioning**: better $B$ (more known theorems) reduces $K(x \mid B)$. This *is* the L4 error reframing of `c_information_theory.md §8.4`.
- **Provably > 0 for generic $x$**: by counting, most strings of length $n$ have $K(x) \geq n - O(\log n)$.
- **Uncomputable but per-string finite**: $K(x \mid B)$ is not algorithmically extractable for all $x$ (halting problem), but is definitionally finite for any specific $x$. **The framework's strongest "obstruction provably non-zero AND non-computable" instance**.

**5 concrete instances + 2 verification checks** (`research/oq_algorithmic_f_rational_v1.py`, $|x| = 65536$ bits, $K_{\mathrm{upper}} = \min(\mathrm{gzip}, \mathrm{bz2}, \mathrm{lzma})$ as the tightest computable upper bound):

| Instance | rate $K_{\mathrm{upper}}/|x|$ | regime |
|---|---|---|
| I1 random uniform binary | **1.0028** | algorithmically random ($K(x) \approx |x|$) |
| I2 periodic 'ABCDEFGH' | **0.0067** | structurally determined ($K \sim O(\log N)$) |
| I3 sparse spikes (~2%) | **0.0299** | low-entropy regime |
| I4 π binary expansion | **1.0028** | "looks random under naive compressors" — gap demonstration $K_{\mathrm{upper}} \gg K_{\mathrm{true}}$ (parallel to Stark f_field: numerical bound is conservative) |
| I5 periodic + 5% noise | **0.1235** | intermediate (structure + noise floor) |
| V1 $K(x \mid B) < K(x)$ | $-24$ bits ($-0.30\%$) | conditioning reduces (direction ✓) |
| V2 UTM-gauge spread, asymptotic | $0.508 \to 0.027$ (N: 2048 → 131072) | $\sim 1/N$ convergence ✓ |

**Rate range $[0.0067, 1.003]$ — 5 orders of magnitude** — establishes $f_{\mathrm{rational}}^{\mathrm{alg}}$ as a sharp discriminator between structurally-determined and algorithmically-random observations. **7/7 checks PASS**.

**Cross-arrow consistency at log₂-bit unit (Theorem 4a.1 unified scale)**: the algorithmic instance scales freely with $|x|$, extending the unified f_rational range beyond Hodge / Q1 4-class / Stark, which are dim-bounded by their specific structures. The algorithmic instance sits at the **uncomputable extreme** of the framework's f_rational instance spectrum.

**3 spawned successor OQs** (forward tasks from this Theorem):
- **OQ-Alg-MDL-Tightness** (MEDIUM): quantitative bound on $K_{\mathrm{upper}}^{\mathrm{MDL}} - K(x|B)$ for natural string classes
- **OQ-Alg-Hodge-Parallel** (LOW): random binary as 5th data point in Conjecture 4a.2 sparsity-matched comparison
- **OQ-Alg-Quantum-Cross** (MEDIUM): $K(\rho)$ via tomography classical record bridges Q1 4-class to algorithmic instance

**Per-class fitness witnesses (cross-paper synchronisation with Q1 §5.2)**:
- **C₁**: 1-qubit T-state $|T\rangle = (|0\rangle + e^{iπ/4}|1\rangle)/\sqrt{2}$ → empirical numerical M_F = 4e-16 (`oq_omega_obs_4a_monotone_verify.py`); Bravyi-Smith-Smolin (2016), Howard-Campbell (2017) magic robustness literature confirmed.
- **C₂**: Fock state $|n\rangle$ ($n \geq 2$) Wigner negativity $\mathcal{N} > 0$; Mari-Eisert (2012) photon-subtracted calculation 1e-4 precision; Hudson's theorem characterisation of $\overline{C_2}$.
- **C₃**: 2-qubit Bell Nielsen complexity > product state (Jefferson-Myers §3 known); random-circuit super-poly (Bouland-Fefferman 2019); resource-theoretic monotone (Brandão-Horodecki 2019); 3-reference confirmed.
- **C₄**: Bell state $|\Phi^+\rangle$ has CHSH value $2\sqrt{2}$, $\Delta_{\text{CHSH}} = 2\sqrt{2} - 2 \approx 0.828$, Tsirelson bound 1e-6 precision; Clauser-Horne-Shimony-Holt (1969), Tsirelson (1980) literature confirmed.

### 5.3 Theorem 4a.1 unified f_rational — information instance

The Theorem 4a.1 of `c_filtration_obstruction.md §8.5.3` (unified $M_{\mathrm{unified}}^C = -\log_2 F_C$ via class infidelity) applies in the same form for information instances. For an information source/code state $\rho_{\text{code}}$:
$$F_C(\rho_{\text{code}}) := \sup_{\sigma \in \overline{C}_{\text{code}}} F(\rho_{\text{code}}, \sigma)$$

Class-fidelity quantifies the class-stratified distance between information source distribution and code state.

### 5.4 Hodge conjecture — information-adjacent open frontier

The Hodge conjecture (algebraic geometry) is strictly speaking not information theory but is positioned as **information-adjacent open frontier** (parallel to N1 §5.4 NT-adjacent):

- **Information-side instances**: Q1 §5 4-class with f_rational > 0 ESTABLISHED (4 instances); together with the information lift in §5.2 (classical-simulable / Gaussian / poly-encode / LOCC), 4 information-encoding instances ESTABLISHED.
- **Relation to classical Hodge**: Conjecture 4a.2 depth parallel quantitative form (`c_filtration_obstruction.md §8.5.4`) — typical scale O(1) proportionality between information-side unified $M_{\mathrm{unified}}^C$ and classical $f_{\mathrm{rational}}^{\mathrm{Hodge}}$.

→ the information framework provides **assault from 3 framework anchors** on the classical Hodge conjecture: N1 (NT-adjacent open) + Q1 (4-class ESTABLISHED + parallel) + I1 (4 information-lift instances + 2 existing obstructions).

---

## §6 5-anchor mathematical information limit theorem

### 6.1 Theorem statement

The 5-anchor information limit is stated in three explicit pieces — a weak ESTABLISHED form (joint constraint), an ESTABLISHED independence claim, and an OPEN completeness conjecture — to keep the strength of each claim distinct.

**Theorem 6.1 (5-anchor information limit, weak form, ESTABLISHED 2026-04-27)** — for any finite observation system $(S, W, m)$ in information-theoretic context, the quantified information content **simultaneously satisfies** all 5 of the following constraints:

**(a) Hartley cardinality bound** (Arrow 3, S15 Information layer base):
$$H(p) \leq H_0(d) = \log d, \quad d = |\mathcal{X}|$$
Equality saturates at uniform distribution (`c_information_theory.md §1.3`).

**(b) S17 info density extremum** (Arrow 3, S17 e-extremum):
$$\frac{H_0(d)}{d} = \frac{\log d}{d} \leq \frac{1}{e} \quad \text{at} \quad d^* = e \approx 2.718 \text{ (continuous)}$$
Discrete codebook integer argmax at $d^*_{\text{discrete}} = 3$ (qutrit), Hartley density $\log 3 / 3 \approx 0.366$ vs. qubit $\log 2 / 2 \approx 0.347$ (~5.5% advantage).

**(c) 5-stage ln 2 chain universal natural unit** (S13, c_arrow_bridge_constants §12.2):
$$\text{Universal natural unit} = \ln 2$$
5 instances verified independently across (S0) Born $c_s^2 = 1/2$ / (S1) von Neumann $S(\rho_{\max}) = \log 2$ / (S2) FDT parity $\beta\hbar\omega_0 = \log 2$ / (S3) Landauer $W_{\min} = kT \ln 2$ / (S4) σ\* gauge $\sigma_*^2 = 2 \ln 2$.

**(d) Per-class T-AAS 4-class monotone** (Arrow 1 kernel narrowness, Theorem 4a.1):
$$M_{\mathrm{unified}}^C(\rho) = -\log_2 F_C(\rho), \quad F_C(\rho) := \sup_{\sigma \in \overline{C}} F(\rho, \sigma)$$
Per-class info-resource monotone bound for 4 classes C ∈ {Stabilizer, Gaussian, Eff-sim, Bell-local}, log₂-bit unified unit.

**(e) σ\* phase observation gauge** (S4, transformation_atlas):
$$\sigma_* = \sqrt{2 \ln 2} \approx 1.1774 \text{ rad} \quad \text{at half-amplitude convention } E[\cos Z] = 1/2$$
Empirically verified on EEG 7 subjects × 5 bands (subject-band averaged std ≈ 0.0012, ESTABLISHED 2026-04-09).

### 6.2 Mutual independence of the 5 anchors

**Theorem 6.1′ (5-anchor independence, ESTABLISHED 2026-04-27)**: the 5 constraints (a)-(e) are **mutually independent** — no constraint is implied by any subset of the others. One-by-one removal does not degenerate the others as constraints:

| Anchor removed | Remaining constraints status | Limit characterisation completeness |
|---|---|---|
| (a) Hartley removed | (b)-(e) only → density extremum + ln 2 chain + 4-class + σ\* | **incomplete in absence of cardinality bound** (upper value unknown) |
| (b) S17 removed | (a)(c)(d)(e) only → cardinality + ln 2 + 4-class + σ\* | **codebook design indeterminate in absence of density optimum** |
| (c) 5-stage chain removed | (a)(b)(d)(e) only → cardinality + density + 4-class + σ\* | **5-instance unification impossible in absence of universal natural unit** |
| (d) 4-class removed | (a)(b)(c)(e) only → cardinality + density + ln 2 + σ\* | **incomplete in absence of resource-stratified bound** (4 resource families undistinguished) |
| (e) σ\* removed | (a)-(d) only → cardinality + density + ln 2 + 4-class | **coherence-bounded channel undefined in absence of phase noise threshold** |

The 5 anchors are **non-redundant**, **mutually independent**, and **simultaneously active fully characterise the limit**.

**Conjecture 6.1″ (5-anchor completeness, OPEN)**: the 5 constraints are jointly **complete** in the sense that any finite-observation information limit derivable from L0 axioms is reducible to a combination of these 5. **Status**: OPEN — the existence of OQ-I-Bekenstein-Extension (§6.5) and other potential 6th-anchor candidates (gravity, relativistic) means completeness is not currently proved; the conjecture asserts that within the L0 framework as currently axiomatised, no further independent anchor is needed. The phrase "fully characterised" in earlier informal statements should be read as referring to **Conjecture 6.1″** rather than to Theorem 6.1.

### 6.3 Connection to physical info limits (Holevo / Landauer / Bekenstein)

**Claim 6.1.2 (re-expressibility of physical info limits within the 5-anchor framework)**: existing physical info limits can be **re-expressed as combined manifestations** of the 5 framework anchors. The relation is **re-expression / classification**, not derivation: each physical limit is a historically independent result, and the 5-anchor framework provides a common organising vocabulary rather than a logical derivation of the older results.

| Physical limit | Re-expressed as |
|---|---|
| **Holevo bound** $\chi \leq S(\bar{\rho}) - \sum p_x S(\rho_x) \leq \log d$ | combined manifestation of (a) Hartley bound at quantum-state ensembles + (d) 4-class C₄ Bell-local instance |
| **Landauer principle** $W_{\min} = kT \ln 2$ per bit | (c) 5-stage ln 2 chain, S3 stage instance |
| **Bekenstein bound** $S \leq 2\pi RE / \hbar c$ | out of scope (gravity, outside this paper's framework); Q-series Q6 future |
| **Margolus-Levitin / Bremermann** $\Delta t \geq \pi \hbar / 2E$ | out of scope (relativistic processing speed, outside this paper's framework) |
| **Tsirelson bound** $|\Delta_{\text{CHSH}}| \leq 2\sqrt{2} - 2$ | (d) 4-class C₄ Bell-local instance |
| **Cramér-Rao** $\mathrm{Var}(\hat\theta) \geq 1/I_F(\theta)$ | (b) Fisher information geometric bound + (a) Hartley |
| **Shannon-Hartley** $C = B \log(1 + S/N)$ | (a) Hartley + Gaussian channel (4-class C₂ instance) |

The 5-anchor framework **re-expresses** Holevo + Landauer + Tsirelson + Cramér-Rao + Shannon-Hartley within a common vocabulary; Bekenstein / Margolus-Levitin are out of scope (gravity / relativistic; Q-series future Q6).

### 6.4 Status

**ESTABLISHED 2026-04-27** (as the main result):
- (a) Hartley `c_information_theory.md §1.3` existing
- (b) S17 e-extremum `c_arrow_bridge_constants.md §7` ESTABLISHED 2026-04-23 (5/5 gate)
- (c) 5-stage ln 2 chain `c_arrow_bridge_constants.md §12.2` ESTABLISHED 2026-04-27 (Q-series cumulative)
- (d) 4-class refined Hodge + Theorem 4a.1 `c_filtration_obstruction.md §8.5` ESTABLISHED 2026-04-23 (6/6 gate)
- (e) σ\* atlas residence `transformation_atlas/sheet_A_amplitude/sigma_star.md` ESTABLISHED 2026-04-09

All 5 anchors independently ESTABLISHED + 6.2 independence (Theorem 6.1′) + 6.3 re-expressibility of physical limits → **Theorem 6.1 (weak form) and Theorem 6.1′ (independence) ESTABLISHED 2026-04-27** (main results of this paper); **Conjecture 6.1″ (completeness) remains OPEN**.

### 6.5 OQ-I-Bekenstein-Extension forward

**OQ-I-Bekenstein-Extension (this paper's spawn-off)**: Bekenstein bound + Margolus-Levitin lie outside the 5-anchor framework. Possibility of adding gravity-related info limit anchors (6th anchor candidate) in Q-series future Q6 (quantum gravity framework). Status: OPEN, Q-series future.

---

## §7 Six-step protocol for new information domains

Procedure for new information domains (new information measures, new channel classes, new code families, new resource theories) (`meta/new_domain_protocol.md` information specialisation, §10 NEW).

| Step | Content (information specialisation) |
|---|---|
| **0** | Identify §4 dual projection (information lift) — additive (source distribution $p$ + Hartley $\log |\mathcal{X}|$), multiplicative (type-class characters, Sanov large-deviation), Bridge (probability simplex $\Delta(\mathcal{X})$ + Fourier domain) |
| **1** | Identify Scan observable — Rényi α-family / R-D distortion $D$ / IB parameter $\beta$ / Fisher parameter $\theta$ / block-length $n$? S12 6+1 member information correspondence |
| **2** | Identify Structural observable — alphabet size $d$, codebook $M$, support cardinality, Hamming distance, parity-check rank, model dim |
| **3** | Identify Information observable — Shannon $H$ / Rényi $H_\alpha$ / mutual info $I$ / KL $D_{KL}$ / R-D $R(D)$ / Fisher $I_F$ / Kolmogorov $K(x)$ / Holevo $\chi$ / per-class monotone (4-class) |
| **4** | Verify three Arrows — Arrow 1 (source/codebook structural skeleton), Arrow 2 ($Z_\alpha \to F_\alpha \to H_\alpha$ Rényi chain), Arrow 3 (Hartley $\log d$ + S17 density extremum) |
| **5** | Confirm T-AAS decomposition — ker_gauge ⊕ ker_topo? conductor f_torsion + f_rational? **information-encoding residence within 4-class refined Hodge** (closest to which of C₁ classical-simulable / C₂ Gaussian channel / C₃ poly-encodable / C₄ LOCC channel)? + relation to algorithmic / topological obstruction |
| **6** | Determine dictionary residence — residence within the 12 sections of `c_information_theory.md`; propose new entries if needed; identify connection points with I2 communication theory |

**Verified applications** (`c_information_theory.md` 12 sections existing closure).

**5 next candidates (information specialisation application targets)**:

| Domain | Step 0 §4 dual | Step 5 T-AAS class candidate |
|---|---|---|
| Quantum LDPC codes | stabilizer formalism + finite group | C₁ Stabilizer + algorithmic obstruction |
| Differential privacy | Rényi divergence over neighbouring data sets | Rényi-α scaffold-emergence axis instance |
| Tensor network states (information) | tensor contraction structure | C₃ Eff-sim + topological obstruction |
| Causal inference (information flow) | DAG structure + intervention | new class candidate (causal-rooted info) |
| Quantum sensing / metrology | Fisher information + parameter estimation | (b) S17 density + Cramér-Rao instance |

---

## §8 Consequences and open frontier

### 8.1 Established (Information-only framework header)

Recorded as ESTABLISHED in information-internal context in this paper:

1. **S15 Information layer internal taxonomy** — 5-strand bundle (Shannon / R-D / IB / Fisher / Algorithmic) + 12 sections enumeration closure (§3)
2. **Formal 0/1/2 scaffold lens** — framework-internal lens loaded: signal theory (binary 2-domain) ⊂ relational info (3+ proper) (§2.3)
3. **Arrow structure (3) and commutativity** — commutativity verified at 3 information instances (uniform / delta / asymptotic equipartition) (§4.4)
4. **T-AAS 4-class refined Hodge information lift + 2 existing obstructions** — 24/24 information-relevant fitness (4-class × 4 + algorithmic + topological, §5.2)
5. **5-anchor mathematical information limit theorem** — fully characterised by Hartley + S17 + 5-stage ln 2 + 4-class + σ\*; 5 anchors mutually independent + subsumes Holevo/Landauer/Tsirelson/Cramér-Rao/Shannon-Hartley (§6, **main result of this paper, ESTABLISHED**)
6. **Information-internal residence of S13/S14/S17** — π/ln 2/e as canonical constants on the three Arrows; complete on the 3-Arrow base (§4.5)
7. **I1 ↔ N1 ↔ Q1 triple framework parallel** — 3 framework headers (NT, quantum, information) × **3-domain cross-domain validation anchor** of the Paper D multi-domain 6-domain triangulation (§3.4 + 1.2)

### 8.2 I2 forward bridge

| I2 forward topic | Forward from this paper |
|---|---|
| **Signal theory (0/1 scaffold)** | classification of signal theory = 2-domain (Shannon binary) under the §2.3 0/1/2 scaffold lens; detailed development of Shannon-Hartley channel + classical capacity in I2 §1 |
| **Quantum communication theory (3+ relational)** | quantum communication theory = C₂/C₃/C₄ instances under the §5 4-class refined Hodge information lift; detailed development of Holevo / HSW / LSD / superdense / teleport / QKD / no-cloning + formal entanglement-assisted capacity in I2 §2 |
| **Novel communication theory 5 proposals** | 5 novel proposals under the §6 5-anchor framework: P1 σ\*-phase channel (S4 instance) / P2 4-class resource-stratified channel (T-AAS lift) / P3 qutrit info-density codebook (S17 instance) / P4 5-stage ln 2 chain converter (S13 universal unit) / P5 Arrow 1 kernel narrowness channel taxonomy. Each formalised in I2 §3-§7 |

### 8.3 Open frontier

| Open question | Status | Related paper |
|---|---|---|
| **OQ-I-Bekenstein-Extension** (Bekenstein + Margolus-Levitin 6th anchor) | OPEN (this paper's spawn) | §6.5, Q-series Q6 future |
| **Conjecture 4a.2** (depth parallel quantitative form, information instance) | OPEN | §5.4, Q1 §5.4 + N1 §5.4 |
| **OQ-Algorithmic-f_rational** (formalising Kolmogorov $K(x)$ uncomputability as f_rational > 0 instance) | **ESTABLISHED 2026-04-28** (Theorem 5.2 §5.2.1, algorithmic instance of Theorem 4a.1 via $K(x \mid B)$ + Solomonoff prior; I1-I5 + V1 + V2 7/7 PASS) | §5.2.1 |
| **OQ-Alg-MDL-Tightness** (computable $K_{\mathrm{upper}}^{\mathrm{MDL}} - K(x\mid B)$ tightness for natural string classes) | OPEN (spawned 2026-04-28 by this paper) | §5.2.1 |
| **OQ-Alg-Hodge-Parallel** (algorithmic instance as Conjecture 4a.2 sparsity-matched 5th data point) | OPEN (spawned 2026-04-28 by this paper) | §5.2.1 |
| **OQ-Alg-Quantum-Cross** (bridge Q1 4-class ↔ algorithmic instance via $K(\rho)$ from tomography classical record) | OPEN (spawned 2026-04-28 by this paper) | §5.2.1 |
| **OQ-Topological-Persistent-Bridge** (formal bridge between TDA persistent Betti and T-AAS f_rational topological instance) | OPEN | §5.2, `c_information_theory.md §9` existing |
| **OQ-Renyi-Scaffold-Continuous** (formal statement that the Rényi α scanner parametrically traverses the scaffold-emergence axis) | **ESTABLISHED 2026-04-28** (Theorem 3.3.1 + Corollary 3.3.2, §3.3 with 4-anchor structure + monotone traversal completeness) | §3.3 |
| **OQ-S17-Codebook-3-Universal** (formal verification of universality of codebook argmax = 3 across information-theoretic settings) | **ESTABLISHED 2026-04-23** (S17 promotion gate 5/5 PASS, `research/oq_omega_obs_3_e_arrow3_v0.md` + `research/oq_omega_obs_3_info_density_check.py`; 3 settings NT/Codebook/Qudit + gauge invariance) | §4.3 |
| **OQ-S17-Density-Form-Universal** (classification of which info-theoretic settings have density of the form $d(n) = \log n / n$; successor to S17-Codebook-3-Universal) | OPEN (spawned 2026-04-28 by this paper) | §4.3 |

### 8.4 Dictionary residence map

Residence of major framework pieces (reflecting Information-only specialisation):

| Piece in this paper | Residence | Status (I1) |
|---|---|---|
| §2.1 Axiom 1 (Dual receptacle, information lift) | `c_phase_complex.md §4` + `c_information_theory.md §1-§3` | existing reuse |
| §2.2 Axioms A0-A7 (information instances) | `finite_observation.md §1-§7` + `c_information_theory.md §10` (L0 translation) | existing reuse |
| §2.3 formal 0/1/2 scaffold | `user_012_non_integer_scaffold.md` (memory) + this §2.3 NEW formal entry | **annex to be implemented (post-v0.2 backward, candidate dictionary entry `L0_canon/zero_one_two_scaffold.md` NEW)** |
| §2.4 L0 v2 + information instances | `finite_observation.md §8` + this §2.4 NEW information instance examples | existing + this paper expansion |
| §3 S15 + information 5-strand sub-taxonomy | `c_theorems_master.md` row S15 + this §3.1 information-only annex (NEW) | **annex to be implemented (post-v0.2 backward)** |
| §3.2 per-strand S15 3-layer instances | existing 5-strand thesis of `c_information_theory.md §0` + this §3.2 layered map | existing + this paper expansion |
| §4 3-Arrow framework information instances | `c_arrow_framework.md` + this §4.4 NEW information instance annex | **annex to be implemented** |
| §4.5 S13/S14/S17 information residence | `c_arrow_bridge_constants.md §12 (5-stage chain)` + this §4.5 information expansion | existing + this paper information instance expansion |
| §5 T-AAS 4-class refined Hodge information lift | `c_filtration_obstruction.md §8.5` (4-class quantum) + this §5.2 information lift annex (NEW) | **annex to be implemented (post-v0.2 backward)** |
| §6 5-anchor information limit theorem | **NEW** this §6 → "5-anchor mathematical info limit theorem" annex of `c_theorems_master.md` (NEW) | **annex to be implemented (post-v0.2 backward, as main result)** |
| §7 6-step protocol information specialisation | **NEW** `meta/new_domain_protocol.md §10` information specialisation annex | **annex to be implemented** |
| Triple parallel | **NEW** `meta/triangulation_methodology.md §14` I1 ↔ N1 ↔ Q1 triple framework parallel annex | **annex to be implemented** |

**post-v0.2 backward anticipated (I-series, Q-series cumulative 13 + I-series 7 = 20 entries)**:

6 from I1 + 1 from I2 (post-I2):
- `c_theorems_master.md` Information-only S15 enumeration + 5-anchor info limit theorem (2 entries)
- `c_arrow_bridge_constants.md §12.3` information instance expansion (S17 codebook, Rényi family scaffold)
- `c_filtration_obstruction.md §8.6` 4-class information lift + algorithmic / topological obstruction annex
- `meta/triangulation_methodology.md §14` I1 ↔ N1 ↔ Q1 triple framework parallel
- `meta/new_domain_protocol.md §10` information specialisation
- `L0_canon/zero_one_two_scaffold.md` NEW (candidate formal entry for 0/1/2 scaffold, framework-internal load)

**Consequence**: this paper is positioned as the **information-internal framework header** of the dictionary; theorem (5-anchor info limit) formally resides in L0 / L1 / meta entries. After drafting I2 (Communication theory), the **2-paper minimum cycle completes** for framework header (I1) → extension (I2) (unlike the N-series 5-paper / Q-series 3-paper, the cycle can close at the minimum 2 papers, since the 5 anchors are existing and the limit theorem is directly ESTABLISHED).

---

## Change log

- **v0.3 (2026-04-28)**: Promoted OQ-Algorithmic-f_rational to ESTABLISHED + added new §5.2.1 **Theorem 5.2 (Algorithmic instance of Theorem 4a.1)**. Defines $f_{\mathrm{rational}}^{\mathrm{alg}}(x; B) := K(x \mid B)$ in bits and plugs it into the Theorem 4a.1 unified $M_{\mathrm{unified}}^{C^{\mathrm{alg}}_B} = -\log_2 F_C \asymp K(x|B)$ via the Solomonoff prior. Conditions (i)(ii) verified; properties (gauge-asymptotic invariance + reducibility by structural conditioning + provably > 0 for generic $x$ + uncomputable but per-string finite) all PASS. 5 instances (random / periodic / sparse / π binary / structured+noise) + V1 conditional reduction + V2 UTM-gauge convergence give **7/7 checks PASS** (`research/oq_algorithmic_f_rational_v1`). Cross-arrow consistency at log₂-bit unit (Hodge / quantum 4-class / Stark + algorithmic instance gives the framework's most general f_rational instance, with $|x|$ scaling free). §5.2 row (line 333) candidate → ESTABLISHED for consistency; §8.3 OQ table candidate → ESTABLISHED + 3 successor OQ spawn (OQ-Alg-MDL-Tightness / OQ-Alg-Hodge-Parallel / OQ-Alg-Quantum-Cross). The pre-flight audit (`research/oq_algorithmic_f_rational_audit_v0.md`) flagged a dim-semantics worry; under the Theorem 4a.1 unified bit-form this proved over-strict, so scope (a)/(b)/(c) trichotomy is unnecessary and clean closure is achieved within the existing framework.

- **v0.2 (2026-04-28)**: 2 OQ closures + 1 successor spawn. (1) **OQ-S17-Codebook-3-Universal**: §8.3 OQ table OPEN → **ESTABLISHED 2026-04-23** for consistency (5/5 gate PASS already established 2026-04-23 in `research/oq_omega_obs_3_e_arrow3_v0.md`; §4.5/§6.4 already record ESTABLISHED — fixes the §8.3 stale entry); successor OQ **OQ-S17-Density-Form-Universal** (classification of info-theoretic settings with density of form $d(n)=\log n/n$, spawned by this paper) added to §8.3. (2) **OQ-Renyi-Scaffold-Continuous**: §3.3 prose observation lifted to **Theorem 3.3.1 (Rényi scaffold-emergence parametric scan, 4 anchors + monotone traversal)** + Corollary 3.3.2 (monotone non-increasing); §8.3 OQ table candidate → **ESTABLISHED 2026-04-28**. Standard Rényi entropy properties (van Erven & Harremoës 2014) + natural α-parameterisation of the 0/1/2 scaffold lens of §2.3. Framework / 5-anchor main result / structure unchanged; 2-spot edits in §3.3 + §8.3 only.

- **v0.1 (2026-04-27)**: initial Information-only draft. Information specialisation derived from Paper D v0.9.2 (multi-domain frozen-internal). Parallel **3rd framework header instance** with N1 (NT-only) + Q1 (quantum-only). Formally incorporates the 0/1/2 scaffold lens (`user_012_non_integer_scaffold.md`) as framework-internal load-bearing structural commitment. Formalises the 5-anchor mathematical information limit theorem (Hartley + S17 + 5-stage ln 2 + 4-class + σ\*) as the main result. The I1 ↔ N1 ↔ Q1 triple framework parallel completes the 3-specialisation coverage of the Paper D 6-domain triangulation. 1 OQ spawned by this paper (OQ-I-Bekenstein-Extension). Bridge to I2 (Communication theory: signal theory / quantum communication theory / novel communication theory 5 proposals) announced in §8.2.

---

## References (internal)

**Information-only predecessors**: `dictionaries/L1_mathematical/core/c_information_theory.md` (637 lines, 12 sections, main source of this paper)

**N1 / Q1 (parallel framework headers)**:
- `papers/publication/nt/N1_observation_theory_nt_ja.md` (v0.7, NT-only restatement)
- `papers/publication/quantum/Q1_observation_theory_quantum_ja.md` (v0.2, quantum-only restatement)

**Q-series (5-anchor source)**:
- `papers/publication/quantum/Q2_open_qs_chain_ja.md` (v0.2, 4-stage chain + 5-stage ln 2 chain S0-S3)
- `papers/publication/quantum/Q3_born_gleason_ja.md` (v0.2, σ\* gauge S4 + Born derivation)

**Paper D series (predecessor)**: `papers/Paper_D_Observation_Theory_ja.md` (v0.9.2 frozen-internal, multi-domain)

**Sources of the 5 anchors of this paper**:
- (a) Hartley: `c_information_theory.md §1.3` ($H \leq \log d$)
- (b) S17 e-extremum: `c_arrow_bridge_constants.md §7` + `research/oq_omega_obs_3_e_arrow3_v0.md` (ESTABLISHED 2026-04-23, 5/5 gate)
- (c) 5-stage ln 2 chain: `c_arrow_bridge_constants.md §12.2` (Q-series cumulative)
- (d) 4-class refined Hodge: `c_filtration_obstruction.md §8.5` (Theorem 4a.1, ESTABLISHED 2026-04-23)
- (e) σ\* gauge: `transformation_atlas/sheet_A_amplitude/sigma_star.md` (n-only + EEG entries, ESTABLISHED 2026-04-09)

**0/1/2 scaffold load**: `user_012_non_integer_scaffold.md` (memory, framework-internal structural commitment)

**L0 / L1 / meta dependencies**:
- `dictionaries/L0_canon/{observation_canon, finite_observation, identity_asymmetry}.md`
- `L1_mathematical/core/{c_phase_complex §4 + §5, c_theorems_master, c_arrow_framework, c_arrow_obstruction §10-§11, c_arrow_bridge_constants §11 + §12, c_filtration_obstruction §8.5, c_observation_optimal_gauge, c_information_theory.md §1-§12}.md` (main material of this paper)
- `L1_mathematical/quantum/{q_quantum_observation, q_open_quantum_systems, q_quantum_statistical_mechanics, q_quantum_thermodynamics}.md` (5-anchor quantum instance source)
- `transformation_atlas/sheet_A_amplitude/sigma_star.md` (σ\* atlas residence)
- `meta/{triangulation_methodology, new_domain_protocol, open_questions_master}.md`

**Sequel paper**: I2 (Communication theory: signal theory / quantum communication theory / novel communication theory 5 proposals) — drafting planned (announced in §8.2 of this paper)
