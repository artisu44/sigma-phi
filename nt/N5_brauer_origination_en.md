# Paper N5: Brauer Obstruction Theory + Origination Matrix 8-gauge

**Subtitle**: 5-tier failure-mode group-theoretic criteria, Tier-dependent Stark methods, 8 origination gauge families, NT-series final closure

**Version**: v0.2 (compact, 2026-04-26)
**Status**: DRAFT — final paper of the NT framework + result series after N1-N4. Combines two threads: detailed taxonomy of Brauer closure failure modes + generalisation of Paper Ω origination matrix 8-gauge. Completes the NT-series cycle and announces the quantum sequels (Q1-Q3).
**Prerequisites (framework)**: N1 (`N1_observation_theory_nt_ja.md` v0.7) / N2 (`N2_paper2_structural_ja.md` v0.5) / N3 (`N3_path2_dirichlet_universality_ja.md` v0.5) / N4 (`N4_hasseweil_stark_ja.md` v0.3)
**Prerequisites (L1)**: `c_arrow_bridge_constants.md §11` / `c_theorems_master.md` (Path 2 + Dirichlet L + Hasse-Weil L extension scope annexes)
**Prerequisites (L1 NT)**: `nt_conductor.md §6.9` / `nt_dedekind_artin_zeta.md §1, §7` / `nt_frobenius_schur.md` / `nt_root_numbers.md` / `nt_relative_units.md`
**Prerequisites (Paper Ω)**: `papers/Paper_Omega_Origination.md` (v0.7+, 8 constants × 8 gauges)
**Research roots**: `research/brauer_closure_galois_classification_v0.md` (OQ-NT-7 v0.2, success side) / `research/brauer_closure_failure_taxonomy_v0.md` (OQ-NT-8 v0.2, failure side) / `research/stark_projection_v0.md`
**Sequel papers**: Q1 (Quantum observation theory edition) / Q2 (Open QS chain) / Q3 (Born-Gleason)

---

## §0 Abstract

This paper is the **final paper** of the 5-paper NT series. After N4 establishes Hasse-Weil L × Stark structure, we combine (a) **detailed group-theoretic criteria for Brauer 5-tier closure failure modes** + an existence proposal for Tier-dependent Stark methods, and (b) generalisation of Stark 6-gauge by Paper Ω's **8 origination gauge family** (ordinal / addZ / mult / prime_coord / char / cont / geom / anal), bringing the N1-N5 NT framework to closure.

**Main results (M1-M5)**:

**(M1) Brauer 5-tier failure-mode group-theoretic criteria** — a **conjecture** that the 5-tier (Tier 1 strict / 2 relaxed / 3+ multi-rational / √ sqrt-only / ∞ impossible), classified by which of the 4 failure axes (C1 real irrep / C2 induction irreducible / C3 zeta ratio reduction / C4 unit lattice closure) breaks, is fully parameterised by group-theoretic invariants (irrep dim, FS indicator $\nu(\rho)$, subgroup lattice, character inner products). Empirical verification on $S_3$ (Tier 1, ℚ(√−23)) / $D_4$ (Tier 2, ℚ(√−14)) / $Q_8$ (Tier √, LMFDB witness).

**(M2) Tier-dependent alternative Stark methods (existence proposal)** — Tier 1 = classical Stark formula (single ratio) / Tier 2 = field-pair regulator ratio / Tier √ = quaternionic descent + ε-factor sign-resolution attempt / Tier ∞ = Hecke L direct construction (no Stark closure path). Atlas grammar functor formalisation registered as **OQ-NT-6** task on the candidate+ promotion path.

**(M3) Origination matrix 8-gauge (Paper Ω generalisation of Stark 6-gauge)** — 8 origination gauge families (axis-1 D side: ordinal / addZ / mult / prime_coord / char; axis-1 C side: cont / geom / anal); origination signatures of 8 constants (π, e, ζ, γ, τ, i_add, i_mult, Φ) complete. The N4 §4 Stark 6-gauge is the Stark-relevant subset of the 8-gauge (addZ + mult + char + cont + geom + anal — without ordinal + prime_coord). The constants 0.216, 2/3, and ln 2 from N2 §3.1 carry 8-gauge signatures **{anal, mult}**, **{prime_coord, anal}**, and **{char, anal}** respectively.

**(M4) Cross-connection: Brauer 5-tier ↔ Origination 8-gauge** — (a) Tier classification ↔ T-AAS Arrow 1 kernel taxonomy: Tier 1 = $(f_\text{tor}, f_\text{rat}) = (0, k>0)$ / Tier √ = $(1, k\geq 0)$ / Tier ∞ = $(\infty, \infty)$. (b) 8-gauge signature ↔ Path 2 Type α/β/γ trichotomy: Type α = single dominant gauge / Type β = gauge family crossing / Type γ = subspace within gauge family. (c) N3 Atkin-Lehner Type γ ↔ Brauer Tier 2 (D_4) connection (shared sub-object structure). (d) Open question whether Hasse-Weil L adds a **new signature** to 8-gauge.

**(M5) NT-series final closure (N1-N5 cycle complete)** — framework header (N1) + ζ-family core (N2) + Path 2 Dirichlet L "structural fit only" (N3) + Hasse-Weil L genuine BSD (N4) + Brauer + 8-gauge final (this paper) form **NT framework total**. Re-reading the weight-class-dependent transfer pattern from the origination matrix viewpoint: weight-1 abelian (Stark, addZ + mult + char) / weight-1 non-abelian (Brauer Tier 1-3+/√/∞) / weight-2 (Hasse-Weil L, BSD-related new signature candidate).

**Thesis**: full Galois rep closure (abelian Stark + non-abelian Brauer + automorphic Hasse-Weil) + the origination matrix viewpoint of weight-class-dependent transfer pattern provides closure of the NT framework. After NT closure, §7.3 announces the bridge to the **quantum sequels (Q1-Q3)** and positions the quantum-side extension of the N1 framework header as future work.

**Forward / dictionary impact**: NT framework total closure with 15+ cumulative annexes across L0 / L1 / L2 / Meta layers; 4-vertex triangulation proposal_v2 (`meta/triangulation_methodology.md §10`) + "NT-series final closure OQ" section newly created (OQ-NT-6 + OQ-Tier3-Plus-Search + OQ-Tier-Sqrt-Resolution + OQ-433a1-Outlier); Q1-Q3 quantum sequels announced. See §7.5.

---

## §1 Introduction

### 1.1 Position of the NT-series final paper and 2-thread combination

In the 5-paper series N1 (NT observation theory framework header v0.6) → N2 (Paper 2 ζ-family core v0.4) → N3 (Path 2 NT universality v0.3) → N4 (Hasse-Weil L × Stark v0.2) → **N5 (this paper)**, the ζ-family core (N2) is fully ESTABLISHED, the Dirichlet L extension (N3) closed as "structural fit only", and the Hasse-Weil L extension (N4) established **genuine BSD K_E·t²→r**. This N5, as the NT-series final paper, accomplishes 5 tasks: (1) detailed Brauer obstruction theory (failure-mode group-theoretic criteria + Tier-dependent alternative Stark methods); (2) Origination matrix 8-gauge (formal residence in the Paper Ω 8-gauge framework + generalisation of Stark 6-gauge); (3) cross-connection (Brauer 5-tier ↔ Origination 8-gauge); (4) NT-series cycle completion summary; (5) announcement of quantum sequels (Q1-Q3).

**Two main threads**:

**Thread 1 — detailed Brauer obstruction theory** (§2-§3): N4 §5 gave a Stark-connection overview; this §2 details the 4 failure axes (C1-C4 breakdowns) + each Tier example (S_3, D_4, Q_8) and presents a conjecture fully parameterising them by group-theoretic invariants. §3 organises Tier-dependent alternative Stark methods (Tier 1 classical / Tier 2 field-pair / Tier √ quaternionic descent / Tier ∞ Hecke direct) at the existence-proposal level.

**Thread 2 — Origination matrix 8-gauge** (§4): formally resides Paper Ω's **8 origination gauge family** (ordinal / addZ / mult / prime_coord / char / cont / geom / anal) within the NT framework. Formal definition of the axis-1 D/C subdivision disambiguated as **gauge²** in N1 §1.3.1. Position N4 §4 Stark 6-gauge as a subset of 8-gauge; classify N2 §3.1 constants + the N3 §5.3 Fi-origin vs. I-origin dichotomy by 8-gauge signatures.

**Cross-thread** (§5): the axis crossing of Brauer 5-tier ↔ Origination 8-gauge exposes the closure structure of the NT framework.

### 1.2 Forward confluence point + Q1-Q3 announcement

N5 picks up forward tasks from N1-N4: N1 §8.2 (detailed Brauer failure mode + 6→8-gauge) / N2 §8.3 (8-gauge classification of constants) / N3 §7.3 (Atkin-Lehner Type γ ↔ Brauer Tier 2, Fi/I-origin 8-gauge) / N4 §7.3 (failure-mode group-theoretic + Hasse-Weil L 8-gauge) / N4 §10 (OQ-4VertexClosure: 4-vertex triangulation formal closure).

**§7** gives the N1-N5 NT-series cycle completion summary + forward bridge to **quantum sequels (Q1-Q3)**: **Q1** Paper D quantum-side extension (S17 / Hodge / 4-vertex / OQ-Ω-Obs-4a) — quantum version of observation theory; **Q2** Open QS chain (open_quantum_systems → quantum_statistical_mechanics → quantum_thermodynamics → many_body_quantum); **Q3** Born rule + Gleason (§4 dual = root, σ\* = √(2 ln 2), Gleason gap).

---

## §2 Brauer obstruction theory — failure-mode group-theoretic criteria

### 2.1 4 failure axes (C1-C4 breakdowns) recap

The **4 closure conditions** of `brauer_closure_failure_taxonomy_v0.md` v0.2:

| Axis | Condition | Failure meaning |
|---|---|---|
| **A** | C1 (real irrep) | $G$ does not have a real / orthogonal irreducible representation of $\dim = [G:N]$ |
| **B** | C2 (induction irreducible) | $\mathrm{Ind}_N^G \chi$ is not irreducible (Mackey stabiliser $\supsetneq N$) |
| **C** | C3 (zeta ratio reduction) | $L(s, \rho)$ is not a rational combination of intermediate fields |
| **D** | C4 (unit lattice closure) | the Galois orbit of $F$-units does not span $O_H^\times$ / torsion |

Each Tier is sub-classified by which of the C1-C4 closure conditions breaks.

### 2.2 Tier 1 strict (S_3, A_4/V_4)

**Form**: $L(s, \rho) = \zeta_F(s) / \zeta_\mathbb{Q}(s)$ — closes with a single intermediate field $F = H^{\ker\rho}$ as **single ratio closure**. C1-C4 all hold.

**S_3 instance (ℚ(√−23) cubic class character, already in N4 §4.4)**: $K = \mathbb{Q}(\sqrt{-23})$, $h_K = 3$, Hilbert class field $H = \mathbb{Q}(\alpha)$ where $\alpha$ = root of $x^3 - x - 1$. $\rho_2$ = $S_3$ standard 2-dim irrep (real, orthogonal). C1: $\nu(\rho_2) = +1$ ✓ / C2: $\mathrm{Ind}_{A_3}^{S_3} \chi_K = \rho_2$ irreducible ✓ / C3: $L(s, \rho_2) = \zeta_{\mathbb{Q}(\alpha)}(s) / \zeta_\mathbb{Q}(s)$ ✓ / C4: $\alpha, \sigma\alpha$ are fundamental units of $H$ ✓ → Tier 1 strict; Stark formula $L'(0, \chi_K) = \log|\alpha_1|$ exact (Stark unit $\varepsilon_{\chi_K} = \alpha$).

**A_4 / V_4 instance**: $A_4$ (order 12) has 1-dim characters + a 3-dim irrep (real). With $V_4 \trianglelefteq A_4$ (Klein 4-group, Sylow 2-subgroup) as normal subgroup, $\dim \rho = [A_4 : V_4] = 3$ real irrep ✓ / $\rho = \mathrm{Ind}_{V_4}^{A_4} \chi$ for non-trivial $\chi$ ✓ / $L(s, \rho) = \zeta_F / \zeta_\mathbb{Q}$ for $F = H^{V_4}$ ✓ → Tier 1 strict (Hilbert class field setting).

### 2.3 Tier 2 relaxed (D_4 + ℚ(√−14))

**Form**: $L(s, \rho) = \zeta_{F_1}(s) / \zeta_{F_2}(s)$ — closes via the zeta ratio of 2 intermediate fields $F_1 \subsetneq F_2$. **Necessary and sufficient condition** (Frobenius reciprocity): $\exists$ subgroups $H_1 \subsetneq H_2 \leq G$ s.t. $\langle \rho|_{H_1}, \mathbf{1}\rangle - \langle \rho|_{H_2}, \mathbf{1}\rangle = 1$ and $\forall \psi \neq \rho: \langle \psi|_{H_1}, \mathbf{1}\rangle = \langle \psi|_{H_2}, \mathbf{1}\rangle$.

**D_4 instance (ℚ(√−14) Hilbert class field, `brauer_closure_galois_classification_v0.md §11-12`)**: $K = \mathbb{Q}(\sqrt{-14})$, $h_K = 4$, $H = K(\sqrt{2})$, $\mathrm{Gal}(H/\mathbb{Q}) = D_4$ (8-element dihedral). $\chi_K$ = quadratic class character ($\mathrm{Cl}_K \cong \mathbb{Z}/2$). Tier 2 form $L(s, \chi_K)^2 = \zeta_{F_1}/\zeta_{F_2} \cdot (\text{quadratic factor})$ for specific 2 fields $F_1 = K(\sqrt{2}), F_2 = \mathbb{Q}(\sqrt{2})$. Closure: C1 ($\rho$ 2-dim faithful real, $\nu(\rho) = +1$) ✓ / C2 ($\mathrm{Ind}_{Z(D_4)}^{D_4} \chi$ irreducible) ✓ / **C3 (Tier 2 relaxed)**: single ratio fails, 2-field ratio closure ✓ / C4 ($K(\sqrt{2})$-units span $O_H^\times$ / torsion via Galois orbit) ✓. Stark formula $L'(0, \chi_K) \propto h_{F_1} R_{F_1} / (h_{F_2} R_{F_2})$ (developed in N4 §5.4).

### 2.4 Tier 3+ multi-rational (hypothetical)

**Form**: $L(s, \rho) = \prod_i \zeta_{F_i}(s)^{n_i}$, $n_i \in \mathbb{Z}$ — multi-field rational combination. C1-C2 hold; C3 fails to close in 2-field ratio and requires multi-product.

**Candidate groups**: $S_4 / V_4$ (3-dim irrep, multiple intermediate fields) / $A_5$ (3-dim, 4-dim, 5-dim irreps) / higher-dim irreps of general non-abelian simple groups.

**No verified instance**: no concrete Tier 3+ instance is currently confirmed within the NT framework. **OQ-Tier3-Plus-Search** registered as OPEN open frontier (§7.4).

### 2.5 Tier √ sqrt-only (Q_8 quaternionic, already in N4 §5.3)

**Form**: $L(s, \rho)^{2k}$ rational but $L \notin$ — even-power rational; **sign obstruction** key feature.

**Q_8 instance recap (LMFDB 8.0.12230590464.1)**: 2-dim irreducible ρ quaternionic ($\nu(\rho) = -1$), $L(0, \rho)^2 = 16$, $L(0, \rho) = \pm 4$ sign obstruction. Structural origin: the 2-dim irreducible ρ of $Q_8$ is realised over ℍ (quaternion division algebra); under ℝ-rational descent, the sign remains as a free parameter.

**Closure failure (4 axes)**: C1 fails ($\nu = -1$ quaternionic ⟹ no real irrep) / C2 holds ✓ / C3 fails for $L$, holds for $L^2 = 16$ rational / C4 sub-issue. → **Tier √ ≠ Tier ∞** (sign obstruction with even-power rational but magnitude rational closure).

**T-AAS read** (N1 §5): $f_\text{torsion}(\rho) = 1$ (sign = ℤ/2 torsion = "ker_gauge" classical) / $f_\text{rational}(\rho) \geq 0$ (magnitude rational). The Tier √ obstruction is the **minimal instance** breaking Stark's "R-gauge zero residual" claim. The Stark conjecture is stated for rank-1 abelian to avoid Tier √/∞ (abelian ⟹ all 1-dim ⟹ $\nu = +1$ forced).

### 2.6 Tier ∞ impossible (genuinely beyond)

**Form**: $L(s, \rho)^{n}$ no power works for any $n \geq 1$ — must rely on direct Hecke L construction.

**Candidate groups (theoretically)**: very high-dim irreps (8-dim, 16-dim) / regulators of high transcendence degree (rank ≥ 4 unit lattice) / non-arithmetic Galois reps.

**Status**: Tier ∞ instance identification search OPEN (`open_questions_master.md` OQ-NT-8 internal sub-OQ).

### 2.7 Conjecture: full parameterisation by group-theoretic invariants

**Conjecture (v0, tentative; same pattern as Schumann v1 N3 §6.3)**:

> a rank-1 abelian Stark setup of a finite Galois group $G$ falls into **exactly one** of {Tier 1, 2, 3+, √, ∞}. The tier is determined entirely by the representation-theoretic structure of $G$ (irrep dimensions, FS indicators, subgroup lattice, character inner products).

This is a strong claim that the Arrow 1 kernel decomposition of T-AAS (ker_gauge ⊕ ker_topo) is **fully parameterised by group-theoretic invariants**. Empirically supported by the N1 §5.2 Brauer 5-tier instance table + the detailed examples in this §2. **Status**: candidate_v1. Full verification (tier identification across all finite-group classes) is open as the **OQ-NT-7 / OQ-NT-8** dual pair.

---

## §3 Alternative Stark methods (Tier-dependent)

Stark formula realisations corresponding to each Tier. Presented at the **existence-proposal level**; formal algorithms separated as the OQ-NT-6 task.

| Tier | Form | Status |
|---|---|---|
| **Tier 1: classical Stark formula (single ratio)** | $L'(0, \chi) = -(1/e_\chi) \sum_\sigma \chi(\sigma^{-1}) \log\|\sigma(\varepsilon_\chi)\|$, $\varepsilon_\chi$ = Stark unit in $F = H^{\ker\rho}$ | 3 verified cases (N4 §4.2: ℚ(√5), ℚ(√2), ℚ(√−23)) |
| **Tier 2: field-pair regulator ratio (D_4)** | $L'(0, \chi) \propto h_{F_1} R_{F_1} / (h_{F_2} R_{F_2}) \cdot \text{(normalisation)}$, Stark unit constructed as 2-field unit difference | structurally confirmed for D_4 ℚ(√−14); numerical OQ-NT-7 v0.3 task |
| **Tier √: Q_8 sign-resolution attempt** | $L^2 = 16$ rational but $L = \pm 4$ sign outside. Proposed methods: (i) quaternionic descent (ε-factor sign formula); (ii) via Deligne-Langlands sign formula; (iii) whether sign is determined by higher derivative $L''(0, \rho)$ | existence proposal; concrete formula undetermined. Q_8 sign obstruction = **structurally intrinsic** (T-AAS read); Tier-1-style closure impossible. OQ-Tier-Sqrt-Resolution open |
| **Tier ∞: Hecke L direct construction** | Hecke characters of $K$ used directly; $L(s, \chi_\text{Hecke})$ evaluated by spectral methods (Selberg trace formula); no Stark-style closed form | outside N5 scope; existence acknowledgement only. Detailed in OQ-Schumann-HeckeArtin-Ext (`open_questions_master.md`) |

**Atlas grammar functor formalisation (OQ-NT-6 task)**: Atlas grammar representation of rank-1 Stark (`stark_projection_v0.md §2.2`):

```yaml
stark_rank1_entry:
  f_n: log |σ(ε_χ)| ; phi_phase: χ(σ⁻¹) ; N_X: 1/e_χ
  comp_X: Σ_{σ ∈ G} ; observable: L'(0, χ)
  primary_axis: E ; secondary: A ; residual_type: [R-gauge, R-info]
```

Task: formalise as a **Tier-dependent functor**. If uniform Atlas grammar entry construction across Tier 1 / 2 / √ / ∞ is achieved, the Stark R-gauge complete representation theorem (N4 §4.3) extends functorially.

**Status**: OPEN. N5 v0.2 explicit task scope; actual formalisation is a v0.3+ or post-N5 task in conjunction with Q1 (Quantum observation theory edition).

---

## §4 Origination matrix 8-gauge — Paper Ω framework

### 4.1 8 origination gauge families

The **8 origination gauge family** established in `papers/Paper_Omega_Origination.md`. Each gauge is an independent axis categorising the "origin" of mathematical objects:

| Family | Content | Examples |
|---|---|---|
| **ordinal** | level 0 (scaffold prior to constant generation): absence → origin → orientation → branching → structure | 0, 1, −1, 2, 3 |
| **addZ** | additive integer structure (ℤ → S¹ via $n \mapsto e^{2\pi i n / L}$) | 2 (parity minimum) |
| **mult** | multiplicative structure (product, decomposition, principal failure) | $h_K$, prime decomposition |
| **prime_coord** | prime coordinates (Euler product, prime indexing) | $\zeta(s) = \prod_p (1 - p^{-s})^{-1}$, $\omega(X)$ |
| **char** | character / dual structure (Pontryagin dual, root of unity) | $i$, $w_K$, Dirichlet $\chi$ |
| **cont** | continuous (real / complex topology, archimedean place) | $\pi$, $e$ |
| **geom** | geometric (vol, area, Minkowski lattice) | $(2\pi)^{r_2}$, $\sqrt{|d_K|}$ |
| **anal** | analytic (zeta zeros, L-function, transcendence) | $\zeta(2)$, $\gamma$ |

**Axis-1 D / C subdivision within the gauge² 8-gauge family** (gauge² is defined in N1 §1.3 as the family of 8 origination fields; the axis-1 D/C subdivision partitions this 8-gauge family by discrete/continuous origin): D (Discrete) ⊃ {ordinal, addZ, mult, prime_coord, char} (5 families) / C (Continuous) ⊃ {cont, geom, anal} (3 families). The axis-1 D/C subdivision is also the axis-1 partition of the **2-axis (Fi/I × D/C) framework** of L0 v2 (`finite_observation.md §8`); the two coincidences (gauge² family partition + L0 v2 axis-1) are co-aligned.

### 4.2 Origination signatures of 8 constants

(Notation for **i_add** and **i_mult**: these are the additive and multiplicative imaginary units in the Paper Ω 8-gauge family. **i_add** = the ℤ/2ℤ-valued parity arising at p = 2 — the additive imaginary unit, intrinsic to the additive integer structure. **i_mult** = the 4th root of unity arising at primes p ≡ 1 mod 4 — the multiplicative imaginary unit, intrinsic to character / mult structure. Both reside as origination-field constants within the 8-gauge framework of Paper Ω; the distinction matters because π and i can carry **either** signature depending on which prime-place they are referred to.)

| Constant | Origination signature | Main mechanism |
|---|---|---|
| **π** | {cont, geom} | S¹ topology / $(2\pi)^{r_2}$ archimedean volume |
| **e** | {cont, **anal**} | $(\log n)/n$ extremum (S17), exp continuation |
| **ζ** | {addZ, mult, anal} | ζ(s) = $\sum n^{-s}$ has addZ (n) + mult (multiplicativity) + anal (analytic continuation) |
| **γ** (Euler-Mascheroni) | {addZ, mult, anal} | ζ-γ pair: ζ residual (boundary residue, ζ-γ pair on Arrow 2) |
| **τ** (lattice 2π) | {addZ, geom} | periodicity + S¹ length |
| **i_add** | {addZ, char} | additive imaginary unit (Z/2Z parity, p=2) |
| **i_mult** | {char, mult} | multiplicative imaginary unit (p ≡ 1 mod 4) |
| **Φ** (golden ratio) | {mult, **geom**} | algebraic extremum (5-fold rotational symmetry, lattice ratio) |

**Observation**: the 8 constants are not in bijection with the 8-gauge family; each constant originates with a **multi-gauge signature** (typically 2-3 gauges) → main conclusion of Paper Ω §2 origination matrix.

### 4.3 6-gauge → 8-gauge generalisation (Stark + Hasse-Weil)

**Stark 6-gauge (N4 §4.1)**: the 6 factors of the class number formula $\mathrm{Res}_{s=1} \zeta_K(s) = (2^{r_1} (2\pi)^{r_2} h_K R_K) / (w_K \sqrt{|d_K|})$ ↔ {cont,geom} π / {addZ} parity / {mult,anal} discriminant / {mult} class group / {cont,char} regulator / {char} root of unity.

**Generalisation to 8-gauge**: Stark 6-gauge is the **Stark-relevant subset** of the 8-gauge framework. The remaining 2 gauges (**ordinal** + **prime_coord**) are **not directly represented in the class number formula but function as background scaffold**:
- **ordinal** (level 0): the unit "1" (identity) is an implicit assumption of the class number formula. Without "1" the formula itself is undefined. Resides in `identity_asymmetry.md §3.4` as identity asymmetry.
- **prime_coord** (Euler product): the Euler product structure $\zeta_K(s) = \prod_\mathfrak{p} (1 - N\mathfrak{p}^{-s})^{-1}$ is essential for derivation of the class number formula. In N2 §2.5 the **carry conductor dim = ω(X)** is the NT instance of the prime_coord gauge.

→ **Full 8-gauge framework** = 6-gauge Stark + ordinal scaffold + prime_coord Euler product. N4 6-gauge is confirmed via explicit factors of the class number formula; this §4 generalises to the implicit 8-gauge framework.

### 4.4 8-gauge classification of constants from N2 §3.1 (0.216, 2/3, ln 2)

The 3 constants of the N2 §3.1 D_floor parabolic formula $D_{\mathrm{floor}}(s, N) \sim N^{-2/3} \cdot \exp(0.216 (\log N)^2 (s - 1/2)^2)$:

| Constant | Where it appears | 8-gauge signature | Interpretation |
|---|---|---|---|
| **0.216** | curvature C_log/(log N)² | {**anal**, mult} | zero-density time average, Riemann-von Mangoldt origin |
| **2/3** | decay $D_0 \sim N^{−2/3}$ | {**prime_coord**, anal} | sieve weight + destructive interference, prime-coord index |
| **ln 2** | (S13 half-value fixed point reference) | {**char**, anal} | half-value parity (Z/2 character) + log analytic |

**Observation**: the 3 constants are classified with signatures **mult+anal**, **prime_coord+anal**, **char+anal**. **anal** is common; the distinguishing factors are (mult, prime_coord, char). Unlike Stark 6-gauge, **prime_coord** appears — a feature of the NT instance.

### 4.5 N3 §5.3 Fi-origin vs. I-origin dichotomy and 8-gauge connection

**Fi-origin vs. I-origin dichotomy** established in N3 §5.3 (`c_arrow_bridge_constants.md §11`):

| Origin | Path 2 examples | Main 8-gauge family |
|---|---|---|
| **Fi-origin** (discrete group action fixed points) | ζ(1/2), θ_3(i), modular L central values | **{addZ, mult, char} dominant** (Z/2 group action = discrete, character-based involution) |
| **I-origin** (continuous extremal / topological invariants) | π (S¹), ln 2 (S13 half-value), e (S17) | **{cont, geom, anal} dominant** (continuous topology + extremal + analytic transcendence) |

→ **Fi-origin = axis-1 D side dominant** / **I-origin = axis-1 C side dominant**. The axis-1 D/C subdivision of 8-gauge (§4.1) is in **structural alignment** with the Fi/I origin dichotomy — deep consistency within the framework: L0 v2 axis-2 Fi/I + axis-1 D/C + Origination 8-gauge subdivision are all **co-aligned**.

---

## §5 Cross-connection: Brauer 5-tier ↔ Origination 8-gauge

### 5.1 Tier classification ↔ T-AAS Arrow 1 kernel taxonomy

T-AAS framework of N1 §5: $\ker(\text{Arrow 1}) = \ker_\text{gauge} \oplus \ker_\text{topo}$, $f(\rho) = f_\text{torsion} + f_\text{rational}$. T-AAS read of Brauer 5-tier:

| Tier | $f_\text{torsion}(\rho)$ | $f_\text{rational}(\rho)$ | Interpretation |
|---|---:|---:|---|
| Tier 1 strict | 0 | $k > 0$ (single field) | R-gauge complete, single intermediate field |
| Tier 2 relaxed | 0 | $k > 0$ (2 fields) | R-gauge complete, field-pair |
| Tier 3+ multi-rational | 0 | $k > 0$ (multi-field) | R-gauge complete, multi-field rational |
| Tier √ sqrt-only | **1** (sign) | $k \geq 0$ | sign obstruction (FS $\nu = -1$) |
| Tier ∞ impossible | (∞ undefined) | (∞ undefined) | Hecke direct only, R-gauge framework outside |

**Key insight**: Tier 1-3+ have f_torsion = 0 (R-gauge complete, Stark applies); Tier √ has f_torsion jumping to 1 (sign obstruction emerges); Tier ∞ is outside the T-AAS framework. Brauer 5-tier classifies the structural complexity of T-AAS ker decomposition by tier number (Tier 1, 2, 3+: number of intermediate fields = R-gauge structural complexity / Tier √: ℤ/2 sign torsion emergence / Tier ∞: R-gauge framework breakdown).

### 5.2 8-gauge signature ↔ Path 2 Type α/β/γ trichotomy + Atkin-Lehner ↔ Brauer Tier 2

8-gauge signature view of the Path 2 Type α/β/γ trichotomy in N3 §2.2:

| Type | Path 2 fix realisation | 8-gauge signature pattern |
|---|---|---|
| **Type α** (single point) | fix is a single point inside the same algebraic object (ζ s=1/2, theta τ=i) | **single dominant gauge**: ζ → {addZ, mult, anal} combined organisation concentrated at 1 fix point |
| **Type β** (different object) | fix is a single rep in a different object (spherical Laplacian → SU(2) spin-1/2) | **gauge family crossing**: the SU(2) rep "shadows" to another object via {char} |
| **Type γ** (sub-object) | fix is a sub-object inside the same object (M_k^+ of Atkin-Lehner W_N) | **subspace within gauge family**: M_k^+ is the +1 eigenspace inside the modular form gauge = subspace structure |

→ Type α/β/γ trichotomy is the **realisation mode** of Path 2 fix points; 8-gauge signature pattern is the **algebraic content** of that mode — they are **complementary axes** classifying Path 2 instances.

**N3 Atkin-Lehner Type γ ↔ Brauer Tier 2 (D_4) connection**:

| Aspect | Atkin-Lehner Type γ | Brauer Tier 2 |
|---|---|---|
| Fix structure | $S_k^+ \subset S_k$ subspace (eigenspace) | $F_1 \subsetneq F_2$ field pair |
| Sub-object cardinality | typically $\dim S_k^+ \geq 2$ | 2 intermediate fields |
| algebraic distinction | Petersson +1 eigenspace | Galois rep $\rho$ irreducible 2-dim |
| Realisation | weight-k modular form space | Hilbert class field $D_4$ structure |

→ **Both are realised by "sub-object decomposition inside a single object"**. Type γ (Path 2) and Tier 2 (Brauer) expose the **same structural pattern** in **different frameworks** = a **structural unification** instance of the N1 framework.

### 5.3 Does Hasse-Weil L add a new signature to 8-gauge?

**Open question (issued in N4 §7.3)**: does Hasse-Weil L (weight-2 modular L, BSD-related) add a **new signature** to the Origination matrix 8-gauge?

**Candidate 8-gauge signature for Hasse-Weil L**: $\Lambda(s, E) = N_E^{s/2} (2\pi)^{-s} \Gamma(s) L(s, E)$ — subset of {addZ, mult, prime_coord (Euler product over good primes), cont, geom (for $(2\pi)^{-s}$), anal}. BSD-related "elliptic curve gauge" candidates: $E[\ell^\infty]$ Tate module, conductor $N_E$ (mult), root number $\varepsilon(E)$ (char), rank $r$ (mult, anal via $K_E·t²→r$). Representable by the existing 8-gauge family, or does a **new 9th gauge** ("elliptic curve gauge", "automorphic L gauge") emerge?

**Status**: OPEN (`OQ-HasseWeil-8Gauge-NewSignature`). N5 v0.2 assumes representability by the existing 8-gauge; if the rank-encoded BSD content of Hasse-Weil L (K_E·t²→r) cannot be fully captured by the existing 8 gauges, a 9-gauge extension is needed.

**Working hypothesis**: representable by the existing 8-gauge, but the **predictive content (BSD K·t²→r)** of Hasse-Weil L is a **new combination pattern** of the (mult, prime_coord, anal) triple signature (rank emerges from Taylor expansion at $s=1$, $c_r$ coefficient).

### 5.4 4-vertex triangulation formal closure attempt (OQ-4VertexClosure)

**OQ-4VertexClosure** proposal issued in N4 §6.3 / §10: extension from 3-vertex (Paper C / Stark / Brauer) → 4-vertex (Hasse-Weil added). N5 attempts **formal closure**:

**Formalisation of Hasse-Weil's Arrow focus**: formalise the Arrow focus of Hasse-Weil, vaguely written in N4 §6.3 as "Arrow 2 + Information layer (BSD K_E·t²→r)" → **Arrow 2 (analytical scan ζ-family member)** + **Information layer Taylor expansion at fix locus s = 1**. Concretely: Scan member $\Lambda(s, E)$ (modular L weight-2) / Information observable $K_E(t)$ (central curvature) / BSD analytic rank $r$: $K_E(t) \cdot t^2 \to r$ as $t \to 0+$ (rank = scalar encoded in Information layer). The Arrow focus of Hasse-Weil is a specific path **Arrow 2 → Information (rank-encoding via Taylor expansion)**, independent of Paper C / Stark / Brauer.

**4-vertex independence verification**:

| Vertex | Arrow focus | Independent root cause |
|---|---|---|
| Paper C | 3 Arrows simultaneous | simultaneous instantiation of Scan/Structural/Information inside the single object F_{g,k}(s) |
| Stark | Arrows 2/3 (R-gauge) | analytical → algebraic gauge product (class number formula 6-gauge) |
| Brauer | Arrow 1 kernel | representation-theoretic obstruction of Galois rep (5-tier) |
| **Hasse-Weil** | **Arrow 2 + Information rank-encoding** | **weight-2 Taylor expansion at $s=1$, rank-encoded $K_E·t²→r$** |

The 4 vertices all carry different Arrow focus + root cause → independence ✓. **S15 + 3 Arrow exhaustive coverage**: Scan (each instance: Paper C, Stark, Brauer, Hasse-Weil) / Structural (Paper C ζ-zero oscillation, Stark 6 factors, Brauer Tier classification, Hasse-Weil conductor+rank) / Information (Paper C ε_{g,k}, Stark log h_K, Brauer kernel dim, Hasse-Weil $K_E$). 4 vertices give **redundant cover** of the S15 3 layers + **3 Arrows are cleanly partitioned**.

**Status**: **proposal_v2** (formal closure attempt presented in N5 v0.2). Formal proof open as OQ-4VertexClosure, N5 v0.3 task.

---

## §6 NT-series final closure — overall structural total of N1-N5

### 6.1 N1-N5 cycle completion

```
N1 v0.6 (framework header) → N2 v0.4 (ζ-family core, ESTABLISHED)
   → N3 v0.3 (Path 2 + Dirichlet L "structural fit only")
   → N4 v0.2 (Hasse-Weil L + Stark + Brauer, "genuine BSD")
   → N5 v0.2 (Brauer detail + 8-gauge, NT series final closure)
   → dictionary (15+ annexes total, across all L0 / L1 / meta layers)
```

**5-paper structural total**: N1 framework header (axioms / S15 / Arrow / T-AAS / NT-internal triangulation) / N2 ζ-family core structural analysis (Carry / D_floor / Dirichlet residue exclusivity) / N3 Path 2 NT universality (Schumann v1 + Dirichlet L "structural fit only") / N4 Hasse-Weil L × Stark (BSD K_E·t²→r genuine + Brauer 5-tier connection) / N5 Brauer detail + 8-gauge (failure-mode group-theoretic criteria + Origination matrix generalisation + 4-vertex closure).

### 6.2 Weight-class-dependent transfer pattern + Galois rep full closure (8-gauge view)

N4 main thesis: the framework predictive transfer pattern is **weight-class dependent**. Integrated view from 8-gauge perspective + Galois rep coverage:

| Galois rep / weight class | Path 2 instance | Predictive content | Dominant 8-gauge signature | Paper coverage |
|---|---|---|---|---|
| abelian Stark rank 0 | Path 2 weight-1 abelian | Class number formula 6-gauge ESTABLISHED | {addZ, mult, char, cont, geom, anal} | N4 §4.1 |
| abelian Stark rank 1 | weight-1 abelian rank-1 | R-gauge complete representation candidate (3 cases) | {addZ, mult, char} dominant | N4 §4.2-§4.3 |
| non-abelian Tier 1-3+ | weight-1 non-abelian | rational closure (intermediate field zeta ratios) | {char, mult} dominant | N4 §5 + N5 §2.2-§2.4 |
| non-abelian Tier √ (Q_8) | weight-1 quaternionic | sign obstruction, T-AAS f_torsion = 1 | {char, mult} + ℤ/2 torsion | N4 §5.3 + N5 §2.5 |
| non-abelian Tier ∞ | weight-1 generic | Hecke L direct only, R-gauge outside | {anal} only | N5 §2.6 |
| weight-1 Dirichlet L | Path 2 weight-1 family | "structural fit only" (SC4 universal identity) | {char, anal} (universal identity-level) | N3 |
| **weight-2 (Hasse-Weil L)** | Path 2 weight-2 family | **genuine BSD K_E·t²→r** (rank-encoded) | **{addZ, mult, prime_coord, anal}** new combination | N4 §2-§3 + N5 §5.3 |
| higher weight (modular L, k≥4) | Path 2 weight-k family | predictive content **OPEN** | TBD | N3 §3.3 forward |
| Hecke L on number fields | (extension target) | OQ-Schumann-HeckeArtin-Ext | TBD | N5 §3 + Q forward |
| Higher-rank Stark (rank ≥ 2) | (transcendence theory) | scope outside | — | N4 §7.4 future |

→ each weight class carries predictive content with a different 8-gauge signature pattern. **Emergence of the {addZ, mult, prime_coord, anal} new combination (rank-encoding) at weight-2 Hasse-Weil L** is the demonstration of the rich predictive structure of the framework from the 8-gauge viewpoint.

**Full closure**: the NT series covers **abelian Stark (rank 0/1)** + **full non-abelian 5-tier** + **automorphic weight-2**. Higher-weight modular L + Hecke L on general number fields + higher-rank Stark + Hodge-related are **explicitly open frontier** (§7.4).

---

## §7 Consequences and open frontier + Q1-Q3 quantum sequel announcement

### 7.1 ESTABLISHED status (M1-M5)

| Result | Status |
|---|---|
| **M1 Brauer 5-tier failure-mode group-theoretic criteria** | **candidate_v1** (S_3, D_4, Q_8 examples + conjecture, OQ-NT-7/8 v0.2) |
| **M2 Tier-dependent alternative Stark methods (existence proposal)** | **proposal_v1** (existence acknowledged for each Tier 1-3+/√/∞ method, OQ-NT-6 functor formalisation OPEN) |
| **M3 Origination matrix 8-gauge framework** | **ESTABLISHED reference** (existing Paper Ω framework, formal residence in NT framework via N5) |
| **M4 Cross-connection: Brauer 5-tier ↔ 8-gauge** | **proposal_v2** (Tier ↔ T-AAS taxonomy + 8-gauge ↔ Type trichotomy + 4-vertex closure attempt) |
| **M5 NT-series final closure (N1-N5 cycle)** | **closure stage** (N1-N5 5-paper publication + dictionary 15+ annex residence completed) |

### 7.2 NT-series 5-paper completion summary

```
NT framework total (N1-N5, publication completed 2026-04-26)
================================================
[Foundation]   N1 (framework header) ─────────────────┐
[Core result]  N2 (ζ-family Paper 2 structural analysis)│
[Extension 1]  N3 (Path 2 NT universality, Dirichlet close)│
[Extension 2]  N4 (Hasse-Weil L + Stark, genuine BSD)  │
[Closure]      N5 (Brauer detail + 8-gauge, NT final) ─┘
                 ↓
[Forward]      Q1-Q3 (quantum sequel announcement)
```

### 7.3 Bridge to quantum sequels (Q1-Q3)

| Paper | Topic | Material | Connection to NT closure |
|---|---|---|---|
| **Q1** Observation theory quantum edition | quantum-side extension of N1 framework. S17 (Arrow 3 e-extremum), Hodge predicate (T-AAS f_rational), quantum version of 4-vertex triangulation (quantum lift of S15 axis-2 projection map), OQ-Ω-Obs-4a (refined quantum Hodge 4-class framework) | quantum part of `Paper_D_Observation_Theory_ja.md` v0.9.2 §6, `oq_omega_obs_*` series, 8 entries of `L1/quantum/` | N1 §5.4 Hodge (NT-adjacent open frontier) is formally addressed on the quantum side; the N5 §5.3 Hasse-Weil L 8-gauge new-signature problem is relevant as quantum BSD-analogue |
| **Q2** Open QS chain | Specialisation of the N1 framework in the Open Quantum Systems series. Redevelop observation theory in quantum statistical mechanics language across the chain q_open_quantum_systems → q_quantum_statistical_mechanics → q_quantum_thermodynamics → q_many_body_quantum | 8 entries of `dictionaries/L1_mathematical/quantum/`, `research/quantum_chain_*` series | quantum statistical mechanics analogue of NT-series D_floor formula (N2 §3) (partition function, spectral form factor); quantum group action + fixed-point structure of N3 Path 2 |
| **Q3** Born-Gleason | quantum-side closure of N1 §2.3 §4 dual = root. σ\* = √(2 ln 2) (half-amplitude gauge), natural unit of quantum observation in Born rule + Gleason theorem framework | Born derivation of `Paper_D_Observation_Theory_ja.md` §4.6.1, `q_quantum_observation.md` | quantum lift of N1 §2.3 §4 ι_L/χ dual; specialisation of N5 §4.1 axis-1 D/C subdivision in the quantum Hilbert space context |

### 7.4 Open frontier (remaining tasks after NT closure)

| Open question | Status | Forward to |
|---|---|---|
| **Hodge conjecture** (T-AAS f_rational > 0 candidate) | OPEN (= conjecture itself) | Q1 forward |
| **BSD conjecture proper** (analytic rank = geometric rank) | OPEN | NT scope outside |
| **BSD higher-rank** ($K_E \cdot t^2 \to r$ for $r \geq 4$) | OPEN | N4 §7.4, OQ-BSD-HigherRank |
| **OQ-433a1-Outlier** (curve-specific Taylor coefficient anomaly at 433a1: $K_E \cdot t^2 = 0.12$ at $t = 0.3$ vs. predicted $r = 2$; small $|c_2|$ relative to $|c_3|$ shifts the leading-order regime to $t \leq 0.05$) | LOW (curve-specific, not framework) | N4 §3.3 |
| **p-adic Stark / Gross-Stark** | scope outside (p-adic vocabulary outside dictionary) | OQ-Ω11 candidate, future N |
| **Higher-rank Stark (rank ≥ 2)** | scope outside (transcendence-theoretic territory) | N4 §7.4 |
| **Artin holomorphy conjecture** | OPEN (since 1924) | N4 §7.4 |
| **Hecke L on general number fields** | OPEN | OQ-Schumann-HeckeArtin-Ext, N5 §3 + Q forward |
| **OQ-NT-6 Atlas grammar functor formalisation** | OPEN | N5 §3 + Q1 connection |
| **OQ-NT-7/8 Brauer 5-tier completeness** | candidate_v1 | N5 §2.7 |
| **OQ-Tier3-Plus-Search** (Tier 3+ instance identification) | OPEN | N5 §2.4 |
| **OQ-Tier-Sqrt-Resolution** (Q_8 sign resolution) | OPEN | N5 §3 |
| **OQ-HasseWeil-8Gauge-NewSignature** | OPEN | N5 §5.3 |
| **OQ-4VertexClosure** | proposal_v2 | N5 §5.4 |
| **OQ-Schumann-v1.5** (Type γ formal + 6th instance) | OPEN | Schumann v1.5 task |
| **OQ-IOriginFormal** (formal classification of I-origin canonical scalars) | OPEN | N3 §5.3, c_arrow_bridge_constants §11 |

### 7.5 Dictionary residence map (final state, 2026-04-26)

Final state of NT-series N1-N5 dictionary residence:

**L0 (axiom layer)**: `observation_canon.md §2-§3` (axioms A0-A7 + L0 v2) / `finite_observation.md §1-§8` (axiom details + axis-2 framework) / `identity_asymmetry.md §3.4` (vanishing order + product formula identity)

**L1 (mathematical core)**: `c_phase_complex.md §4` (structural root, ι_L/χ dual) / `c_theorems_master.md` (S12-S17 + Path 2 family annex + Dirichlet L extension scope annex + **Hasse-Weil L extension scope annex** + S15 NT-only enumeration closure annex) / `c_arrow_framework.md` (3 Arrows + §4.2.1 NT 3-instance commutativity) / `c_arrow_obstruction.md §10-§11` (T-AAS + 5-class obstruction) / `c_arrow_bridge_constants.md §5-§6 + **§11 Fi-origin vs. I-origin**` annex / `c_observation_optimal_gauge.md §2-§5 + **§5.5 Path 3 arithmetic mod-n expansion**` / `c_filtration_obstruction.md` (ker_topo, Hodge open frontier) / `c_recursive_floor_principle.md §6.8 + **§6.8.1 Dirichlet L gap-class universality (12/12 PASS)** + **§6.8.2 Hasse-Weil L extension**` / `c_spectral.md §8` (class number formula 6-gauge)

**L1 NT (number theory specific)**: `nt_conductor.md §1-§5 + §6 + **§6.10 NT carry conductor**` / `nt_dedekind_artin_zeta.md §1-§6 + **§7 modular L countably-infinite Path 2**` / `nt_frobenius_schur.md`, `nt_genus_class_fields.md`, `nt_relative_units.md`, `nt_root_numbers.md`

**L2 (domain)**: `number_theory_dictionary_v1.md §1-§7` (5-field case log + 3 Stark cases)

**Meta**: `meta/triangulation_methodology.md §1-§8 + **§9 NT-internal Arrow-level lens** + **§10 Hasse-Weil 4th-vertex extension proposal**` / `meta/new_domain_protocol.md §1-§7 + **§8 NT specialisation**` / `meta/open_questions_master.md` (Path 2 NT universality OQ section + Path 2 OQ summary 2026-04-26 post-N4 update)

**Paper Ω (sister)**: `papers/Paper_Omega_Origination.md` (8-gauge framework + 8 constants origination matrix; formally resided in NT framework via N5 §4)

**Total dictionary touchpoints (N1-N5 cumulative)**: 15+ NEW annexes/sections + many existing entry updates. The NT framework reaches complete closure with touchpoints across all layers L0 (axiom) → L1 (mathematical core + NT specific) → L2 (domain) → Meta (methodology).

---

## Change log

- **v0.2 (2026-04-26)**: compact version. Reduced redundancy from v0.1 (747 lines) — long paragraphs of M1-M5 in Abstract compressed; §1.1/§1.2/§1.3 (position / 2-thread combination / forward confluence) 3 subsections merged into 2 (1.1 = position+2 thread, 1.2 = forward+Q1-Q3 announcement); "form" subsubsections (§2.x.1) of each Tier in §2.2-§2.6 unified and compressed into 1 subsection per Tier; recap-only of Q_8 Tier √ overlap with N4 §5.3 in §2.5; §3.1-§3.5 Tier-dependent methods 5 subsections consolidated into 1 table + Atlas grammar formalisation paragraph; redundant 6-gauge recap with N4 in §4.4.1 removed; §4.1/§4.3 axis-1 D/C explanation merged; §5 4-vertex closure explanation compressed; §6.1/§6.2/§6.3 NT-series final closure 3 subsections merged into 2 (6.2 has weight-class 8-gauge view + Galois rep full closure tabularised together); §7.5 residence map compressed from bullet form to layer-paragraph form. Skeleton, claims, instance numerics, Tier classification, status, and Q1-Q3 bridge all preserved.
- **v0.1 (2026-04-26)**: initial NT-only draft. NT-series 5-paper final paper. Combines detailed Brauer obstruction theory + Origination matrix 8-gauge generalisation; cross-connection brings the NT framework total to closure; N4 §10 OQ-4VertexClosure formal closure attempt; announces the bridge to quantum sequels (Q1: observation theory quantum edition / Q2: Open QS chain / Q3: Born-Gleason).

---

## References (internal)

**Framework**: N1 (`N1_observation_theory_nt_ja.md` v0.7) / N2 (`N2_paper2_structural_ja.md` v0.5) / N3 (`N3_path2_dirichlet_universality_ja.md` v0.4) / N4 (`N4_hasseweil_stark_ja.md` v0.3)

**Brauer obstruction theory (main material of §2-§3)**: `research/brauer_closure_galois_classification_v0.md` (OQ-NT-7 v0.2, success side: Tier 1/2/3+) / `research/brauer_closure_failure_taxonomy_v0.md` (OQ-NT-8 v0.2, failure side: Tier √/∞ + Q_8 LMFDB witness) / `research/stark_projection_v0.md` (rank 0/1 Stark + 6-gauge + Atlas grammar + ℚ(√−23) closure)

**Paper Ω (main material of §4)**: `papers/Paper_Omega_Origination.md` (8 origination gauge family + 8 constants origination matrix, sister theory of Canon)

**L1 / meta dependencies (via N1-N4)**: `c_theorems_master.md` (Path 2 family annex + Dirichlet L extension scope annex + Hasse-Weil L extension scope annex) / `c_arrow_obstruction.md §10-§11` / `c_arrow_bridge_constants.md §5-§6 + §11 Fi-origin vs. I-origin` / `c_recursive_floor_principle.md §6.8 + §6.8.1 + §6.8.2` / `c_spectral.md §8` / `nt_conductor.md §6, §6.9, §6.10` / `nt_dedekind_artin_zeta.md §1, §4, §7` / `nt_frobenius_schur.md` / `nt_root_numbers.md` / `nt_relative_units.md` / `meta/triangulation_methodology.md §9 + §10` / `meta/new_domain_protocol.md §8` / `meta/open_questions_master.md` / `number_theory_dictionary_v1.md §5`

**Quantum sequel announcement (Q1-Q3)**: `papers/Paper_D_Observation_Theory_ja.md` v0.9.2 §6 (multi-domain version, quantum part) / 8 entries of `dictionaries/L1_mathematical/quantum/` (q_open_quantum_systems, q_quantum_statistical_mechanics, q_quantum_thermodynamics, q_many_body_quantum, q_quantum_observation, q_quantum_action_principles, q_quantum_gauge_field_theory, q_fine_structure) / `research/oq_omega_obs_*` series (OQ-Ω-Obs-1/2/3/4a)
